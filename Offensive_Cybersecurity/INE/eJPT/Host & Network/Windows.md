#eJPT #INE #Windows 

*Microsoft Windows is the dominant operating system worldwide with a market share >=70% as of 2021.*

# Common Windows Vulnerabilities

● **Information disclosure** - Vulnerability that allows an attacker to access confidential data.
● **Buffer overflows** - Caused by a programming error, allows attackers to write data to a buffer and overrun the allocated buffer, consequently writing data to allocated memory addresses.
● **Remote code execution** - Vulnerability that allows an attacker to remotely execute code on the target system.
● **Privilege escalation** - Vulnerability that allows an attacker to elevate their privileges after initial compromise.
● **Denial of Service (DOS)** - Vulnerability that allows an attacker to consume a system/host’s resources (CPU, RAM, Network etc) consequently preventing the system from functioning normally.

# Frequently Exploited Services

![[Frequently Exploited Windows Services.png]]

# Microsoft IIS

*IIS can be used to host both static and dynamic web pages developed in ASP.NET and PHP.*

- Typically configured to run on **ports 80/443**.
- Supported executable file extensions:
	+ .asp
	+ .aspx
	+ .config
	+ .php

# WebDAV

*WebDAV essentially enables a web server to function as a file server for collaborative authoring.*
- WebDAV runs on top Microsoft IIS on **ports 80/443.**
- In order to connect to a WebDAV server, you will need to <u>provide legitimate credentials</u>. This is because WebDAV implements authentication in the form of a username and password

davtest - Used to scan, authenticate and exploit a WebDAV server.
+ Pre-installed on most offensive penetration testing distributions like Kali
and Parrot OS.
● cadaver - cadaver supports file upload, download, on-screen display, in-
place editing, namespace operations (move/copy), collection creation and
deletion, property manipulation, and resource locking on WebDAV servers.
+ Pre-installed on most offensive penetration testing distributions like Kali
and Parrot OS