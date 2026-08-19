LDAP stands for Lightweight Directory Access Protocol. It is a protocol ***used by applications and systems to access, search, and manage centralized directory information*** such as users, groups, and computers. LDAP uses a hierarchical directory structure and commonly operates on ***TCP port 389***, while LDAP over TLS, commonly called LDAPS, uses port 636. 



Active Directory is a directory service provided by Microsoft that supports LDAP, so LDAP and Active Directory are not the same thing—LDAP is the protocol, while AD is the directory service. LDAP is commonly used for centralized authentication and retrieving user and group information across applications and systems.





**# LDAP:**

* It is a network protocol used to access, search, and manage directory information such as users, groups, computers, and organizational resources over a network.
* Think of LDAP as a standard way for applications to communicate with a directory service.





**# How LDAP Works:**

Suppose an employee logs into an application.

*User*

&#x20;*↓*

*Application*

&#x20;*↓*

*LDAP Authentication Request*

&#x20;*↓*

*LDAP Server / Active Directory*

&#x20;*↓*

*Search User*

&#x20;*↓*

*Verify Credentials*

&#x20;*↓*

*Success / Failure*

&#x20;*↓*

*Application grants access*





**# LDAP Directory Structure:**

LDAP uses a hierarchical structure called a Directory Information Tree (DIT).



Example:

dc=company,dc=com

│

├── ou=Users

│     ├── uid=shambhu

│     └── uid=rahul

│

├── ou=Groups

│     └── cn=Developers

│

└── ou=Computers





**# What Can LDAP Do?**

* Search users
* Authenticate users
* Retrieve user information
* Manage groups
* Query organizational information
* Manage directory objects
* Provide centralized identity information to applications

