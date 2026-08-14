**# inode (Index Node):**

Is is a data structure in the Linux filesystem that stores the metadata (information) about a file or directory, but not the file's name or actual data.



**# Important to Remember:**

Filename → Stored in the directory.

Metadata → Stored in the inode.

Actual content → Stored in data blocks.



**# Why Do We Need Inodes?**

Imagine millions of files on a disk.

Instead of searching the entire disk, Linux:

1. Finds the filename in the directory.

2\. Gets the inode number.

3\. Reads the inode.

4\. Uses the block addresses stored in the inode to find the file's data.

This makes file access efficient.



**# Inode Fields:**

| ------------------- | ---------------------------------------------------------- |

| Field               | Description                                                |

| ------------------- | ---------------------------------------------------------- |

| Inode Number        | Unique identifier of the inode                             |

| File Type           | Regular file, directory, symbolic link, etc.               |

| Permissions         | Read, write, execute permissions                           |

| Owner UID           | User ID of the owner                                       |

| Group GID           | Group ID of the owner                                      |

| File Size           | Size of the file in bytes                                  |

| Link Count          | Number of hard links to the file                           |

| Access Time (atime) | Last time the file was accessed                            |

| Modify Time (mtime) | Last time the file content was modified                    |

| Change Time (ctime) | Last time the inode metadata changed                       |

| Block Pointers      | Addresses of the data blocks containing the file's content |

| ------------------- | ---------------------------------------------------------- |



**# If the Inode is Full, Can We Create a File?**

No. If all available inodes are used, you cannot create any new files or directories, even if there is plenty of free disk space.

Check inode usage: ***df -i***



**# Can two filenames point to the same inode?**

Yes. This happens with hard links, where multiple directory entries reference the same inode.



**# What happens if inode usage reaches 100%?**

New files and directories cannot be created until some inodes are freed, even if the filesystem still has free storage space.

