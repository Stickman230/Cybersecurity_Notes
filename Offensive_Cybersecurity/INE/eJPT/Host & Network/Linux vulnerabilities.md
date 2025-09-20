#eJPT #INE #Linux


| COMMAND        | FUNCTION                       |
| -------------- | ------------------------------ |
| *searchsploit* | Search the exploit DB database |

*Linux is a free and open source operating system that is comprised of the Linux kernel, which was developed by Linus Torvalds, and the GNU toolkit, which is a collection of software and utilities that was started and developed by Richard Stallman.*

---
# Frequently Exploited Services

![[Frequenty_exploited_linux_services.png]]

---
# FTP

*FTP (File Transfer Protocol) is a protocol that uses TCP port 21 and is used to facilitate file sharing between a server and client/clients*

- FTP authentication requires a username and password combination (except anonymous)

#### Exploiting using Hydra

1. Identify FTP and version
2. Run hydra `hydra -L /usr/share/metasploit-framework/data/wordlists/common_users.txt -P /usr/share/metasploit-framework/data/wordlists/unix_passwords.txt DOMAIN -t 4 ftp`
3. login `ftp IP`

---
# SSH

*SSH (Secure Shell) is a remote administration protocol that offers encryption and is the successor to Telnet.*

● SSH uses **TCP port 22 by default**, however, like other services, it can be configured to use any other open TCP port.

● SSH authentication can be configured in two ways:
- Username & password authentication
- Key based authentication
#### Exploiting using Hydra

1. Identify SSH and version
2. Run hydra `hydra -L /usr/share/metasploit-framework/data/wordlists/common_users.txt -P /usr/share/metasploit-framework/data/wordlists/unix_passwords.txt IP -t 4 ssh`
3. login `SSH USER@IP`

---

# SAMBA

*SMB (Server Message Block) is a network file sharing protocol that is used to facilitate the sharing of files and peripherals between computers on a local network (LAN).*

*SMB uses port 445 (TCP). However, originally, SMB ran on top of NetBIOS using port 139.*

- **Samba is the Linux implementation of SMB**, and allows Windows systems to access Linux shares and devices.
- SAMBA utilizes username and password authentication

After obtaining legitimate credentials, **we can use a utility called SMBMap** in order to enumerate SAMBA share drives, list the contents of the shares as well as download files and execute remote commands on the target.

● We can also utilize **a tool called smbclient.** smbclient is a client that is part of the SAMBA software suite. It communicates with a LAN Manager server, offering an interface similar to that of the ftp program. It can be used to download files from the server to the local machine, upload files from the local machine to the server as well as retrieve directory information from the server.

#### Exploiting using Hydra

1. Identify SAMBA and version
2. Run hydra `hydra -L /usr/share/metasploit-framework/data/wordlists/common_users.txt -P /usr/share/metasploit-framework/data/wordlists/unix_passwords.txt IP -t 4 smb`
3. Run `smbmap -H IP -u USER -p PASS`  or `smbclient -L 192.107.192.3 -U USER` to list out the shares
4. Then once you have identified a share : `smbclient //192.107.192.3/SHARE -U USER `
(you can also use `enum4linux -a -u USER -p PASS IP` to enumerate shares)