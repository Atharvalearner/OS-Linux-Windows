Active Directory is backed up by taking a ***System State backup of the Domain Controller*** using Windows Server Backup or the wbadmin command.



The System State includes the Active Directory database, SYSVOL, registry, boot files, and other critical components.



There are two types of Active Directory restore.



1. ***A Non-Authoritative Restore*** is the default method, where the restored Domain Controller synchronizes with other healthy Domain Controllers and receives the latest updates through replication. It is mainly used for server failures or hardware replacement.
2. ***An Authoritative Restore*** is used when Active Directory objects such as users, groups, or Organizational Units have been accidentally deleted and the deletion has already replicated to all Domain Controllers. In this case, the restored objects are marked as authoritative so they replicate to the other Domain Controllers and replace the deleted data.





| Topic                     | Remember This                                             |

| ------------------------- | ----------------------------------------------------------|

| AD Backup                 | System State Backup                                       |

| Tool                      | Windows Server Backup / `wbadmin`                         |

| Backup Includes           | NTDS.dit, SYSVOL, Registry, Boot Files, COM+              |

| Non-Authoritative Restore | Restore → Receive latest updates from other DCs           |

| Authoritative Restore     | Restore → Replicate restored data to other DCs            |

| Use Non-Authoritative     | DC failure, OS corruption, hardware replacement               |

| Use Authoritative         | Recover deleted users, OUs, groups, or GPOs after replication |

