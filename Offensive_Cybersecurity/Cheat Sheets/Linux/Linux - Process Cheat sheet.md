
# Enable SMB network Share

- Navigate to `impacket` directory using `cd /opt/impacket/examples`
- Enter the command, to start the SMB server sharing the `/tmp` directory.```
```shell
python3.9 smbserver.py -smb2support -comment "My Logs Server" -debug logs /tmp
``` 

- You can access the contents of the network share by entering the command `smbclient //ATTACKBOX_IP/logs -U guest -N`. This would allow you to connect to the network share, and then you can issue the command `ls` to list all the commands.