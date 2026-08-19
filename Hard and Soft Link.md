***## Inode:*** 

* Contain information about each file in the filesystem. 
* Normally, an inode doesn't contain a file's name, which is located in a directory instead.  
* An inode contains information such as the type of file, the permission bits, the owner, the group, the file size, and the time when the file was modified





***## Hard Link:***

* Mirror images of the originally linked files and are linked with an inode number.
* A hard-linked file remains even after the original file is deleted. Since hard links point to inodes, they cannot be implemented on directories.
* Command: **ln \[original filename] \[link name]**





***## Soft Link / Symbolic links:***

* soft links are linked to the file name and can reside on the same as well as different file systems.
* When a soft link is created or deleted, it does not affect the original file, but when the original file is deleted, the soft link stops working.
* Typically, soft links are aliases (alternative paths) for the original file.
* Command: **ln -s \[original filename] \[link name]**





&#x09;	**Hard Link							Soft Link**

1. Hard-linked files have the same inode number. 		Soft-linked files have different inode numbers.

2\.  Despite deleting the target file, it remains valid.		When an original file is deleted, it becomes invalid.

3\.  Hard links are faster than soft links. 			Soft links are slower than hard links.

4\.  The command used for creating a hard link in Linux is "ln". The command used for creating a soft link in Linux is “ln -s”.

5\.  There is no way to use it across file systems.  		You can use it on any file system.

6\.  Hard links cannot use relative paths. 			Both absolute and relative paths can be used in soft links.

