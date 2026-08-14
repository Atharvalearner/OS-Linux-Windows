DHCP (Dynamic Host Configuration Protocol) is used to automatically assign IP addresses and network configuration to clients. To configure a DHCP server in Linux, I install the DHCP package such as dhcp-server, then configure the main file /etc/dhcp/dhcpd.conf where I define the subnet, IP range, gateway, and DNS servers. After that, I bind the service to a network interface, start and enable the DHCP service, and allow UDP port 67 in the firewall. When a client connects, it follows the DORA process—Discover, Offer, Request, and Acknowledge—to receive an IP address dynamically.





**# Ports:**

Server: UDP port 67

Client: UDP port 68





\# DHCP Server Configuration in Linux on RHEL/CentOS/Rocky:



1\. Install DHCP Server:

***sudo yum install dhcp-server***



2\. Configure DHCP Main File Edit:

***sudo vim /etc/dhcp/dhcpd.conf***



Example:

***subnet 192.168.1.0 netmask 255.255.255.0 {***

&#x20;   ***range 192.168.1.100 192.168.1.200;			.. dhcp pool / network range***

&#x20;   ***option routers 192.168.1.1;				.. default gateway***

&#x20;   ***option subnet-mask 255.255.255.0;***		

&#x20;   ***option domain-name-servers 8.8.8.8, 8.8.4.4;	.. dns server***

&#x20;   ***default-lease-time 600;***

&#x20;   ***max-lease-time 7200;***

***}***



3\. Bind DHCP to Interface

***sudo vim /etc/sysconfig/dhcpd***		

&#x09;***DHCPDARGS=eth0				..*** add this line



4\. Start and Enable Service

***sudo systemctl enable --now dhcp-server***



5\. Allow Firewall

***sudo firewall-cmd --add-service dhcp --permanent***

***sudo firewall-cmd --reload***







**# DHCP Working (Flow):**

Client → DHCP Discover (Broadcast)

&#x20;       ↓

Server → From IP pool DHCP Offer an IP

&#x20;       ↓

Client → DHCP Request

&#x20;       ↓

Server → DHCP Acknowledge







