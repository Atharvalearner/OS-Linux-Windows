***# How to Configure DHCP in Windows Server***



**1: Install DHCP Role**

Server Manager >> Add Roles and Features >> DHCP Server >> Install



**2: Complete DHCP Post-Installation**

Click on Complete DHCP Configuration

This authorizes the DHCP server in Active Directory.



**3: Open DHCP Manager:** Tools >> DHCP



**4: Create a Scope**

Right Click: IPv4 >> New Scope. Example Scope Name: Office Network



**5: Configure IP Range**. Example: Start: 192.168.1.100, End: 192.168.1.200



**6: Configure Subnet Mask**: 255.255.255.0



**7: Configure Gateway:** 192.168.1.1



**8: Configure DNS Server**: Example: 192.168.1.10

This should usually be the Domain Controller or internal DNS server.



**Step 9: Activate the Scope**: Done

Now clients automatically receive IP addresses.





***# Summary:***

*Install DHCP role → Authorize Server → Create Scope → Configure IP Range, subnet mask, Gateway, DNS → Activate Scope*

