| Technique             | Flag(s)                      | Purpose                                 |
| --------------------- | ---------------------------- | --------------------------------------- |
| Fragmentation         | `-f`, `--mtu`                | Bypass packet filters via fragmentation |
| Decoys                | `-D`                         | Hide source IP                          |
| Source IP Spoofing    | `-S`, `-e`                   | Impersonate another host                |
| Source Port           | `--source-port`              | Evade port-based firewall rules         |
| Timing                | `-T0`–`-T5`                  | Control speed to evade IDS              |
| Randomize Hosts       | `--randomize-hosts`          | Avoid predictable scan order            |
| Scan Delay / Max Rate | `--scan-delay`, `--max-rate` | Throttle packets                        |
| MAC Spoofing          | `--spoof-mac`                | Disguise as another device              |
| IPv6 Scanning         | `-6`                         | Bypass IPv4-only firewalls              |
| No / Force DNS        | `-n`, `-R`                   | Control DNS resolution                  |
| Data Length           | `--data-length`              | Obfuscate packet signatures             |
| Idle/Zombie Scan      | `-sI`                        | Indirect, stealth scanning              |

---
## 1. Fragmentation (`-f`, `--mtu`)
Split probe packets into tiny fragments to bypass packet inspection filters.

```bash
nmap -f <target>
nmap --mtu 24 <target>
```
- `-f` → Tiny 8-byte IP fragments.
- `--mtu <size>` → Set custom fragment size (must be multiple of 8).

---
## 2. Decoy Scans (`-D`)

Hide your real IP by spoofing multiple decoys.

```bash
nmap -D RND:10 <target> nmap -D 192.168.1.5,192.168.1.6,ME <target>
```

- `RND:10` → 10 random decoys.
- `ME` → Your real IP among decoys.

---
## 3. Source IP Spoofing (`-S`) + Interface (`-e`)

Send packets with a forged source address.
```bash
nmap -S 192.168.1.100 -e eth0 <target>
```

---
## 4. Source Port Manipulation (`--source-port`)

Send packets from ports likely allowed by firewalls.

```bash
nmap --source-port 53 <target> nmap --source-port 443 <target>
```

- Often works for DNS (53), HTTP(S) (80, 443), SMTP (25).

---
## 5. Timing Options (`-T0` to `-T5`)

Adjust speed to avoid detection by IDS/IPS.

```bash
nmap -T0 <target>
```

- Lower speed reduces chance of detection.
- `-T0` waits 5 min between probes.

---
## 6. Randomize Target Order (`--randomize-hosts`)

Avoid predictable scanning patterns.

```bash
nmap --randomize-hosts 192.168.1.0/24
```

---
## 7. Scan Delay & Packet Rate (`--scan-delay`, `--max-rate`)

Throttle scan to avoid triggering alarms.

```bash
nmap --scan-delay 5s <target> nmap --max-rate 50 <target>
```

---
## 8. MAC Address Spoofing (`--spoof-mac`)

Impersonate another device type/vendor.

```bash
nmap --spoof-mac 0   <target>  # Random MAC
nmap --spoof-mac Cisco <target> 
nmap --spoof-mac 00:11:22:33:44:55 <target>
```

---

## 9. Using IPv6

Sometimes bypasses IPv4-only filters.

bash

CopyEdit

`nmap -6 <target>`

---
## 10. Appending DNS Resolution Tricks

Avoid DNS queries or force reverse lookups.

bash

CopyEdit

`nmap -n <target>         # No DNS resolution nmap -R <target>         # Always reverse-resolve`

---

## 11. Custom Packet Payloads (`--data-length`)

Pad packets to evade IDS signatures.

bash

CopyEdit

`nmap --data-length 50 <target>`

- Adds 50 random bytes to each packet.



---
## Combination Example

Mixing evasion techniques for stealth:

```bash
nmap -f -D RND:5 --source-port 443 --data-length 50 -T2 --randomize-hosts <target>
```