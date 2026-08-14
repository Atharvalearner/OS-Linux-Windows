***# systemd:***

* It is the default system and service manager in modern Linux distributions. 
* It is the first userspace process started by the Linux kernel and always runs with PID 1.
* Its responsibilities: 

&#x09;managing services

&#x09;managing dependencies

&#x09;mounting filesystems

&#x09;initializing networking

&#x09;managing user sessions

&#x09;monitoring services

&#x09;device events

&#x09;timers

* Unlike the older System V Init system, systemd starts services in parallel, supports dependency management, uses unit files instead of init scripts, and provides faster boot times and better service management.





***# What was before systemd?***

Before systemd, Linux used System V Init (SysVinit).

System V Init was the traditional init system. It was also PID 1.

It performed similar work, but much more slowly and with fewer features.





**| ------------------------------------------- | ---------------------------------------------------------- |**

**| systemd                                     | System V Init                                              |**

**| ------------------------------------------- | ---------------------------------------------------------- |**

| Modern init system                          | Older init system                                          |

| Parallel startup                            | Sequential startup                                         |

| Faster boot                                 | Slower boot                                                |

| Uses unit files                             | Uses shell scripts                                         |

| Dependency management                       | Limited dependency handling                                |

| Built-in logging (journald)                 | Relies on separate syslog daemons                          |

| Better service monitoring                   | Minimal service monitoring                                 |

| Supports socket, timer, and path activation | No native support for these features                       |

| systemctl command                           | service and chkconfig (or distribution-specific tools)	   |

| ------------------------------------------- | ---------------------------------------------------------- |



***# What happen If PID 1 dies ?***

The operating system cannot function correctly and typically panics or shuts down, because there is no process to adopt orphaned processes or manage essential services.





***# Why is systemd faster than SysVinit?***

Because it starts independent services in parallel and understands service dependencies, whereas SysVinit starts services one after another using shell scripts.

