#eJPT #INE #ActiveInformationGathering


| COMMAND       | FUNCTION                    |
| ------------- | --------------------------- |
| *dnsenum*     | DNS zone transfer           |
| *dig axfrf*   | DNS lookup utility          |
| *fierce*      | lightweight scanner         |
| *netdiscover* | Nmap but using ARP requests |

# What is Active Information Gathering ?

**Gathering information while actively engaging the target (Port Scans, Endpoint Brute forcing...)**

# DNS Zone Transfer 

DNS interrogation is the process of *enumerating DNS records for a specific domain*.

+ The objective of DNS interrogation is to probe a DNS server to provide us with DNS records for a specific domain.
+ This process can provide with important information like the I**P address of a domain, subdomains, mail server addresses **etc.

DNS Zone Transfer on the other hand is :

+ copy or transfer zone files from one DNS server to another. This process is known as a zone transfer.
+ If misconfigured and left unsecured, **this functionality can be abused by attackers to copy the zone file from the primary DNS server to another DNS server**.
+ A DNS Zone transfer can provide penetration testers with a holistic view of an organization's network layout.
+ Furthermore, in certain cases, internal network addresses may be found on an organization's DNS servers.

# Port scanning with Nmap

[[Nmap|Nmap cheat sheet]]

#### Timing Templates

```python
   -T0    -T1    -T2    -T3      -T4      -T5
Paranoid|Sneaky|Polite|Normal|Aggressive|Insane|
```

**Windows system typically block ICMP pings (default scan)**



---

[[Passive Recon|See passive recon]]