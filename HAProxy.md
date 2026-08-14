HAProxy is a high-performance load balancer that distributes client requests across multiple servers using algorithms like round robin. It improves availability, performance, and prevents server overload. It also performs health checks to ensure traffic is only sent to healthy servers.





**# HAProxy (High Availability Proxy):**

an open-source, high-performance load balancer and reverse proxy widely used in production.



**Works at:** Layer 4 (TCP) and Layer 7 (HTTP/HTTPS)



**Why HAProxy?**

High performance (handles thousands of requests/sec)

Improves availability

Supports health checks

Prevents server overload

Used by big companies (Netflix, GitHub, etc.)



**# Working:**

***Flow: Client → HAProxy → Backend Servers***

1. Client sends request

2\. HAProxy receives it

3\. Chooses backend server (based on algorithm)

4\. Forwards request

5\. Sends response back to client



**# Load Balancing Algorithms:**

| Algorithm         | Description                          |

| ----------------- | ------------------------------------ |

| Round Robin       | Requests distributed equally         |

| Least Connections | Server with least active connections |

| Source            | Based on client IP (sticky sessions) |





**# HAProxy Configuration:**

1. sudo yum install haproxy-y		.. Install HAProxy package:

2\. sudo vim ***/etc/haproxy/haproxy.cfg	..*** main config file


frontend http\_front
bind \*:80
default\_backend web\_servers

backend web\_servers

balance roundrobin
server web1 192.168.1.10:80 check
server web2 192.168.1.11:80 check

