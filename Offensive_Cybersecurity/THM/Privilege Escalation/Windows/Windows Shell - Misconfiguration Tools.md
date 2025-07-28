#PrivEsc #Windows 
## WinPEAS 

- WinPEAS is a script developed to enumerate the target system to uncover privilege escalation paths. You can find more information about winPEAS and download either the precompiled executable or a .bat script.

## PrivescCheck

- PrivescCheck is a PowerShell script that searches common privilege escalation on the target system. It provides an alternative to WinPEAS without requiring the execution of a binary file.
- To run PrivescCheck on the target system, you may need to bypass the execution policy restrictions. To achieve this, you can use the Set-ExecutionPolicy cmdlet.
	- Powershell	
	 ```PS C:\> Set-ExecutionPolicy Bypass -Scope process -Force```
	 ```PS C:\> . .\PrivescCheck.ps1```
	 ```PS C:\> Invoke-PrivescCheck```

## WES-NG: Windows Exploit Suggester - Next Generation

- More discreet, python script that runs on attacking host
- run **systeminfo** on target and grab output file
- process output on attacking host

## Metasploit

- If you already have a Meterpreter shell on the target system, you can use the multi/recon/local_exploit_suggester module to list vulnerabilities that may affect the target system and allow you to elevate your privileges on the target system.