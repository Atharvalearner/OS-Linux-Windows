Virtual Hosting is a technique used to host multiple websites on a single server using the same IP address. It works by identifying the requested domain name from the HTTP request and serving the corresponding website. There are three types of virtual hosting: name-based, IP-based, and port-based. Name-based virtual hosting is the most commonly used, where multiple domains share the same IP and are differentiated using the Host header. In Linux, virtual hosting can be configured in Apache using VirtualHost blocks or in Nginx using server blocks. It is widely used in production to host multiple websites efficiently on a single server.





**# Virtual Hosting:**

It is a technique used in web servers to host multiple websites on a single server using the same IP address.



**# Types of Virtual Hosting**

**1. Name-Based Virtual Hosting:**

Multiple domains use the same IP address, differentiated by domain name.

example.com → same IP → server

site1.com   → same IP → server



**2. IP-Based Virtual Hosting:**

Each website has a different IP address

example.com → 192.168.1.10

site1.com   → 192.168.1.11



**3. Port-Based Virtual Hosting:**

Different websites use different ports

example.com → :80

site1.com   → :8080





**# Configuration:**

1. create directories for hosting the websites

sudo mkdir /var/www/website1 website2 website3



2\. create the default page for the websites in respected website1, 2, 3 directories

sudo vim /var/www/website1/index.html



3\. create configuration file to virtually host the website1, website2 and website3

sudo vim /etc/httpd/conf.d/website1.conf



&#x09;<VirtualHost \*:80>

&#x20;       	ServerName website1.local		

&#x09;        DocumentRoot /var/www/website1		.. root file path

&#x09;</VirtualHost>





sudo systemctl restart httpd



4\. add the following entries in /etc/hosts which acting as local DNS server (IP > Name):

sudo vim /etc/hosts



127.0.0.1   website1.local

127.0.0.1   website2.local

127.0.0.1   website3.local



5\. verify all the websites using curl in server itself:

curl website1.local





**# sites-available:**

Contains all virtual host configuration files

Path: ***/etc/apache2/sites-available/***



**# sites-enabled:**

Contains only active/enabled sites (via symbolic links)

Path: **/etc/apache2/sites-enabled/**

These are actually symlinks pointing to files in sites-available



**# Working:**

sites-available (all configs)

&#x20;       ├── example.com.conf

&#x20;       ├── site1.conf

&#x20;       ▼ (enable using command)

sites-enabled (only active ones)

&#x20;       ├── example.com.conf → ../sites-available/example.com.conf

