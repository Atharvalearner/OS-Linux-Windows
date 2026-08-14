NFS (Network File System) is a Linux file-sharing protocol that allows one Linux server to share a directory with other Linux systems over the network as if it were a local directory. It uses TCP port 2049. To configure it, I install the NFS server, export the required directory in /etc/exports, start the NFS service, open the firewall, and on the client install the NFS client package and mount the exported directory. NFS is commonly used for centralized storage, shared application data, backups, and sharing website files among multiple Linux servers. Root Squash is used to improve security by mapping the client's root user to the nobody user on the server.





**# NFS (Network File System):**

* An application layer distributed file system protocol that allows Linux/Unix systems to access a remote directory as if it were a local directory.
* It is mainly used for ***Linux-to-Linux file sharing*** and uses ***TCP port 2049***.



**# When should I use NFS?**

Share files between multiple Linux servers

Centralized storage

Shared application data

Shared backup storage

Shared website files across multiple web servers



**# Working:**

NFS Server

&#x20;   │

Exports /shared

&#x20;   │

Access Folder though Network

&#x20;   │

Client mounts /shared

&#x20;   │

Mounted as /mnt

&#x20;   │

Access files like a local directory



* Linux internally handles the communication between the client and server using RPC mechanisms after the mount request.





**# NFS Configuration: *(In lab We use nfs-utils package instead of nfs-kernel-server)***

**I) Server**

1. sudo apt install nfs-kernel-server
2. sudo mkdir /shared				.. Create shared directory
3. sudo vim /etc/exports			.. Edit exports file 
     /shared  172.16.140.0/24(rw,no\_root\_squash)
4. sudo exportfs -ra				.. Apply configuration
5. sudo systemctl enable --now nfs-kernel-server
6. sudo ufw allow 2049/tcp





**II) Client**

1. sudo apt install nfs-common

2\. showmount -e <Server-IP>						.. View available share directories

3\. sudo mount <Server-IP>:/shared\_directory /mnt\_point\_local\_system	.. Mount share

4\. sudo findmnt								.. # check if the nfs share is mounted correctly





**# Root Squash:**

Maps the root user on the client to the nobody user on the NFS server.

Purpose: Prevent client root users from modifying or deleting server files.



**# Scenario:**

***Three Linux application servers need access to the same website files.***

Configure an NFS server, export the shared directory, allow client access in /etc/exports, mount the shared directory on all Linux servers, and all servers will access the same files without maintaining separate copies.

