***# What is the "s" Permission Bit?***

The `s` permission indicates a special permission bit.

It can represent: SUID (Set User ID), SGID (Set Group ID)

The meaning depends on where the `s` appears.



***1. SUID (Set User ID)***

* SUID is a special permission 
* that allows a program to run with the permissions of the file owner instead of the user who executes it.
* ***Setting SUID:*** chmod u+s filename
* ***Remove SUID :*** chmod u-s filename



* Example: 

Owner : root

File : /etc/passwd

Permissions: -rwsr-xr-x



Notice: rws instead of rwx

The `s` replaces the owner's execute (`x`) permission, indicating SUID.



When Any Other User than Root executes this file: /etc/passwd

The program runs with root's privileges.

Otherwise, Non-root user could never update: /etc/shadow



***# Common Commands with SUID***

**Check SUID files:** find / -perm -4000

output:

&#x09;/usr/bin/passwd

&#x09;/usr/bin/su

&#x09;/usr/bin/sudo





**2. SGID (Set Group ID)**

* It allows a program to run with the permissions of the file's group instead of the user's group. 
* On directories, it causes new files and subdirectories to inherit the directory's group ownership.
* **Set SGID:** chmod g+s directory



Example:

Permissions: -rwxr-sr-x

Notice: The `s` replaces the group's execute (`x`) permission.



Suppose: 

Owner : root

Group : developers



When a user runs the program, the program runs using the: developers group.

Example (Directory): /project belongs to Group = developers

Enable SGID**:** chmod g+s /project

Now every new file created inside /project automatically belongs to developers instead of the creator's default group.

This is extremely useful for shared project directories.





| Feature     | SUID                          | SGID                          |

| ----------- | ----------------------------- | ----------------------------- |

| Works on    | Files (commonly)              | Files and directories         |

| Executes as | File owner                    | File group                    |

| Symbol      | `s` in owner execute position | `s` in group execute position |

| Example     | `passwd`                      | Shared project directory      |







***# Sticky Bit:***

* A special permission on directories that allows users to delete or rename only the files they own, even if the directory is writable by everyone.
* It mainly used in shared directories, where multiple resources are stored.



Example: 

Everyone has: Read, Write, Execute

Without the Sticky Bit, Bob can delete Alice's file, Charlie can delete Bob's file, Anyone can delete anyone's files, This is dangerous.



With Sticky Bit:

Permissions become: drwxrwxrwt		... t: sticky bit



Only the file owner, the directory owner, or root can delete it.



* **Setting Sticky Bit:** chmod +t directory
* **Remove Sticky Bit :** chmod -t /shared





**| ---------- | ---------------------------- | --------------------- | ---------------------------------------------------------- |**

**| Permission | Symbol                       | Used On               | Purpose                                                    |**

**| ---------- | ---------------------------- | --------------------- | ---------------------------------------------------------- |**

| SUID       | `s` (owner execute position) | Mainly files          | Run with the file owner's privileges                       |

| SGID       | `s` (group execute position) | Files and directories | Run with the file's group or inherit the directory's group |

| Sticky Bit | `t`                          | Directories           | Prevent users from deleting others' files                  |

**| ---------- | ---------------------------- | --------------------- | ---------------------------------------------------------- |**



**# Numeric Values:**

Linux uses numeric values for these special permissions:



| Permission | Value |

| ---------- | ----: |

| SUID       |     4 |

| SGID       |     2 |

| Sticky Bit |     1 |



Example:

chmod 4755 file 		..  `4` → SUID,  `755` → Regular permissions

chmod 2755 directory		..  `2` → SGID, 

chmod 1777 /shared		..  `1` → Sticky Bit, `777` → Full permissions







***Q1. Why does `passwd` have SUID?***

Because changing a password requires updating `/etc/shadow`, which is writable only by root. The SUID bit lets the `passwd` program run with the file owner's (root's) privileges while it executes.



***Q2. Why is the Sticky Bit used on `/tmp`?***

Because `/tmp` is writable by all users. The Sticky Bit prevents one user from deleting or renaming another user's temporary files.



**# Interview Summary (Remember This)**

| ------------------- | ---------------------------------------------------------------------------------------- |

| Question            | Best Answer                                                                              |

| ------------------- | ---------------------------------------------------------------------------------------- |

| What is `s`?        | A special permission indicating SUID or SGID, depending on where it appears.             |

| What is SUID?       | Runs an executable with the file owner's permissions.                                    |

| Example             | `passwd`                                                                                 |

| What is SGID?       | Runs with the file's group permissions or makes new files inherit the directory's group. |

| What is Sticky Bit? | Prevents users from deleting or renaming files they don't own in a shared directory.     |

| Best example        | `/tmp`                                                                                   |

| Symbol              | `t`                                                                                      |

| Commands            | `chmod u+s`, `chmod g+s`, `chmod +t`                                                     |

| ------------------- | ---------------------------------------------------------------------------------------- |





**# Easy Memory Trick**

SUID = "Owner's identity" → The program temporarily acts as the owner.

SGID = "Group identity" → The program or new files use the group's identity.

Sticky Bit = "Don't touch others' files" → In a shared directory, users can create files, but they can't delete or rename files owned by someone else.

