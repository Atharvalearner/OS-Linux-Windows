A proxy server acts as an intermediary between clients and the internet. Squid is an open-source forward proxy server that provides caching, access control, and monitoring. When a user sends a request, Squid checks if the content is cached; if yes, it returns it directly, otherwise it fetches it from the internet, stores it, and then serves it. Squid also supports ACLs to block or allow websites, authentication for user control, and logging for monitoring user activity. It is widely used in organizations to improve performance, save bandwidth, and enforce security policies.



**# Proxy Server:**

It acts as an intermediary between client and internet.

***Client → Proxy (Squid) → Internet -> (Web Server)***

Client does NOT directly access the internet

All requests go through the proxy





**# Types of Proxy:**

Forward Proxy → Used by clients to access internet

Reverse Proxy → Used by servers to handle incoming requests





**# Squid:**

Squid is an open-source caching proxy server used to improve performance, control access, and monitor internet usage.

Squid is mainly a Forward Proxy.

Port no: 3128



**# Key Features of Squid:**

**1. Caching:** Stores frequently accessed content, Reduces bandwidth usage, Faster response



**2. Access Control (ACLs):** Block/allow websites, Restrict users or IPs, Time-based rules

Example:

acl blocked\_sites dstdomain .facebook.com

http\_access deny blocked\_sites



**3. Logging \& Monitoring:**

Logs stored in: /var/log/squid/access.log

Tracks: User activity, Websites accessed



**4. Authentication:** Username/password-based access

**5. Bandwidth Control:** Limit internet usage per user/group



**# Squid Installation:**

sudo yum install squid –y

sudo systemctl start squid      I

sudo systemctl stop squid       

sudo systemctl restart squid    

sudo systemctl status squid     

sudo systemctl enable squid     



* The main configuration file is: ***/etc/squid/squid.conf***



**# Squid ACL :**

acl localnet src 192.168.1.0/24		.. # Define the ACL. localnet: temp name



http\_access allow localnet		.. # Apply the rule (Allow first, then deny all)

http\_access deny all





**# Blocking websites**

***Method A: Block Individual Domains***

acl blocked\_sites dstdomain facebook.com youtube.com twitter.com	.. dstdomain: destination domains

http\_access deny blocked\_sites



***Method B: Block from External File***

acl blocked\_sites dstdomain "/etc/squid/blocked\_domains.txt"

http\_access deny blocked\_sites





**# Blocking File Downloads by Extension**

***Method A: Block by URL Path Extension***

acl blocked\_files urlpath\_regex -i \\.exe$ \\.zip$ \\.mp3$ \\.avi$ \\.mp4$

http\_access deny blocked\_files



***Method B: Block from External File***

acl blocked\_files urlpath\_regex -i "/etc/squid/blocked\_extensions.txt"

http\_access deny blocked\_files

