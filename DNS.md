DNS (Domain Name System) is used to translate domain names into IP addresses so that systems can communicate over a network. When a user enters a domain name, the DNS server resolves it through a hierarchical process involving root, TLD, and authoritative servers. 



In Linux, DNS is commonly configured using BIND. To configure it, I install the BIND package, define zones in the /etc/named.conf file, create forward and reverse zone files, start the DNS service, and allow port 53 in the firewall. DNS is essential for both internal name resolution in organizations and external internet access.



***(for Theory Refer Your Hand-Notes and refer this notes only for Configuration)***



**# DNS (Domain Name System):**

It is a protocol that translates human-readable domain names into IP addresses so that computers can communicate over a network.



**# DNS Working:**

*User → types google.com*

&#x20;       *↓*

*Client checks local cache*

&#x20;       *↓ if not found at local level*

*Query sent to DNS server*

&#x20;       *↓*

*If not found → Recursive lookup:*

&#x20;   *Root Server*

&#x20;       *↓*

&#x20;   *TLD Server (.com)*

&#x20;       *↓*

&#x20;   *Authoritative Server*

&#x20;       *↓*

*IP returned*

&#x20;       *↓*

*Browser connects to server*



**# Types of DNS Servers:**

1. Recursive DNS Server → resolves queries (ISP, local DNS)

2\. Authoritative DNS Server → has actual records

3\. Forwarder → forwards queries

4\. Caching DNS → stores responses





**# DNS Records:**

| Record | Purpose        |

| ------ | -------------- |

| A      | Domain → IPv4  |

| AAAA   | Domain → IPv6  |

| CNAME  | Alias          |

| MX     | Mail server    |

| NS     | Name server    |

| PTR    | Reverse lookup |

* NS (Name Server): Specifies the authoritative DNS servers for the domain-
* PTR (Pointer): Maps IP to domain (reverse DNS lookup)-
* SOA (Start of Authority): Contains administrative info about the zone





**# Simple configuration steps *(for Detail Config Open Sir's DNS Config file)*:**

1. Install DNS Server (eg. **bind9** for ubuntu or **bind-utils** for RHEL)
2. Edit Main Config file (**/etc/named.conf**) and Add forward and reverse zone/main Domain
3. Create Forward Zone **(/var/named/forward.zone)**
4. Create Reverse Zone **(/var/named/reverse.zone)**
5. Start and enable DNS Service	**(sudo systemctl enable --now named)**
6. Allow Firewall **(sudo firewall-cmd --add-service dns --permanent)**
7. Test DNS by dig or nslookup command.

