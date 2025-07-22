
| icacls                                         | Modify or see DACL of file                               |
| ---------------------------------------------- | -------------------------------------------------------- |
| **net user**                                   | **See all users of machine**                             |
| **wmic** ```product get name,version,vendor``` | **dump information it can gather on installed software** |
| **systeminfo**                                 | **get system info, can be used with tools**              |

---
# Dangerous Privileges

## SeBackup / SeRestore

- check perms
- backup the SAM and SYSTEM hashes
	- _reg save hklm\\system C:\\Users\\THMBackup\\system.hive_
	- _reg save hklm\\sam C:\\Users\\THMBackup\\sam.hive_
- Get hashes on attacking machine
- Use impacket to retrieve the users' password hashes
- Perform a Pass-the-Hash attack
## SeTakeOwnership

- Taking ownership of objects on system ( EX : utilman.exe)
	- _takeown /f C:\\Windows\\System32\\Utilman.exe_
- copy cmd.exe to Utilman.exe
	- copy cmd.exe utilman.exe
- Launch utilman from lock screen
## SeImpersonate / SeAssignPrimaryToken

- allow a process to impersonate other users and act on their behalf
- Export RogueWinRM to target
- Start listener on host
-  spawn shell using BITS service
---
# Unpached Software

- Check info with most installed software using  **wmic** 
---
# Tools

[[Windows Shell - Misconfiguration Tools|Related Tools]]