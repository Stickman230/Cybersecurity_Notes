#eJPT #INE #Enumeration #Metasploit
# What is Enumeration

After the host discovery and port scanning phase of a penetration test, the next logical phase is going to involve *service enumeration*.

- The goal of service enumeration is to **gather additional, more specific/detailed information about the hosts/systems** on a network and the services running on said hosts.
- This includes information like account names, shares, misconfigured services and so on.

# Importing Nmap Scan results to Metasploit

1. Start The PostgreSQL DB 
```bash
service postgresql start
```

2. Check status of DB
```bash
msf> db_status
```

3. Create Workspace to organize results
```
msf> workspace -a NAME
```

4. Import Nmap results
```bash
msf> db_import PATH_TO_RESULTS
```

5. Confirm import 
```bash
msf> hosts or services
```

6. Launch Nmap scan from metasploit
```bash
msf> db_nmap NMAP_SCAN_OPTIONS
```

# Using Metasploit Auxiliary Modules

*Auxiliary modules are used to perform functionality like scanning, discovery and fuzzing.*
**Not exploitation**, information gathering only

+ We can use auxiliary modules to perform **both TCP & UDP port scanning as well as enumerating information** from services like FTP, SSH, HTTP...