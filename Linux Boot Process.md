The Linux boot process starts when the system is powered on. First, the BIOS or UEFI performs the POST (Power-On Self-Test) to verify the hardware and then looks for a bootable device. It loads the GRUB bootloader, which displays the boot menu and loads the Linux kernel along with the initramfs into memory. The kernel then initializes the hardware, memory, and required drivers. Next, the initramfs loads any additional drivers needed to access the real root filesystem and mounts it. After that, the kernel starts systemd, which becomes PID 1. Systemd starts all system services such as networking, SSH, logging, and other background services. Finally, Linux displays the login prompt or graphical desktop, and the system is ready for use.





The Linux boot process is the sequence of steps that occur from the moment the computer is powered on until the user is presented with a login prompt or desktop.



***# Booting Stages:***

*Power ON*

&#x20;     *↓*

*BIOS/UEFI (Hardware Check)*

&#x20;     *↓*

*GRUB (Loads Kernel + Initramfs)*

&#x20;     *↓*

*Kernel (Initialize Hardware \& Memory)*

&#x20;     *↓*

*Initramfs (Mount Real Root Filesystem)*

&#x20;     *↓*

*systemd (Starts All Services)*

&#x20;     *↓*

*Login Prompt / GUI*





***# Bootloader (GRUB):***

* Once BIOS/UEFI finds the boot device, it loads the bootloader.
* GRUB (Grand Unified Bootloader) is the bootloader that loads the Linux kernel and initramfs and provides the boot menu.
* Typical main configuration file: ***/etc/default/grub***
* Generated configuration (varies by distribution): ***/boot/grub/grub.cfg***
* GRUB Responsibilities:

&#x09;1. Displays the boot menu.

&#x09;2. Lets you choose the operating system.

&#x09;3. Loads the Linux kernel into memory.

&#x09;4. Loads initramfs.





***# initramfs:***

* It is a temporary root filesystem loaded into RAM during boot.
* Need: At this stage, the kernel may not yet have the drivers required to access the real root filesystem.
* Once the real root filesystem is mounted, initramfs is no longer needed.





***# What is the role of the kernel during boot?***

The kernel initializes the hardware, loads necessary drivers (directly or through initramfs), manages memory, and starts the first userspace process (systemd).



***# Why is systemd called PID 1?***

Because it is the first userspace process started by the kernel, and all other user processes are ultimately descendants of it.



***# How can you check which process is PID 1?***

ps -p 1



***# What command shows the kernel version?***

uname -r

