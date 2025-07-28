#Tools 
***You need to get root privileges for correct use***

##  TCP 3way handshake protocols on a network subnet
```bash
nmap -sT 10.1.33.0/24
```

## TCP 3way handshake protocols on a device

```bash
nmap -sT 10.1.33.0
```

## TCP  unfinished 3way handshake protocols on a network for #discreet use
```bash
nmap -sS 10.1.33.0/24
```

## Enable OS detection
```bash
nmap -O 10.1.33.0
```

## Enable OS detection, version detection, script scanning, and traceroute
```bash
nmap -A 10.1.33.0
```

