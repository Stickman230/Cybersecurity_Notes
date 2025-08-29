#eJPT #INE #ShellShock

# What is ShellShock

Shellshock (CVE-2014-6271) is the name given to a family of **vulnerabilities in the Bash shell** (since V1.3) that *allow an attacker to execute remote arbitrary commands via Bash*, consequently allowing the attacker to obtain remote access to the target system via a reverse shell.

● The Shellshock vulnerability was *discovered by Stéphane Chazelas on the 12th of September 2014* and was made **public on the 24th of September 2014.**

● Bash is a \*Nix shell that is part of the GNU project and is the **default** shell for most Linux distributions.

**This vulnerability only affects Linux**

● In the context of remote exploitation, Apache web servers configured to run \*CGI scripts or .sh scripts are also vulnerable to this attack.

# Shellshock Exploitation

Caused by a vulnerability in Bash, whereby *Bash mistakenly executes trailing commands after a series of characters*: () {:;};.

● In order to exploit this vulnerability, you will need to locate an input vector or script that allows you to communicate with Bash.

● In the context of an Apache web server, we can utilize any legitimate CGI scripts accessible on the web server.

● Whenever a CGI script is executed, the web server will initiate a new process and run the CGI script with Bash.

● This vulnerability can be exploited both manually and automatically with the use of an MSF exploit module.


---
#### Definitions

- *Nix* : Unix Based operating system
- *CGI (Common Gateway Interface)* :  Scripts used by Apache to execute arbitrary commands on the Linux system, after which the output is displayed to the client.