#eJPT #INE #Windows #PrivEsc


| COMMAND   | FUNCTION                        |
| --------- | ------------------------------- |
| *getpriv* | Show priviledge of current user |
| *getuid*  | Show username                   |
| net users | show user accounts              |

# Windows Kernel

*A Kernel is a computer program that is the core of an operating system and has complete control over every resource and hardware on a system. It acts as a translation layer between hardware and software and facilitates the communication between these two layers.*

**Windows NT is the kernel** that comes pre-packaged with all versions of Microsoft Windows

Two main modes of operation that determine access to system resources and hardware:
- **User Mode** – Programs and services running in user mode have limited access to system resources and functionality.
- **Kernel Mode** – Kernel mode has unrestricted access to system resources and functionality with the added functionality of managing devices and system memory.

#### (TOOL) Windows-Exploit-Suggester 
- This tool compares a targets patch levels against the Microsoft vulnerability database in order to detect potential missing patches on the target. It also notifies the user if there are public exploits and Metasploit modules available for the missing bulletins.
+ GitHub: https://github.com/AonCyberLabs/Windows-Exploit-Suggester

#### Finding correct exploits with metasploit
1. Get a meterpreter session on target 
2. run `post/muti/recon/local_exploit_suggester`

---
# User Account Control (UAC)

*User Account Control (UAC) is a Windows security feature introduced in Windows Vista that is used to prevent unauthorized changes from being made to the operating system.*

A **non-privileged user attempting to execute a program with elevated privileges will be prompted with the UAC credential prompt**, whereas a **privileged user will be prompted with a consent prompt**
## Bypassing UAC

*In order to successfully bypass UAC, we will need to have access to a user account that is a part of the local administrators group on the Windows target system.*
#### (TOOL) UACMe 
- It is an open source, robust privilege escalation tool developed by @hfire0x. It can be used to bypass Windows UAC by leveraging various techniques.
- GitHub: https://github.com/hfiref0x/UACME