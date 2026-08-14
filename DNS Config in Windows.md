***# How to Configure DNS in Windows Server***



1\. Install DNS Role: Open: Server Manager

↓

Add Roles and Features

↓

Select DNS Server

↓

Install



2: Open DNS Manager: Tools

↓

DNS



3: Create Forward Lookup Zone: Right Click >> Forward Lookup Zones

↓

New Zone >> Choose: Primary Zone. Example company.local



4: Add Host Records. Example dc.company.local

↓

192.168.1.10 fileserver.company.local

↓

192.168.1.20

Now clients can resolve these names.



Step 5: Configure DNS Forwarder To resolve Internet websites, Open DNS Manager

↓

Server Properties

↓

Forwarders Add: 8.8.8.8 or 1.1.1.1



Now:

Internal names → Resolved locally.

External names → Forwarded to Public DNS.



***# Summary:***

*Install DNS role → Create Zone → Add Records → Configure Forwarders*

