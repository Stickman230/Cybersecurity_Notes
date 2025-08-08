1. Search for corresponding module
```bash
msf> search MODULE
```

2. Use chosen module
```bash
msf> use MODULE_PATH
```

3. Show module options
```bash
msf> show options
```

4. Set module options
```bash
msf> set OPTION_NAME VALUE
```

5. Run the module
```bash
msf> run or exploit
```

6. Check if session created and info about victim
```bash
meterpreter> sysinfo
```

7. Spawn shell session so we get usual commands
```bash
meterpreter> shell   # Spawn normal shell
meterpreter> /bin/bash -i # Convert to interactive bash session
```

8. Background session if needed
```bash
meterpreter> background
```

9. Check active sessions, or rejoin session
```bash
msf> sessions SESS_NUMBER
```