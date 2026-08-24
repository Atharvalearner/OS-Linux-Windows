| Path                                  | Purpose                                            |
| ------------------------------------- | -------------------------------------------------- |
| C:\Windows                            | Main Windows OS files                              |
| C:\Windows\System32                   | Core Windows system components                     |
| C:\Windows\System32\drivers           | Device-driver files                                |
| C:\Windows\System32\drivers\etc\hosts | Local hostname-to-IP mappings                      |
| C:\Windows\System32\winevt\Logs       | Windows Event Logs                                 |
| C:\Windows\System32\config            | System Registry hives                              |
| C:\Windows\System32\config\SAM        | Local account/security database                    |
| C:\Windows\System32\inetsrv\config    | IIS configuration                                  |
| C:\Windows\SoftwareDistribution       | Windows Update data                                |
| C:\Windows\Prefetch                   | Application startup optimization/forensic evidence |
| C:\Windows\Minidump                   | Small crash dump files                             |
| C:\Windows\SysWOW64                   | 32-bit Windows system components on 64-bit Windows |
| C:\Users                              | User profiles                                      |
| C:\Users\<user>\AppData               | User application data                              |
| C:\Users\<user>\NTUSER.DAT            | User Registry hive stores User data  password hash |
| C:\Users\<user>\AppData\Local\Temp    | User temporary files                               |
| C:\Windows\Temp                       | System temporary files                             |
| C:\Program Files                      | Usually 64-bit applications                        |
| C:\Program Files (x86)                | Usually 32-bit applications                        |
| C:\Boot\BCD                           | Common legacy/BIOS BCD location                    |
| C:\Windows\NTDS\ntds.dit              | Active Directory database on Domain Controllers    |
| C:\Windows\SYSVOL                     | Group Policy/scripts/domain files                  |
| C:\inetpub\wwwroot                    | Default IIS web root                               |
| C:\inetpub\logs\LogFiles              | IIS logs                                           |


# Windows Core & System Directories
 1. Windows System Directory
 C:\Windows
 Contains the main Windows operating-system files and directories.

2. System32
C:\Windows\System32
Contains important Windows system components, including:
- System executables (.exe)
- DLL files
- Administrative utilities
- System configuration tools
- System components and libraries
- Device-driver components

Examples:
C:\Windows\System32\cmd.exe
C:\Windows\System32\services.exe
C:\Windows\System32\WindowsPowerShell\
C:\Windows\System32\drivers\

Important: On 64-bit Windows, System32 normally contains the 64-bit system components, despite the name "32".


3. Drivers
C:\Windows\System32\drivers
Contains Windows device-driver files, commonly with the .sys extension.
A device driver is software that allows the operating system to communicate with hardware devices.

Examples of hardware requiring drivers:
- Network adapters
- Storage controllers
- Graphics devices
- USB devices
- Audio devices


4. Users Directory
C:\Users
Contains profiles for local and domain users.

Example:
C:\Users\Shambhu\
├── Desktop
├── Documents
├── AppData
└── NTUSER.DAT

Each user generally has a separate profile containing their personal files, settings, and application data.


5. AppData
C:\Users\<username>\AppData
A hidden directory containing application-specific user data and configuration.
It contains three important directories:

- Local: C:\Users\<username>\AppData\Local
Contains application data that is generally machine-specific.
Examples: Local application caches, Temporary application data, Machine-specific settings

- Roaming
C:\Users\<username>\AppData\Roaming
Contains user-specific application settings/data that can potentially roam with a domain user profile in environments configured for roaming profiles.

- LocalLow
C:\Users\<username>\AppData\LocalLow

Used by applications running with lower integrity levels, such as certain sandboxed or restricted applications.


6. Program Files
C:\Program Files
On 64-bit Windows, this is normally the default installation directory for 64-bit applications.

Examples:
C:\Program Files\
├── Google\
├── Microsoft Office\
├── Java\
└── ApplicationName\


7. Program Files (x86)
C:\Program Files (x86)
On 64-bit Windows, this is normally used for 32-bit applications.

Simple comparison
C:\Program Files
        ↓
Usually 64-bit applications

C:\Program Files (x86)
        ↓
Usually 32-bit applications


8. Temporary Files
Windows has system-wide and user-specific temporary directories.

System Temp: C:\Windows\Temp
Contains temporary files created by the Windows operating system and services.

User Temp: C:\Users\<username>\AppData\Local\Temp
Contains temporary files created by applications and the current user.


9. Windows Registry Files
C:\Windows\System32\config
Contains important system Registry hive files.

Important files include: SYSTEM, SOFTWARE, SAM, SECURITY
These files contain configuration information used by Windows.


10. SAM File
C:\Windows\System32\config\SAM
SAM = Security Account Manager
The SAM database stores information about local Windows user accounts, including password-related data such as password hashes.

Important: SAM is primarily associated with local accounts. Domain account information is maintained in Active Directory on Domain Controllers.


11. Windows User Registry Hive
C:\Users\<username>\NTUSER.DAT
NTUSER.DAT contains the Registry hive for an individual user.

It stores user-specific information such as:
- User preferences
- Desktop settings
- Application settings
- User-specific configuration

It is associated with the user's HKCU (HKEY_CURRENT_USER) Registry hive when the user is logged in.


12. Hosts File
C:\Windows\System32\drivers\etc\hosts
The hosts file provides local hostname-to-IP address mappings.
Example: 192.168.1.10    server1.company.local
It can be used to resolve a hostname locally without relying on DNS.

Interview point: A hosts-file entry can take precedence over normal DNS resolution, depending on the Windows name-resolution process.



13. Boot Configuration
Windows boot configuration is stored in the BCD (Boot Configuration Data) store.
BIOS/legacy systems A common location is: C:\Boot\BCD
On modern UEFI systems, the BCD is typically stored on the EFI System Partition (ESP) rather than necessarily being accessible as C:\Boot\BCD.

BCD contains information used by Windows Boot Manager to determine how Windows should boot.


14. IIS — Internet Information Services
If IIS is installed, important directories include:

Default Web Root - C:\inetpub\wwwroot
This is commonly the default directory for hosting website files.

IIS Configuration - C:\Windows\System32\inetsrv\config
An important configuration file is - applicationHost.config

IIS Logs - C:\inetpub\logs\LogFiles
Contains IIS web-server logs such as HTTP requests and related information.



15. Active Directory Database
C:\Windows\NTDS\ntds.dit Present on a Domain Controller.
ntds.dit is the main Active Directory database.

It contains directory information about objects such as:
- Users
- Groups
- Computers
- Organizational Units (OUs)
- Other Active Directory objects

Related directory: C:\Windows\NTDS
> Important: ntds.dit is found on Domain Controllers, not on ordinary domain-joined client computers.


16. SYSVOL
C:\Windows\SYSVOL
Present on a Domain Controller.

SYSVOL stores domain-wide files such as:
- Group Policy files
- Logon scripts
- Other domain-related files
- Replicated domain files

Very Important Relationship
NTDS.dit
    ↓
Active Directory database
    ↓
Users, Groups, Computers, OUs, etc.

SYSVOL
    ↓
Group Policy + Scripts + Domain-related files


For interviews, remember:
> NTDS.dit = Active Directory database
> SYSVOL = Group Policy and domain-related files/scripts



17. Windows Update
C:\Windows\SoftwareDistribution

Contains Windows Update-related data, including:
- Downloaded update packages
- Update cache
- Update-related metadata/history

Windows uses this directory as part of its Windows Update process.


18. Windows Prefetch
C:\Windows\Prefetch

Contains Windows Prefetch files.
Prefetch is used by Windows to help optimize application startup by recording information about application execution and files needed during startup.

It is also useful in Windows digital forensics because Prefetch can provide evidence that an application was executed.


19. Windows PowerShell
C:\Windows\System32\WindowsPowerShell
Contains components associated with the Windows PowerShell installation.

PowerShell provides a command-line shell and scripting environment used for:
- System administration
- Automation
- Configuration
- Troubleshooting
- Windows management


20. Windows Event Logs:
C:\Windows\System32\winevt\Logs
Contains Windows Event Log files, normally using the .evtx format.
Examples of important logs include: Application.evtx, Security.evtx, System.evtx

These logs are useful for:
- Troubleshooting
- Security monitoring
- Incident response
- Forensics
- Auditing


21. Windows Minidump
C:\Windows\Minidump
Contains small memory dump files generated after certain system crashes, such as Blue Screen of Death (BSOD) events.
These files can be analyzed to help identify the cause of a crash.

22. What Does 32-bit and 64-bit Actually Mean?
The terms 32-bit and 64-bit primarily refer to the architecture and capabilities of the processor/software environment, including the size of addresses that a program can work with.

A major practical difference is the amount of memory an application can address.
32-bit Application:
- Designed for a 32-bit architecture/environment
- Has a much smaller address space
- Can run on a 32-bit Windows OS
- Usually runs on 64-bit Windows through WOW64
- Common in older applications

64-bit Application:
- Designed for a 64-bit architecture/environment
- Can address a much larger memory space
- Requires a 64-bit operating system
- Runs natively on 64-bit Windows
- Common in modern applications


23. What is WOW64?
WOW64 = Windows 32-bit on Windows 64-bit

It is the Windows compatibility technology that allows 32-bit applications to run on 64-bit Windows.

64-bit Windows
       │
       ├── 64-bit applications
       │       ↓
       │   Run natively
       │
       └── 32-bit applications
               ↓
             WOW64
               ↓
       Run on 64-bit Windows


24. System32 vs SysWOW64
On 64-bit Windows:
C:\Windows\System32
        ↓
64-bit Windows system components

C:\Windows\SysWOW64
        ↓
32-bit Windows system components


The names are confusing because System32 sounds like it should contain 32-bit files, but on 64-bit Windows, it normally contains the 64-bit system files.

SysWOW64 contains the 32-bit system components used by 32-bit applications.


25. Program Files vs Program Files (x86)
On a 64-bit Windows installation:

                 64-bit Windows
                       │
             ┌─────────┴─────────┐
             │                   │
        System Files        Applications
             │                   │
       ┌─────┴─────┐       ┌─────┴──────────┐
       │           │       │                │
   System32    SysWOW64  Program Files  Program Files(x86)
       │           │       |                |
       │           │	   |		    |
    64-bit       32-bit   64-bit     	 32-bit
    system       system   apps       	  apps
    files        files


| Directory              | On 64-bit Windows                |
| ---------------------- | -------------------------------- |
| C:\Windows\System32    | 64-bit Windows system components |
| C:\Windows\SysWOW64    | 32-bit Windows system components |
| C:\Program Files       | Usually 64-bit applications      |
| C:\Program Files (x86) | Usually 32-bit applications      |


| 32-bit Application                           | 64-bit Application               |
| -------------------------------------------- | -------------------------------- |
| Designed for 32-bit architecture             | Designed for 64-bit architecture |
| Smaller address space                        | Much larger address space        |
| Can run on 32-bit Windows                    | Requires 64-bit Windows          |
| Usually runs through WOW64 on 64-bit Windows | Runs natively on 64-bit Windows  |
| Common in older software                     | Common in modern software        |