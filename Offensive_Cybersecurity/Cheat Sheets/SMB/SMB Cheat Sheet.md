#SMB 

# Shares Enumeration
## Enumerate shares (smbclient)

```bash
smbclient -L //10.2.20.146 -U administrator
```

## Enumerate shares (Crackmapexec)

```bash
crackmapexec smb TARGET_IP -u USERNAME -p PASSWORD --shares
```

## Enumerate shares (Impacket)

```bash
impacket-smbclient USERNAME:PASSWORD@TARGET_IP -list
```

## Enumerate shares (Windows)

```powershell
net use \\TARGET_IP\IPC$ PASSWORD /user:USERNAME
net view \\TARGET_IP /all
```
---

# Connect to SMB Share

```bash
smbclient //TARGET_IP/SHARE_NAME -U USERNAME
```