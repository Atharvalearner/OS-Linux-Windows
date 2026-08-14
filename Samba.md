**# Samba (SMB):**

* Samba is an open-source implementation of the SMB (Server Message Block) protocol that ***enables Linux systems to share*** ***files and printers with Windows systems***.
* ***SMB is the protocol***, while Samba is the software that implements it on Linux.
* It primarily uses ***TCP port 445***.





**# When should I use Samba?**

Windows ↔ Linux file sharing

Shared folders for Windows users

Printer sharing

Office file server

Mixed Windows and Linux environments





**# Working:**

Linux Server

&#x20;     │

Samba Service (smbd)

&#x20;     │

Shared Folder

&#x20;     │

Windows Client

&#x20;     │

Run \\\\Server-IP\\Share





**# Authentication:**

Windows users authenticate using: Username and  Password

On Linux System Samba verifies credentials and grants access based on the configured permissions.



**# Scenario**

***100 Windows employees need access to one common HR folder stored on a Linux server.***

Install Samba, configure the shared folder in /etc/samba/smb.conf, create Samba user accounts, restart the Samba service, and users can access the shared folder from Windows using \\\\Server-IP\\HR.





**# Samba Server Configuration**

1. sudo apt install samba			.. install samba service on Linux server

2\. sudo vim /etc/samba/smb.conf			.. Edit Main configuration file of samba

&#x09;	\[HR]

&#x09;	path = /srv/hr			.. # directory path to share the contents

&#x09;	browseable = yes		.. # user can see the contents of the shared directory

&#x09;	writable = yes			.. # make the share writeable

&#x09;	guest ok = no

&#x09;	valid users = smbuser		.. # list of users who can access the smb share

&#x20;   		force user = smbuser		.. # force clients to use this user



3\. sudo mkdir -p /srv/hr			.. Create shared folder

4\. sudo smbpasswd -a user1			.. Create new user for samba

5\. sudo systemctl enable smbd

6\. sudo systemctl start smbd

7\. sudo firewall-cmd --add-service=samba --permanent	.. Allow Firewall





**# Samba Windows Client Configuration:**

\- there is no configuration required on windows

\- open "Run dialog" (windows + R)

\- \\\\<server ip address>





**# Samba Linux Client Configuration:**

1. sudo yum install samba-client cifs-utils	.. install samba client and cifs utils
2. sudo mkdir /client\_smb\_share			.. # create a mount point
3. sudo mount -t cifs -o username=smbuser //samba\_server\_ip/share\_dir /client\_smb\_share	.. mount

