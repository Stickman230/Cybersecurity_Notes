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

4. Import Nmap/Nessus results
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

7. Analise results
```bash
msf> analyze
```

8. Check detected vulnerabilities
```bash
msf> vulns -p PORT
```