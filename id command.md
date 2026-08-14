***# id:*** 

Displays the user and group identity information of a user, such as the User ID (UID), Group ID (GID), and the groups to which the user belongs.



***# Example Output:***

uid=1000(shambhu) gid=1000(shambhu) groups=1000(shambhu),10(wheel),998(docker)



* here, in groups: shambhu is primary group and wheel, docker is supplementary group

wheel → Allows administrative privileges (on many RHEL-based systems)

docker → Allows the user to run Docker commands without sudo



***# User ID:***

| ------------------------------ | -------------------- |

| UID                            | Meaning              |

| ------------------------------ | -------------------- |

| 0                              | Root user            |

| 1–999 (varies by distribution) | System/Service users |

| 1000+                          | Regular users        |

| ------------------------------ | -------------------- |



***# gid (Primary Group ID):***

Every user has one primary group.



***# Commands:***

| ----------- | -------------------------------- |

| Command     | Purpose                          |

| ----------- | -------------------------------- |

| id          | Show UID, GID, and groups        |

| id username | Show identity of a specific user |

| id -u       | Show only the UID                |

| id -g       | Show only the primary GID        |

| id -G       | Show all group IDs               |

| id -un      | Show the username                |

| id -Gn      | Show group names                 |

| ----------- | -------------------------------- |



