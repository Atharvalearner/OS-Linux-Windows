Network management in Linux refers to configuring and managing network interfaces, IP addresses, DNS, and connectivity. One of the commonly used tools is nmcli, which is the command-line interface for NetworkManager. It allows us to configure network settings such as static or dynamic IP addresses, gateway, DNS, and to bring network interfaces up or down. It is widely used in server environments because it works without GUI and supports automation. For example, we can configure a static IP using nmcli by modifying the connection settings and applying them without restarting the system.





**# nmcli (Network Manager Command Line Interface):**

Command-line tool used to manage networking in Linux systems using the NetworkManager service.



**# It allows you to:**

Configure IP addresses (static/dynamic)

Bring interfaces up/down

Manage Wi-Fi/Ethernet

Set DNS and gateway

Create, modify, and delete network connections





**# Commands:**

nmcli connection show				.. # Show all connections

nmcli connection show -- active			.. # Show active connections only

nmcli device show enp0s3			.. # Show detailed device info

nmcli connection up enp0s3			.. # Bring connection up/down

nmcli connection down enp0s3

nmcli con down enp0s3 \&\& nmcli con up enp0s3	.. # Down and up in sequence (minimal downtime)

nmcli connection delete enp0s3			.. # Delete a connection

nmcli connection reload				.. # Reload all connections





**# Configure Static IP using nmcli:**

nmcli con mod eth0 ipv4.addresses 192.168.1.10/24

nmcli con mod eth0 ipv4.gateway 192.168.1.1

nmcli con mod eth0 ipv4.dns 8.8.8.8

nmcli con mod eth0 ipv4.method manual

nmcli con up eth0



In short modify interface setting as: **add IP address -> gateway -> dns ip -> method -> up interface**





**# Alternative Tools of nmcli**

**1. ip Command:**

Modern and powerful tool to manage networking.

commands:

ip a            # Show IP addresses

ip link         # Show interfaces

ip route        # Show routing table



Used for: Viewing network info, Temporary configuration



**2. ifconfig (Deprecated):** 

Older tool (from net-tools package)

Commands:  ifconfig, ifconfig eth0 up

Note: Deprecated in modern Linux, Replaced by ip



**3. systemd-networkd:**

Lightweight network manager (used in minimal systems)

Config path: /etc/systemd/network/

Used in: Containers, Cloud environments

