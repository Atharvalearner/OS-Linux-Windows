NTFS journaling is a filesystem recovery mechanism that records important metadata transactions in the NTFS $LogFile. If the system crashes or loses power during a filesystem operation, NTFS uses this journal during recovery to complete or roll back incomplete transactions and bring the filesystem back to a consistent state. It improves filesystem reliability.



**# Simple Example**

Suppose Windows is writing a file:



*Application*

&#x20;   *↓*

*NTFS starts file operation*

&#x20;   *↓*

*Journal records the required metadata changes*

&#x20;   *↓*

*NTFS performs the actual changes*



If the computer suddenly loses power during the operation, NTFS can use the journal during the next boot to determine what filesystem metadata operations were incomplete and bring the filesystem back to a consistent state.



**# With NTFS journaling:**

*Power Failure*

&#x20;    *↓*

*NTFS checks journal*

&#x20;    *↓*

*Identifies incomplete transactions*

&#x20;    *↓*

*Recovers filesystem metadata*

&#x20;    *↓*

*Filesystem becomes consistent*





