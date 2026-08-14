journalctl is used to view systemd service logs, while dmesg is used to check kernel-level logs such as hardware and boot messages.





**# How to check system logs:**



1. **journalctl**: Used to view logs from system (Main/All Process Parent) services



Commands:

* journalctl                .. # all logs
* journalctl -xe            .. # recent errors
* journalctl -u ssh         .. # logs for specific service
* journalctl -f             .. # real-time logs





**2. dmesg:** Shows kernel logs (boot + hardware messages)



Commands:

dmesg

dmesg | less

dmesg | grep error

