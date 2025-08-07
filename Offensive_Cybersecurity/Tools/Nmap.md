#Tools 
***You need to get root privileges for correct use***

# Timing Options

```python
   -T0    -T1    -T2    -T3      -T4      -T5
Paranoid|Sneaky|Polite|Normal|Aggressive|Insane|
```

# Examples

## Scan host ignoring Ping probes
```Shell
# Very Common for windows host
nmap -Pn 10.1/33/0
```

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

