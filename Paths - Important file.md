\# etc - System-wide configuration files.

| Path                 | Description                                                                                                     |

| -------------------- | --------------------------------------------------------------------------------------------------------------- |

| /etc/passwd          | User account information such as username, UID, GID, home directory, and shell.                                 |

| /etc/shadow          | Password hashes and password-aging information.                                                                 |

| /etc/group           | Group information and group memberships.                                                                        |

| /etc/gshadow         | Secure group-account information.                                                                               |

| /etc/hostname        | System hostname.                                                                                                |

| /etc/hosts           | Local hostname-to-IP mappings.                                                                                  |

| /etc/resolv.conf     | DNS resolver configuration.                                                                                     |

| /etc/fstab           | Defines filesystems that should be mounted automatically.                                                       |

| /etc/mtab            | Historically represented currently mounted filesystems; commonly a symlink to /proc/mounts on modern systems. |

| /etc/sudoers         | Defines sudo privileges.                                                                                        |

| /etc/sudoers.d/      | Additional sudo configuration files.                                                                            |

| /etc/ssh/sshd\_config | SSH server configuration.                                                                                       |

| /etc/ssh/ssh\_config  | SSH client configuration.                                                                                       |

| /etc/ssh/            | SSH keys and configuration files.                                                                               |

| /etc/cron\*           | Cron-related configuration directories/files.                                                                   |

| /etc/crontab         | System-wide cron configuration.                                                                                 |

| /etc/systemd/        | Systemd configuration and unit-related files.                                                                   |

| /etc/default/        | Default configuration used by various services.                                                                 |

| /etc/profile         | System-wide shell environment configuration for login shells.                                                   |

| /etc/bash.bashrc     | System-wide Bash configuration on Debian/Ubuntu systems.                                                        |

| /etc/shells          | Lists valid login shells.                                                                                       |

| /etc/security/       | Security-related configuration, including PAM-related settings.                                                 |

| /etc/pam.d/          | PAM authentication configuration.                                                                               |

| /etc/nsswitch.conf   | Controls how Linux looks up users, groups, hosts, and other information.                                        |

| /etc/services        | Maps service names to port numbers/protocols.                                                                   |

| /etc/protocols       | Lists protocol names and protocol numbers.                                                                      |

| /etc/hosts.allow     | TCP Wrappers configuration on systems that support it.                                                          |

| /etc/hosts.deny      | TCP Wrappers configuration on systems that support it.                                                          |





2\. var — Logs, Application Data, Cache

| Path              | Description                                                                                               |

| ----------------- | --------------------------------------------------------------------------------------------------------- |

| /var/log/         | Main location for system and application logs.                                                            |

| /var/log/auth.log | Authentication-related logs on Debian/Ubuntu.                                                             |

| /var/log/secure   | Authentication/security logs on RHEL/Rocky.                                                               |

| /var/log/syslog   | General system log on Debian/Ubuntu.                                                                      |

| /var/log/messages | General system messages on RHEL/Rocky.                                                                    |

| /var/log/kern.log | Kernel-related logs on systems that maintain this file.                                                   |

| /var/log/dmesg    | Kernel messages on some distributions; dmesg is generally preferred for viewing the kernel ring buffer. |

| /var/log/journal/ | Persistent systemd journal storage when persistent journaling is enabled.                                 |

| /var/log/cron     | Cron-related logs on many RHEL-based systems.                                                             |

| /var/log/boot.log | Boot-related service messages on some distributions.                                                      |

| /var/log/lastlog  | Binary database containing information about users' last login.                                           |

| /var/log/wtmp     | Login/logout history database. Viewed using last.                                                       |

| /var/log/btmp     | Failed login attempts. Viewed using lastb.                                                              |

| /var/lib/         | Persistent variable application/service data.                                                             |

| /var/cache/       | Cached application/package data.                                                                          |

| /var/spool/       | Queued data, such as mail and print jobs.                                                                 |

| /var/tmp/         | Temporary files intended to survive longer than /tmp.                                                   |

| /var/www/html/    | Common Apache web root on Linux systems.                                                                  |





3\. home and User-Related Paths

| Path                            | Description                                                                    |

| ------------------------------- | ------------------------------------------------------------------------------ |

| /home/                          | Contains normal users' home directories.                                       |

| /home/user/                     | Individual user's home directory.                                              |

| /home/user/.bashrc              | Bash configuration for interactive non-login shells.                           |

| /home/user/.bash\_profile        | User-specific login-shell configuration, commonly on RHEL-based systems.       |

| /home/user/.profile             | User-specific login environment configuration, commonly used on Debian/Ubuntu. |

| /home/user/.ssh/                | User's SSH configuration and keys.                                             |

| /home/user/.ssh/authorized\_keys | Public keys allowed for SSH key-based login to that user's account.            |

| /root/                          | Root user's home directory.                                                    |

| /root/.ssh/                     | Root user's SSH configuration and keys.                                        |





4\. boot — Linux Boot Files

| Path              | Description                                            |

| ----------------- | ------------------------------------------------------ |

| /boot/            | Contains files required for booting Linux.             |

| /boot/vmlinuz-\*   | Compressed Linux kernel image.                         |

| /boot/initramfs-\* | Initial RAM filesystem image.                          |

| /boot/grub/       | GRUB files on many Debian/Ubuntu systems.              |

| /boot/grub2/      | GRUB-related files on many RHEL-based systems.         |

| /boot/efi/        | EFI System Partition mount point on many UEFI systems. |





5\. dev — Device Files

| Path           | Description                                                          |

| -------------- | -------------------------------------------------------------------- |

| /dev/          | Contains device files.                                               |

| /dev/sda       | Common name for the first SCSI/SATA disk.                            |

| /dev/sda1      | First partition of /dev/sda.                                       |

| /dev/sdb       | Common name for another disk.                                        |

| /dev/nvme0n1   | Common name for the first NVMe disk.                                 |

| /dev/nvme0n1p1 | First partition of the NVMe disk.                                    |

| /dev/null      | Discards anything written to it.                                     |

| /dev/zero      | Produces zero bytes when read.                                       |

| /dev/random    | Provides random data from the kernel's random subsystem.             |

| /dev/urandom   | Provides pseudorandom data suitable for most applications.           |

| /dev/tty       | Represents the current terminal.                                     |

| /dev/pts/      | Pseudo-terminal devices, commonly used by terminal sessions and SSH. |





6\. proc — Processes and Kernel Information

| Path             | Description                                      |

| ---------------- | ------------------------------------------------ |

| /proc/           | Kernel and process information.                  |

| /proc/1/         | Information about PID 1.                         |

| /proc/<PID>/     | Information about a particular process.          |

| /proc/cpuinfo    | CPU information.                                 |

| /proc/meminfo    | Memory information.                              |

| /proc/version    | Kernel version/build information.                |

| /proc/uptime     | System uptime information.                       |

| /proc/loadavg    | System load information.                         |

| /proc/mounts     | Information about mounted filesystems.           |

| /proc/partitions | Information about detected disk partitions.      |

| /proc/cmdline    | Kernel command-line parameters used during boot. |

| /proc/sys/       | Tunable kernel parameters.                       |





7\. sys — Hardware, Devices and Kernel

| Path              | Description                                               |

| ----------------- | --------------------------------------------------------- |

| /sys/             | Kernel, hardware, and device information.                 |

| /sys/class/       | Device classes such as network devices and block devices. |

| /sys/devices/     | Hardware/device hierarchy.                                |

| /sys/block/       | Block devices such as disks.                              |

| /sys/class/net/   | Network interfaces.                                       |

| /sys/class/block/ | Block devices.                                            |





8\. usr — Applications and User-Space Files

| Path             | Description                                                                 |

| ---------------- | --------------------------------------------------------------------------- |

| /usr/bin/        | Most user commands and executable programs.                                 |

| /usr/sbin/       | System-administration commands.                                             |

| /usr/lib/        | Libraries used by applications.                                             |

| /usr/lib64/      | 64-bit libraries on systems that maintain this separate directory.          |

| /usr/share/      | Architecture-independent data such as documentation and localization files. |

| /usr/include/    | Header files used for software development.                                 |

| /usr/local/      | Software manually installed by the local administrator.                     |

| /usr/local/bin/  | Locally installed user commands.                                            |

| /usr/local/sbin/ | Locally installed administrative commands.                                  |





9\. usr — Applications and User-Space Files

| Path      | Description                                                            |

| --------- | ---------------------------------------------------------------------- |

| /tmp/     | Temporary files; often cleaned automatically.                          |

| /var/tmp/ | Temporary files that are generally intended to persist across reboots. |

| /mnt/     | Common temporary/manual filesystem mount point.                        |

| /media/   | Common mount location for removable media.                             |





10\. Important Network Configuration Paths

| Path                            | Description                                                                                                 |

| ------------------------------- | ----------------------------------------------------------------------------------------------------------- |

| /etc/hosts                      | Static/local hostname-to-IP mappings.                                                                       |

| /etc/hostname                   | System hostname.                                                                                            |

| /etc/resolv.conf                | DNS resolver configuration.                                                                                 |

| /etc/nsswitch.conf              | Defines lookup sources/order for users, groups, hosts, etc.                                                 |

| /etc/services                   | Service names and their port numbers.                                                                       |

| /etc/netplan/                   | Netplan configuration on Ubuntu systems using Netplan.                                                      |

| /etc/NetworkManager/            | NetworkManager configuration.                                                                               |

| /etc/sysconfig/network-scripts/ | Legacy RHEL/CentOS network configuration location; newer RHEL versions use NetworkManager/keyfiles instead. |

| /etc/systemd/network/           | systemd-networkd configuration.                                                                           |





11\. SSH Paths

| Path                   | Description                                              |

| ---------------------- | -------------------------------------------------------- |

| /etc/ssh/              | System-wide SSH configuration and host keys.             |

| /etc/ssh/sshd\_config   | SSH server configuration.                                |

| /etc/ssh/ssh\_config    | SSH client configuration.                                |

| \~/.ssh/                | Current user's SSH directory.                            |

| \~/.ssh/authorized\_keys | Public keys allowed to authenticate as that user.        |

| \~/.ssh/id\_rsa          | RSA private key, if generated using that algorithm.      |

| \~/.ssh/id\_ed25519      | Ed25519 private key, if generated using that algorithm.  |

| \~/.ssh/known\_hosts     | Host keys learned from previously contacted SSH servers. |





12\. Authentication and Security

| Path            | Description                                                           |

| --------------- | --------------------------------------------------------------------- |

| /etc/passwd     | User account information.                                             |

| /etc/shadow     | Password hashes and password-aging information.                       |

| /etc/group      | Group information.                                                    |

| /etc/gshadow    | Secure group information.                                             |

| /etc/sudoers    | sudo configuration.                                                   |

| /etc/sudoers.d/ | Additional sudo rules.                                                |

| /etc/pam.d/     | PAM authentication/service configuration.                             |

| /etc/security/  | Security-related configuration, including limits and access controls. |

| /etc/selinux/   | SELinux configuration on systems using SELinux.                       |





13\. Web Server Paths

| Path                          | Description                                                    |

| ----------------------------- | -------------------------------------------------------------- |

| /etc/httpd/                   | Apache configuration on RHEL/Rocky.                            |

| /etc/httpd/conf/httpd.conf    | Main Apache configuration on RHEL/Rocky.                       |

| /etc/apache2/                 | Apache configuration on Debian/Ubuntu.                         |

| /etc/apache2/apache2.conf     | Main Apache configuration on Debian/Ubuntu.                    |

| /etc/apache2/sites-available/ | Available Apache virtual-host configurations on Debian/Ubuntu. |

| /etc/apache2/sites-enabled/   | Enabled Apache virtual hosts, usually symlinks.                |

| /var/www/html/                | Common Apache web root.                                        |

| /var/log/apache2/             | Apache logs on Debian/Ubuntu.                                  |

| /var/log/httpd/               | Apache logs on RHEL/Rocky.                                     |



| Path                   | Description                           |

| ---------------------- | ------------------------------------- |

| /etc/nginx/            | Nginx configuration.                  |

| /etc/nginx/nginx.conf  | Main Nginx configuration.             |

| /etc/nginx/conf.d/     | Additional Nginx configuration files. |

| /usr/share/nginx/html/ | Common default Nginx web root.        |

| /var/log/nginx/        | Nginx access/error logs.              |





14\. FTP / NFS / Samba

| Path                    | Description                                        |

| ----------------------- | -------------------------------------------------- |

| /etc/vsftpd.conf        | vsftpd configuration on some Debian/Ubuntu setups. |

| /etc/vsftpd/vsftpd.conf | vsftpd configuration on RHEL/Rocky.                |

| /etc/exports            | NFS exported directories.                          |

| /etc/samba/             | Samba configuration directory.                     |

| /etc/samba/smb.conf     | Main Samba configuration.                          |

| /var/lib/samba/         | Samba state/database data.                         |





15\. DNS / DHCP

| Path                 | Description                                                   |

| -------------------- | ------------------------------------------------------------- |

| /etc/bind/           | BIND DNS configuration on Debian/Ubuntu.                      |

| /etc/bind/named.conf | Main BIND configuration on Debian/Ubuntu.                     |

| /var/cache/bind/     | Common BIND working/cache location on Debian/Ubuntu.          |

| /etc/named.conf      | Main BIND configuration on RHEL/Rocky.                        |

| /var/named/          | BIND zone files on RHEL/Rocky.                                |

| /etc/dhcp/dhcpd.conf | DHCP server configuration for ISC DHCP on many distributions. |





16\. Package Management

| Path                     | Description                                              |

| ------------------------ | -------------------------------------------------------- |

| /var/lib/dpkg/           | Debian package-management database.                      |

| /var/log/dpkg.log        | Debian package-management log.                           |

| /etc/apt/                | APT configuration on Debian/Ubuntu.                      |

| /etc/apt/sources.list    | APT repository configuration on systems using this file. |

| /etc/apt/sources.list.d/ | Additional APT repository configuration.                 |

| /var/cache/apt/          | Cached APT package data.                                 |

| /var/lib/rpm/            | RPM database on many RPM-based systems.                  |

| /etc/yum.repos.d/        | YUM/DNF repository configuration on RHEL-family systems. |

| /var/cache/dnf/          | DNF cache.                                               |





17\. Systemd

| Path                     | Description                                                       |

| ------------------------ | ----------------------------------------------------------------- |

| /etc/systemd/system/     | Locally created/administrator-managed systemd units.              |

| /usr/lib/systemd/system/ | Vendor/package-provided systemd units on many RHEL-based systems. |

| /lib/systemd/system/     | Systemd units on many Debian-based systems.                       |

| /run/systemd/system/     | Runtime-generated systemd units.                                  |





18\. Cron

| Path                      | Description                               |

| ------------------------- | ----------------------------------------- |

| /etc/crontab              | System-wide crontab.                      |

| /etc/cron.d/              | Additional system cron jobs.              |

| /etc/cron.daily/          | Daily jobs.                               |

| /etc/cron.hourly/         | Hourly jobs.                              |

| /etc/cron.weekly/         | Weekly jobs.                              |

| /etc/cron.monthly/        | Monthly jobs.                             |

| /var/spool/cron/          | User crontabs on many RHEL-based systems. |

| /var/spool/cron/crontabs/ | User crontabs on Debian/Ubuntu.           |



