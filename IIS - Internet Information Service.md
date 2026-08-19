IIS (Internet Information Services) is Microsoft's web server software for Windows Server. It is used to host websites, web applications, REST APIs, and web services. When a client sends an HTTP or HTTPS request, IIS processes the request, serves static content or forwards it to the application, and returns the response to the client. IIS supports features such as Application Pools for isolation, Virtual Directories, SSL/TLS for secure communication, Windows Authentication, and detailed logging. It commonly supports HTTP, HTTPS, FTP, FTPS, and WebDAV protocols. In enterprise environments, IIS is widely used to host internal portals, business applications, and ASP.NET applications integrated with Active Directory.



***Simply:***

IIS allows users to access websites and web applications hosted on a Windows Server.



***# How to Host a Website***

1: Open IIS Manager

2: Right Click: Sites >> Add Website

3: Provide: Site Name



4: Choose Physical Path for Maps a physical folder to a web path. Example: D:\\HRWebsite Accessible as https://company/hrwebsite



5: Configure Binding

Protocol: HTTP

Port: 80

Hostname: hr.company.local



6: Click Start Website. Now users can access the site.



***# How Does IIS Work?***

Suppose you type: https://company.com

*Browser*

*↓*

*DNS*

*↓*

*IIS Server*

*↓*

*Application*

*↓*

*Database*

*↓*

*Response to Browser > Displays Website*





***# What is an Application Pool?***

An Application Pool isolates one or more web applications so that if one application fails, the others continue running independently.



***# What is the default website location in IIS?***

C:\\inetpub\\wwwroot



***# What is a Binding in IIS?***

A binding defines how a website is accessed by specifying the protocol (HTTP/HTTPS), IP address, port number, and optional hostname.



***# Can IIS host multiple websites?***

Yes. IIS can host multiple websites on the same Windows Server using bindings, which is similar to virtual hosting. A binding identifies a website using IP address, port, and host name. For example, I can host company.com, shop.com, and blog.com on the same server and the same port 80 by configuring different host names. When a request arrives, IIS checks the Host header and matches it with the configured binding, then sends the request to the corresponding website and its physical directory. For HTTPS, SNI can be used to host multiple SSL websites on the same IP and port.



**# Types of Virtual Hosting in IIS:**

1\. Host-name based:

Different hostnames, same IP/port.

192.168.1.10:80

&#x20;       ├── company.com

&#x20;       ├── shop.com

&#x20;       └── blog.com



2\. IP-based:

Each website has a different IP.

192.168.1.10 → company.com

192.168.1.11 → shop.com

192.168.1.12 → blog.com



3\. Port-based:

This is possible but generally less convenient for public websites.

192.168.1.10:80   → company.com

192.168.1.10:8080 → shop.com

192.168.1.10:8081 → blog.com

