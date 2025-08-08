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

## Connect (smbclient)

```bash
smbclient //TARGET_IP/SHARE_NAME -U USERNAME
```

## Connect (impacket-smbclient)

```bash
impacket-smbclient admin:'P@ssw0rd!'@10.10.10.5
```

## Connect NTLM Hash (impacket-smbclient)

``` bash
impacket-smbclient -hashes LMHASH:NTHASH USER@TARGET_IP
```

## Connect NTLM Hash (crackmapexec)

```bash
crackmapexec smb TARGET_IP -u USERNAME -H NTHASH --shares
```

## Connect (Windows)

```powershell
net use \\TARGET_IP\SHARE_NAME PASSWORD /user:USERNAME
```
---
# Mount SMB Share Locally (Linux)

```
sudo mount -t cifs //TARGET_IP/SHARE_NAME /mnt/smb -o username=USERNAME,password=PASSWORD,domain=DOMAIN

```