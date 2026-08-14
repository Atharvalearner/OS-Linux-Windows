iptables is a command-line utility used to configure the Linux kernel's Netfilter firewall. It allows administrators to create rules that permit, block, or modify network traffic based on parameters such as IP addresses, ports, protocols, and interfaces. iptables organizes rules into tables and chains. The most commonly used table is the filter table, which contains the INPUT, OUTPUT, and FORWARD chains. Each incoming or outgoing packet is checked against these rules, and actions such as ACCEPT, DROP, or REJECT are applied. iptables is widely used to secure Linux servers by controlling network access.



**# Simple definition:**

iptables is the firewall configuration tool in Linux that controls which network packets are allowed or blocked.





***# Netfilter:***

* It is the firewall framework built into the Linux kernel.
* It performs the actual packet filtering.
* where iptables is the user-space command-line tool used to configure Netfilter.



***# Table:***

* A table is a collection of chains for a particular purpose.

| -------- | -------------------------------------- |

| Table    | Purpose                                |

| -------- | -------------------------------------- |

| filter   | Filtering traffic (most commonly used) |

| nat      | Network Address Translation            |

| mangle   | Modify packet headers                  |

| raw      | Connection tracking exceptions         |

| security | SELinux security rules                 |

| -------- | -------------------------------------- |



***# Chain:***

* A chain is a sequence of firewall rules.
* The three most commonly used chains are:
1. **INPUT:** Controls incoming packets destined for the local machine.
2. **OUTPUT**: Controls packets leaving the local machine
3. **FORWARD**: Controls packets passing through the Linux machine (when it acts as a router or firewall).



***# Rule:***

A rule tells iptables what to do with matching packets.





***# Common Actions (Targets):***

**ACCEPT**: Allow the packet

**DROP:** 	Silently discard the packet

**REJECT**: Reject the packet and notify the sender

**LOG:** 	Log the packet information





| --------------------------------------------- | --------------------------------------------------------------- |

| iptables                                      | firewalld                                                       |

| --------------------------------------------- | --------------------------------------------------------------- |

| Low-level firewall configuration tool         | Higher-level firewall management service                        |

| Rules managed manually                        | Uses zones and services                                         |

| Changes often require explicitly saving rules | Supports runtime and permanent configurations                   |

| More complex                                  | Easier to manage                                                |

| Directly configures Netfilter                 | Uses Netfilter underneath (often via nftables on newer systems) |

| --------------------------------------------- | --------------------------------------------------------------- |



**Common Commands:**

1. sudo iptables -L						.. list all firewall rules
2. sudo iptables -F						.. Flush all config except chain
3. sudo iptables -A INPUT -p tcp --dport 80 -j ACCEPT		.. Allow HTTP, -A: Append Rule, -p tcp: TCP Protocol, -j Accept: jump to Accept to Allow
4. sudo iptables -A INPUT -p tcp --dport 443 -j ACCEPT		.. Allow HTTPS
5. sudo iptables -A INPUT -s 192.168.1.100 -j DROP		.. Block IP
6. sudo iptables -D INPUT 1					.. Deletes the first rule in the INPUT chain.



***# Which table is used most frequently?***

The filter table. It is default table.



***# How does iptables communicate with Netfilter?***

iptables is a userspace utility used by administrators to configure firewall rules. These rules are passed to the Linux kernel and stored in the Netfilter framework. When a network packet arrives, Netfilter, which runs inside the kernel, evaluates the packet against the stored rules and decides whether to ACCEPT, DROP, or REJECT it. During packet processing, iptables is not involved; it is only used to create, modify, or delete the rules.

