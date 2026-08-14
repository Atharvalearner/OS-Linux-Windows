Network Policy Server (NPS) is a Windows Server role that functions as a RADIUS server and RADIUS proxy. It provides Authentication, Authorization, and Accounting (AAA) for network access. When a user connects to a VPN, Wi-Fi, or wired network, the access device sends a RADIUS request to the NPS server. NPS verifies the user's credentials against Active Directory, evaluates configured network policies such as group membership, authentication method, or time restrictions, and then returns either Access-Accept or Access-Reject. NPS also logs authentication events for auditing and troubleshooting. It is commonly used with 802.1X wireless authentication, VPN servers, and enterprise wired networks to centrally control who can access the network.



***# Think of it this way:***

**Active Directory =** Stores user identities.

**NPS =** Decides whether those identities are allowed onto the network.



***# Real Company Example:***

Suppose your company has:

1 Domain Controller, 1 NPS Server, 5 Wireless Access Points, 300 Employees



**Workflow:**

*Employee Laptop*

*↓*

*Wireless Access Point*

*↓*

*NPS Server*

*↓*

*Active Directory*

*↓*

*Verify User*

*↓*

*Apply Network Policy*

*↓*

*Access Granted*



***# Can NPS work without Active Directory?***

Yes, NPS can work with other identity sources, but in Windows environments it is most commonly integrated with Active Directory to authenticate domain users.



***# What is the default RADIUS port?***

Authentication: UDP 1812

Accounting: UDP 1813

