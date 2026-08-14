File Server Resource Manager (FSRM) is a Windows Server role service used to manage and control storage on file servers. It allows administrators to configure storage quotas, block unwanted file types through file screening, generate storage usage reports, classify files, and automate file management tasks. For example, an administrator can limit users to a specific amount of storage, prevent media files from being stored on company file servers, and receive reports identifying the largest files or users consuming the most disk space. FSRM helps organizations manage storage efficiently, improve compliance, and prevent misuse of file server resources.



***In simple words:***

FSRM helps control what users can store on a file server, how much they can store, and provides reports about storage usage.



***# Real Company Example:***

Suppose your company has: 500 Employees, Shared File Server, 2 TB Storage



**The administrator configures:**

HR Folder: 		Hard quota: 100 GB

Finance Folder: 	Hard quota: 200 GB

Engineering Folder: 	Soft quota: 500 GB



File Screening: Block: .mp3, .mp4, .iso, .exe



Every Sunday: Generate reports showing: Largest files, Top users by storage, Duplicate files



This keeps the file server clean and prevents unnecessary storage usage.





***# What is the difference between a Hard Quota and a Soft Quota?***

Hard Quota: Prevents users from exceeding the storage limit.

Soft Quota: Allows users to exceed the limit but generates alerts and reports.



***# What is File Screening?***

It allows administrators to block or monitor specific file types, such as .mp3, .mp4, .exe, or .iso, on selected folders.



***# Can FSRM automatically send email alerts?***

Yes. FSRM can send email notifications, log events, run scripts, or execute commands when quota thresholds are reached or other configured events occur.



***# What kind of reports can FSRM generate?***

Large Files Report

Duplicate Files Report

Files by Owner

File Screening Audit Report

Quota Usage Report

