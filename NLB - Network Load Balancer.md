Network Load Balancing (NLB) is a Windows Server feature that distributes incoming client requests across multiple servers. It improves application availability, scalability, and performance by ensuring that no single server handles all client traffic. Clients connect to a single Virtual IP (VIP), and NLB distributes requests among the servers in the cluster. If one server fails, NLB automatically stops sending traffic to that server and continues using the remaining healthy servers. NLB is commonly used for IIS web servers, web applications, VPN servers, and other stateless services that require high availability and load distribution.



***# Simply:***

It is same as HAProxy in Linux which distributes traffic on behalf of backend servers.





***# Architecture:***

&#x20;                   Users

&#x20;                     │

&#x20;                     ▼

&#x20;              xyz.company.com

&#x20;                     │

&#x20;                     ▼

&#x20;              Virtual IP (VIP)

&#x20;               192.168.1.100

&#x20;                     │

&#x20;     ┌───────────────┼───────────────┐

&#x20;     ▼               ▼               ▼

&#x20;+-----------+   +-----------+   +-----------+

&#x20;|  Server1  |   |  Server2  |   |  Server3  |

&#x20;| IIS + App |   | IIS + App |   | IIS + App |

&#x20;+-----------+   +-----------+   +-----------+





**| ---------------- | ----------------------------------------------------- |**

**| Topic            | Remember This                                         |**

**| ---------------- | ----------------------------------------------------- |**

| NLB              | Distributes client requests across multiple servers   |

| Purpose          | High availability + scalability + performance         |

| VIP              | One shared IP for the cluster                         |

| Common Uses      | IIS, Web Apps, VPN, Remote Desktop Gateway            |

| Benefit          | If one server fails, others continue serving requests |

| NLB              | Load sharing                                          |

| Failover Cluster | Service takeover during failures                      |

| ---------------- | ----------------------------------------------------- |

