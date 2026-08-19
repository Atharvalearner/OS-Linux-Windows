&#x20;                   Active Directory

&#x20;                         │

&#x20;         ┌───────────────┼────────────────┐

&#x20;         │               │                │

&#x20;       LDAP           Kerberos          DNS

&#x20;         │               │                │

&#x20;Directory access     Authentication    Locate DC/services

&#x20;         │               │

&#x20;         └───────────────┼────────────────┘

&#x20;                         ↓

&#x20;                Windows Resources



1. **LDAP → Directory access:**

LDAP is used to query and access information stored in AD.

LDAP commonly uses TCP 389, and LDAPS uses TCP 636.

For example: Which groups does this user belong to ?



**2. Kerberos → Authentication:**

Kerberos is primarily used to authenticate the user and provide tickets for accessing services.

So when you log into a Windows domain, Kerberos is normally the primary authentication protocol.



**3. DNS → Finding Domain Controllers and services:**

DNS helps the client find the appropriate Domain Controller and other AD services.





**# What happens when you access a shared folder ?**

Suppose you access: \\\\fileserver\\finance

A simplified flow could be:

1\. DNS: Find fileserver / AD services

2\. Kerberos: Authenticate user / obtain service ticket

3\. SMB: Access the actual shared folder

4\. AD: User/group information and permissions help determine authorization

