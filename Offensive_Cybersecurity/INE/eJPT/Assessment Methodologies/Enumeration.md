#eJPT #INE #Enumeration #Metasploit


| COMAND    | FUNCTION        |
| --------- | --------------- |
| *curl* -I | Get the headers |

# What is Enumeration

After the host discovery and port scanning phase of a penetration test, the next logical phase is going to involve *service enumeration*.

- The goal of service enumeration is to **gather additional, more specific/detailed information about the hosts/systems** on a network and the services running on said hosts.
- This includes information like account names, shares, misconfigured services and so on.

---
# Importing Nmap Scan results to Metasploit

[[Import Nmap Results|See import nmap to metasploit cheat sheet]]

---
# Using Metasploit Auxiliary Modules

*Auxiliary modules are used to perform functionality like scanning, discovery and fuzzing.*
**Not exploitation**, information gathering only

+ We can use auxiliary modules to perform **both TCP & UDP port scanning as well as enumerating information** from services like FTP, SSH, HTTP...

[[Use Modules|See Cheat Sheet for using metasploit module for exploitation]]

[[Pivoting targets|See Cheat Sheet for using metasploit to pivot targets]]

Metasploit wordlists are in 
- /usr/share/metasploit-framework/data/wordlists/common_passwords.txt
- /usr/share/metasploit-framework/data/wordlists/unix_passwords.txt
- /usr/share/metasploit-framework/data/wordlists/common_users.txt
- /usr/share/metasploit-framework/data/wordlists/namelist.txt

---
# FTP

**FTP (File Transfer Protocol) is a protocol that uses TCP port 21** and is used to facilitate file sharing between a server and client/clients.

Metasploit modules:
- ftp_version
- ftp_login (bruteforce)

---
# SMB

*SMB (Server Message Block) is a network file sharing protocol* that is used to facilitate the sharing of files and peripherals between computers on a local network (LAN).
+ SMB uses **port 445 (TCP)**. However, originally, SMB ran on top of **NetBIOS using port 139**.

SAMBA is the Linux implementation of SMB, and allows Windows systems to access Linux shares and devices.

Metasploit modules:
- smb_enumusers
- smb_enumshares 
- smb_login

---
# WEB Servers

HTTP is an application layer protocol that utilizes TCP port 80 for communication or 443 for SSL confections (HTTPS).
+ Examples of popular web servers are : Apache, Nginx and Microsoft IIS.

Metasploit modules:

DISCOVERY
- auxiliary/scanner/http/http_version
- auxiliary/scanner/http/http_header

ENUM
- auxiliary/scanner/http/dir_scanner
- auxiliary/scanner/http/files_dir

BRUTEFORCE
- auxiliary/scanner/http/http_login
- auxiliary/scanner/http/apache_userdir_enum (**APACHE SPECIFIC**) 
---
# MYSQL

+ MySQL is an open-source relational database management system based on SQL (Structured Query Language).
+ *MySQL utilizes TCP port 3306* by default, **however, like any service it can be hosted on any open TCP port**.

Metasploit modules:

DETECTION
- auxiliary/scanner/mysql/mysql_version

BRUTEFORCE
- auxiliary/scanner/mysql/mysql_login

ENUMERATION
- auxiliary/admin/mysql/mysql_enum

- auxiliary/admin/mysql/mysql_sql
- auxiliary/scanner/mysql/mysql_file_enum
- auxiliary/scanner/mysql/mysql_hashdump
- auxiliary/scanner/mysql/mysql_schemadump
- auxiliary/scanner/mysql/mysql_writable_dirs