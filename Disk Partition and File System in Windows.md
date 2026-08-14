In Windows, I can create a partition using the Disk Management GUI. First, I open Disk Management by running diskmgmt.msc. If the disk is new, I initialize it using GPT or MBR. Then I right-click the unallocated space and select "New Simple Volume." I specify the partition size, assign a drive letter, choose the NTFS filesystem, optionally perform a quick format, and click Finish. Windows then creates the partition, formats it, and makes it ready for use.





***# Real Company Example:***

Suppose a company installs a new 1 TB hard disk in a Windows File Server.

The administrator:

1. Opens Disk Management (diskmgmt.msc).
2. Initializes the disk using GPT or MBR.
3. Right click Unallocated Space.
4. Select New Simple Volume
5. Enter Partition Size.
6. Assigns drive letter eg. E:.
7. Formats it with NTFS.
8. Labels it Backup.

9\. Finish



Now the backup software stores data in: E:\\Backup





***# What is "Unallocated Space"?***

It is disk space that has no partition and cannot be used until a partition is created.

