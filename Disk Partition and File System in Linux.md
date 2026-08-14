To use a new disk, we first create a partition and then create a filesystem on that partition. In Linux, I can create a partition using fdisk or parted, create a filesystem using mkfs.ext4 or mkfs.xfs, create a mount point using mkdir, mount it using the mount command, and make it persistent by adding an entry to /etc/fstab



***# why do we need to create partition on disk instead of directly using it ?***

We create partitions to logically divide a physical disk into multiple independent sections. This helps organize data, install multiple operating systems, isolate system files from user data, improve management, and reduce the impact of filesystem corruption. Although it is technically possible to use an entire disk as a single filesystem without multiple partitions, partitioning provides better flexibility, security, and administration.



***# Create Partition and Filesystem:***

Suppose a new disk is attached.



1. **Check disks:** lsblk

Output: sda: 100G, sdb : 50G

Here, sdb is the new disk.



**2. Create Partition:** sudo fdisk /dev/sdb

Inside fdisk:

n      → New Partition

p      → Primary Partition

1      → Partition Number

Enter  → Default First Sector

Enter  → Default Last Sector

w      → Write Changes



**3. Create Filesystem**:

sudo mkfs.ext4 /dev/sdb1

OR

sudo mkfs.xfs /dev/sdb1



**4. Create Mount Point:**

sudo mkdir /Mounting\_Directory\_Name



**5. Mount Partition to Filesystem:**

sudo mount /dev/sdb1 /Mounting\_Directory\_Name



**6. Permanent Mount:** sudo vim /etc/fstab

/dev/sdb1   /Mounting\_Directory\_Name   FileSystem   defaults   0   0



| --------------------- | ------------------------- |

| Command               | Purpose                   |

| --------------------- | ------------------------- |

| lsblk                 | List disks and partitions |

| fdisk /dev/sdb        | Create partition          |

| mkfs.ext4 /dev/sdb1   | Create EXT4 filesystem    |

| mkfs.xfs /dev/sdb1    | Create XFS filesystem     |

| mkdir /data           | Create mount point        |

| mount /dev/sdb1 /data | Mount filesystem          |

| df -h                 | Check mounted filesystems |

| blkid                 | Display UUID              |

| vi /etc/fstab         | Configure permanent mount |

| --------------------- | ------------------------- |

