If I forget the root password, I reboot the Linux system and enter the GRUB menu. I edit the boot entry and boot into an emergency shell using rd.break on RHEL-based systems or Recovery Mode on Ubuntu. The root filesystem is mounted as read-only, so I remount it as read-write. Then I use chroot /sysroot to access the installed operating system. After that, I reset the password using the passwd root command. If SELinux is enabled, I run touch /.autorelabel. Finally, I reboot the server and log in using the new root password.





***# Recovery Process (RHEL/CentOS/Rocky Linux)***

**1. Reboot the System:**

Restart the server.

When the GRUB menu appears: *Press e to edit the boot entry*.



**2. Edit the Boot Parameters:**

Find the line that starts with: *Linux or linux16*

At the end of that line, append: *rd.break*

This tells the kernel to stop before switching to the real root filesystem.



**3. Boot with the Modified Entry for Emergency Shell:**

Press: *Ctrl + X or F10*

The system boots into an emergency shell.



**4. Mount the Root Filesystem as Read-Write:**

By default, the root filesystem is mounted as read-only.

Remount it as read-write: *mount -o remount,rw /sysroot*



**5. Change Root to the Installed System:**

Run: *chroot /sysroot*

Now you're working inside the installed Linux system.



**6. Reset the Root Password:**

Run\*: passwd root\*

Enter the new password when prompted.



**7. Relabel SELinux (If Enabled):**

On systems with SELinux enforcing, create the autorelabel file: touch /.autorelabel

This ensures file security contexts are corrected on the next boot.



**8. Exit and Reboot:**

*reboot*





***# Complete Workflow:***

Forgot Root Password

&#x20;       ▼

Reboot System

&#x20;       ▼

GRUB Menu

&#x20;       ▼

Press "e"

&#x20;       ▼

Add rd.break

&#x20;       ▼

Boot (Ctrl+X)

&#x20;       ▼

Mount Root Filesystem (Read-Write)

&#x20;       ▼

chroot /sysroot

&#x20;       ▼

passwd root

&#x20;       ▼

touch /.autorelabel

&#x20;       ▼

Reboot

&#x20;       ▼

Login with New Password





***# Which command changes the root password?***

passwd root



***# Why do we use chroot /sysroot?***

chroot changes the root directory of the current shell to the installed operating system. This allows commands like passwd to update the actual system instead of the temporary recovery environment.



***# Why do we remount the filesystem?***

The root filesystem is mounted as read-only in emergency mode to protect the system. We remount it as read-write so we can modify files, including updating the root password.



***# Why do we use touch /.autorelabel?***

On SELinux-enabled systems, it tells the system to relabel files with the correct SELinux security contexts during the next boot.



***# What is Boot Parameters in GRUB?***

Boot parameters are kernel arguments passed during system startup through GRUB. When we press ‘e’ in GRUB, we temporarily edit the kernel boot line (starting with ‘linux’) and append parameters like rd.break to enter into emergency mode. These parameters control how the kernel behaves during boot. It is not editing a configuration file, but modifying the boot command for that session only.

