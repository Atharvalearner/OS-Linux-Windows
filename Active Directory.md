***# Active Directory (AD):***

* It is a ***directory service*** developed by Microsoft.
* Used in Windows Server to ***centrally manage and organize users, computers, groups, printers, and other network resources*** in a Windows domain.
* It ***provides authentication, authorization, and centralized administration*** for an organization's network.
* AD as a ***central database*** that contains information about all resources in the organization.





***# Basic Features of Active Directory:***

**1. Centralized User Management:**

Allows administrators to centrally create, modify, disable, or delete user accounts instead of managing each computer individually.



**2. Authentication:**

Authenticates users by verifying their usernames and passwords before allowing access to the network.



**3. Authorization:**

Authorizes users by checking their permissions and determining which resources they can access.



**4. Domain Management:**

A Domain is a collection of computers and users managed under one central database for centralized management and security.



**5. Group Policy (GPO):**

Allows administrators to centrally apply security settings and configuration policies to users and computers across the domain.

Examples: Disable USB devices, Enforce password complexity, Set desktop wallpaper



**6. Organizational Units (OU):**

Logical containers used to organize users, computers, and groups, making administration easier.

Each OU can have its own policies which applies to all resources under it.

eg. Company have departments like HR, Finance, IT which is nothing but OUs.



**7. Security Groups:**

Instead of assigning permissions to individual users, permissions are assigned to groups.



**8. DNS Integration**

Active Directory depends heavily on DNS.

DNS helps to Find Domain Controllers, Locate services, Authenticate users

Without DNS, Active Directory cannot function properly.



**9. Single Sign-On (SSO):**

Users log in once and can access multiple domain resources without repeatedly entering credentials.

Example: After logging in, users can access: File Server, Printer, Email, Shared folders without logging in again.





**# Real-Life Example**

**A company has:** 1,000 employees, 800 computers, 50 servers, 100 printers



***Without Active Directory:***

Each computer has separate user accounts.

Passwords are managed locally.

Security settings differ from one system to another.



***With Active Directory:***

Employees use one domain account.

Password policies are enforced centrally.

Shared resources are managed consistently.

Group Policies automatically configure all systems.





***# Quick Revision***

**AD**: Microsoft's directory service for Windows Server.

**Purpose**: Centralized management of users, computers, and resources.

**Main Functions**: Authentication, Authorization, Administration.

**Stores**: Users, Groups, Computers, Printers, Servers, OUs.

**Key Features**: Domain management, Group Policy, Security Groups, DNS integration, Replication, Single Sign-On, Centralized Security Policies.

**Benefits**: Simplifies administration, strengthens security, and enables centralized control in enterprise networks.

