***# FSMO (Flexible Single Master Operations):***

Although Active Directory uses multi-master replication (All changes are replicated between more than one Domain Controller), certain critical operations are handled by only one Domain Controller at a time to prevent conflicts. These special responsibilities are called FSMO roles.



**There are five FSMO roles:** 

1. Schema Master
2. Domain Naming Master
3. RID(Relative Indexer) Master
4. PDC(Password changes) Emulator 
5. and Infrastructure Master



The Schema Master manages schema changes, the Domain Naming Master manages domains in the forest, the RID Master allocates RID pools, the PDC Emulator handles password changes, account lockouts, and time synchronization, and the Infrastructure Master updates cross-domain object references.



FSMO roles can be transferred during planned maintenance when both Domain Controllers are healthy. If the current role holder has permanently failed and cannot be recovered, the role is seized and forcefully assigned to another Domain Controller. Seizing is an emergency operation and should only be used as a last resort.



**# One-line version:**

FSMO roles are five ***special AD responsibilities assigned to specific Domain Controllers*** to handle operations that shouldn't be performed concurrently by multiple DCs.



| Role                  | Easy Way to Remember                       |

| --------------------- | ------------------------------------------ |

| Schema Master         | Control Changes structure of AD. 	     |

| Domain Naming Master  | Controls changes to the domain namespace.  |

| RID Master            | Gives unique IDs to users and groups.      |

| PDC Emulator          | Handles passwords, time, and logon issues. |

| Infrastructure Master | Keeps cross-domain references updated.     |

