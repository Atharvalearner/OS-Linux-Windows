**# FTP (File Transfer Protocol):**

* An application layer protocol used to transfer files between a client and a server over a TCP/IP network.
* It uses TCP port 21 for control communication and Port 20 for separate data connection for file transfer.



**# When should I use FTP?**

Upload website files

Download log files

Transfer backup files

Exchange files between systems



**# Working:**

Client

&#x20;  │

Connects to Port 21

&#x20;  │

Username + Password

&#x20;  │

Authentication

&#x20;  │

Control Connection Established

&#x20;  │

Separate Data Connection

&#x20;  │

Upload / Download File





1. ***Active FTP***

Client connects to server on 21

Client tells the server which client port to use

Server initiates the data connection back to the client from port 20.

Problem: Firewalls on the client side may block this incoming connection.



***2. Passive FTP***

Client connects to server on 21

Server replies with an available high-numbered port

Client initiates the data connection to that server port.

Works much better through NAT and firewalls, so it is the preferred mode today.



**Easy trick**

Active FTP: Server connects to Client

Passive FTP: Client connects to Server





**# Scenario 1:**

I would configure an FTP server (or preferably SFTP for secure environments), create a user account, grant the required permissions, enable the service, open the firewall for FTP, and then the developer can upload files using an FTP client like FileZilla.



**# Would you use FTP in production?**

No, I would generally prefer SFTP because FTP sends data and credentials in plain text, whereas SFTP uses SSH to encrypt the entire communication, making it much more secure for production environments.



**# SFTP port number: 22**, SFTP is subsystem of SSH so whenever we perform FTP operation through SSH service it will secure those connections data by default.





**# Scenario 2:** 

**Suppose a developer wants to upload website files to your Linux server. What would you do?**

I would install and configure vsftpd, disable anonymous access, create a dedicated FTP user, restrict the user to their home directory using chroot, enable Passive Mode, start the FTP service, configure the firewall to allow FTP traffic, and verify connectivity using an FTP client such as FileZilla or the Linux ftp command. Finally, I would test both file upload and download to ensure the configuration is working correctly.





**## Configuration:**

**I) Server configuration**

sudo yum update				.. # update yum repositories

sudo yum install vsftpd ftp		.. # install vsftpd (ftp server) and ftp (client)

sudo vim /etc/vsftpd/vsftpd.conf	.. # open the vsftpd configuration file to add the following configuration

&#x09;use\_localtime=YES		.. # when a file is created, the date and time will be set from server

&#x09;chroot\_local\_user=YES		.. # give access to the users created on this server

&#x09;chroot\_list\_enable=YES		.. # give access to the list of users

&#x09;pasv\_enable=YES			.. # configure the server to run in passive mode

&#x09;pasv\_min\_port=30000		.. # range of ephemeral ports used to communicate with client

&#x09;pasv\_max\_port=31000



sudo useradd ftpuser			.. # create a user

sudo passwd ftpuser			.. # change the password of ftp user

echo "ftpuser:test" | sudo chpasswd



sudo vim /etc/vsftpd/chroot\_list	.. # add the user the enabled users list

ftpuser					.. # add the user name



sudo systemctl enable --now vsftpd	.. # enable and start the server



sudo firewall-cmd --add-service ftp --permanent		.. # add the ftp service to the firewall

sudo firewall-cmd --reload				.. # reload the firewall settings

sudo firewall-cmd --list-services			.. # confirm the ftp is listed in opened services list



ftp localhost					.. # test the ftp on server

```



**II) Client configuration:**

sudo yum update				.. # update yum repositories

sudo yum install ftp			.. # install ftp client



vim /tmp/client-file			.. # create a temp file



ftp <server ip address>			.. # open ftp connection with server

ftp> pwd

ftp> put /tmp/client-file client-file		.. # It will upload a file named client-file from client machine to server machine (at /home/ftpuser directory)



ftp> cd /tmp

ftp> get server-file /tmp/server-file		.. # create a file on server machine at /tmp/server-file

