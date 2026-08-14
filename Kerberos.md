Kerberos is a secure ticket-based authentication protocol that provides Single Sign-On. Instead of sending the user's password across the network every time, Kerberos authenticates the user once through the Authentication Server in the Key Distribution Center. After successful authentication, the user receives a Ticket Granting Ticket (TGT). Whenever the user wants to access a service like a file server or database, the client presents the TGT to the Ticket Granting Server, which issues a Service Ticket. The client then sends the Service Ticket to the target server, and the server grants access after verifying it. Since only encrypted tickets are exchanged and passwords are never transmitted over the network, Kerberos is much more secure than repeatedly sending passwords





***# Kerberos:***

* A network authentication protocol 
* That securely authenticates users and services over an insecure network using secret-key cryptography and tickets instead of sending passwords across the network.
* It provides Single Sign-On (SSO) where user authenticate once and access authorized resources(Email, Database, File server, Printer, etc)



***Simple definition:***

Kerberos is a ticket-based authentication protocol that allows users to securely log in once and access multiple services without repeatedly entering their password.



***# Kerberos is commonly used in:***

Microsoft Active Directory, 

Linux Identity Management (FreeIPA)

Enterprise Networks, 

Universities, 

Large Organizations



***# TGT (Ticket Granting Ticket):***

* It is issued after successful login.
* Purpose: It allows the user to request service tickets without entering the password again.



***# Service Ticket:***

* A Service Ticket is a ticket issued by the TGS that allows access to a specific service, such as a file server or database.
* Each service gets its own ticket



***# KDC (Key Distribution Center):***

It is central authentication server in Kerberos. 

It authenticates users and issues tickets. 

It consists of:

Authentication Server (AS)

Ticket Granting Server (TGS)



***# Why is Kerberos Secure?***

1\. **Password is Never Sent Across the Network**: Only encrypted messages and tickets are exchanged.

**2. Ticket-Based Authentication**: Instead of passwords, Kerberos uses tickets.

**3. Mutual Authentication:** The client verifies the server. The server verifies the client.

**4. Encryption:** Tickets are encrypted using secret-key cryptography.

**5. Time-Stamped Tickets:** Tickets contain timestamps. Old tickets expire.



***# Which port does Kerberos use?***

TCP/UDP Port 88



***# Does Kerberos encrypt all application data?***

Not necessarily. Kerberos primarily provides authentication. Whether the application's traffic is encrypted depends on the application protocol. For example, HTTPS encrypts web traffic, while Kerberos authenticates the user.

