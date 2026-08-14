**# UFW:**

* It is a frontend for iptables (and on newer systems, it can use the nftables backend depending on the distribution).
* Instead of writing complex iptables rules, you use simple commands.
* Configuration: ***/etc/ufw/***
* Rules file: ***/etc/ufw/user.rules***
* Example:

&#x09;sudo ufw allow 22

&#x09;sudo ufw allow 80

&#x09;sudo ufw enable





**# firewall-cmd:**

* firewall-cmd is the command-line tool used to manage firewalld.
* Like UFW, it is also a frontend to the underlying Linux firewall framework.
* It supports advanced features like: Zones, Services, Runtime and permanent rules, Rich rules, Dynamic updates
* Configuration: ***/etc/firewalld/***
* Zone files: ***/etc/firewalld/zones/***
* Example:

&#x09;sudo firewall-cmd --add-service=http --permanent

&#x09;sudo firewall-cmd --add-port=8080/tcp

&#x09;sudo firewall-cmd --reload



| UFW                               | firewall-cmd (firewalld)             |

| --------------------------------- | ------------------------------------ |

| Stands for Uncomplicated Firewall | Command-line tool for firewalld      |

| Mainly **Ubuntu/Debian**              | Mainly **RHEL, Rocky, CentOS, Fedora**   |

| Easy to learn                     | More feature-rich                    |

| Best for beginners                | Best for enterprise servers          |

| Simple allow/deny rules           | Supports zones, services, rich rules |

| Few commands                      | More configuration options           |







**# Easy Memory Trick**

Ubuntu / Debian

&#x20;       ↓

&#x20;  UFW (Simple Firewall)



\-------------------------

Rocky / RHEL / CentOS

&#x20;       ↓

&#x20;  firewall-cmd (Enterprise Firewall)

