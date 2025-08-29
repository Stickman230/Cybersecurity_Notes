1. Search for corresponding module
```bash
msf> search MODULE
msf> search type:TYPE name:MODULE_NAME cve:CVE_NUM
```

2. Use chosen module
```bash
msf> use MODULE_PATH
```

3. Show module options
```bash
msf> show options
msf> info  # Show full details
```

4. Set module options
```bash
msf> set OPTION_NAME VALUE     # SET MODULE OPTION
msf> setg OPTION_NAME VALUE    # SET GLOBAL OPTION

msf> unset OPTION_NAME VALUE     # UNSET MODULE OPTION
```

5. Run the module
```bash
msf> run or exploit
```

6. Check if session created and info about victim
```bash
meterpreter> sysinfo
```

7. Upload local file to remote host
```bash
meterpreter> upload LOCAL_PATH REMOTE_PATH # You can upload
```

8. Spawn shell session so we get usual commands
```bash
meterpreter> shell   # Spawn normal shell
meterpreter> /bin/bash -i # Convert to interactive bash session
```

9. Background session if needed
```bash
meterpreter> background
```

10. Check active sessions, or rejoin session
```bash
msf> sessions SESS_NUMBER
```