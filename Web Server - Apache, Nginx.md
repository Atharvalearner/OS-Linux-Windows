Apache and Nginx are popular web servers used to serve web content over HTTP and HTTPS. Apache uses a process or thread-based architecture where each request is handled by a separate process, making it flexible and suitable for dynamic applications. Nginx uses an event-driven architecture, which allows it to handle a large number of concurrent connections efficiently with low resource usage, making it ideal for high-traffic websites. Apache is commonly used for dynamic content, while Nginx is often used as a reverse proxy, load balancer, or for serving static content. In modern architectures, both are often used together, where Nginx handles incoming traffic and Apache processes backend requests.





**# Web server:**

It is software that serves web content (HTML, CSS, JS, APIs) to users over HTTP/HTTPS.

Browser → Request (HTTP/HTTPS) → Web Server → Response (Web Page)



**1. Apache:**

HTTP Server is one of the oldest and widely used web servers.



***Working:***

* Uses process-based / thread-based model
* Each request is handled by a separate process or thread



***Flow:*** Client Requests → Apache → Creates Process/Thread → Sends Response



***Directory Structure***

▪ Main config: **/etc/httpd/conf/httpd.conf**

▪ Virtual hosts:  **/etc/httpd/conf.d/**

▪ Document root: **/var/www/html/**

▪ Logs: **/var/log/httpd**



***Usage and Feature:***

* Used in Small to medium traffic websites
* Applications needing flexibility
* PHP-based applications
* Easy to configure
* Good for dynamic content



***Commands: (RHEL pkg name httpd and Debian based apache2)***

sudo systemctl start httpd

sudo systemctl stop httpd

sudo systemctl restart httpd

sudo systemctl enable httpd

sudo systemctl status httpd







**2. Nginx:**

It is a high-performance web server and reverse proxy.

Works as: Web server, Reverse proxy, Load balancer



***Working:***

* Uses event-driven, asynchronous architecture
* Handles thousands of requests with fewer resources
* Client Requests → Event Loop → Handles Multiple Requests Efficiently



***Key Features:***

* High performance
* Low memory usage
* Excellent for static as well as dynamic content



***Directory Structure:***

Config: **/etc/nginx/nginx.conf**

Web root: **/usr/share/nginx/html**



**Commands:**

sudo systemctl start nginx

sudo systemctl enable nginx



***Usage:***

High traffic websites

Microservices architecture

Load balancing

Reverse proxy (very common in DevOps)



| Feature        | Apache               | Nginx                 |

| -------------- | -------------------- | --------------------- |

| Architecture   | Process/Thread-based | Event-driven          |

| Performance    | Moderate             | High                  |

| Resource Usage | More                 | Less                  |

| Best For       | Dynamic content      | Static + high traffic |

| .htaccess      | Supported            | Not supported         |

