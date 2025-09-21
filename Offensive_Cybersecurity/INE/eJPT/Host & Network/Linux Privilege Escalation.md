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

---
# SUID Binaries

*In addition to the three main file access permissions (read, write and execute), Linux also provides users with specialized permissions that can be utilized in specific situations. One of these access permissions is the **SUID (Set Owner User ID)** permission*

- This permission **provides users with the ability to execute a script or binary with the permissions of the file owner** as opposed to the user that is running the script
- if improperly configured unprivileged users can exploit misconfigurations or vulnerabilities within the binary or script to obtain an elevated session.

#### Exploiting SUID Binaries

*The success of our attack will depend on the following factors*:
- Owner of the SUID binary – Given that we are attempting to elevate our privileges, we will only be exploiting SUID binaries that are owned by the “root” user or other privileged users.
- Access permissions – We will require executable permissions in order to execute the SUID binary.