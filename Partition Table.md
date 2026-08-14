A partition table is a data structure stored on a disk that contains information about how the disk is divided into partitions.



**Simple definition:**

A partition table is like a map of the disk. It tells the operating system where each partition starts, where it ends, its size, and its type.



**# What Fields Does a Partition Table Store?**

| -------------------- | ------------------------------------------- |

| Field                | Description                                 |

| -------------------- | ------------------------------------------- |

| Partition Type       | Linux, Windows, EFI, Swap, etc.             |

| Starting Sector      | Where the partition begins                  |

| Ending Sector        | Where the partition ends                    |

| Partition Size       | Total size of the partition                 |

| Boot Flag            | Indicates whether the partition is bootable |

| Partition Identifier | Unique identifier (especially in GPT)       |

| -------------------- | ------------------------------------------- |



**# Types of Partition Tables**

1. MBR (Master Boot Record) (Older)

2\. GPT (GUID Partition Table) (Modern)



| ---------------------- | -------------------- | --------------------------------------------------------------- |

| Feature                | MBR                  | GPT                                                             |

| ---------------------- | -------------------- | --------------------------------------------------------------- |

| Full Form              | Master Boot Record   | GUID Partition Table                                            |

| Introduced             | Early 1980s          | Modern (UEFI era)                                               |

| Maximum Disk Size      | 2 TB                 | Much larger than 2 TB (up to \~8 ZiB theoretical)                |

| Maximum Partitions     | 4 primary partitions | Typically 128 partitions                                        |

| Backup Partition Table | No                   | Yes                                                             |

| Integrity Check        | No                   | CRC protection                                                  |

| Firmware               | BIOS                 | UEFI (preferred), though some systems can boot GPT in BIOS mode |

| Reliability            | Lower                | Higher                                                          |

| ---------------------- | -------------------- | --------------------------------------------------------------- |



**# Where is the MBR stored?**

In the first sector (512 bytes) of the disk.

