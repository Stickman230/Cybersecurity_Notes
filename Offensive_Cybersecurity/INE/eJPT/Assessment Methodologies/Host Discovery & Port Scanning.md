#eJPT #INE #HostDiscovery

| COMMAND                                        | FUNCTION                   |
| ---------------------------------------------- | -------------------------- |
| *fping* -aqg                                   | Discover hosts on network  |
| *nmap* -Pn -A $target                          | basic scan for all options |
| *mysql* -u USERNAME -pPASSWORD -h 192.134.78.3 | connect to remote mysql db |
| *ftp*                                          | connect to ftp service     |

# Network Mapping

The process of **identifying Network Infrastructure, Hosts and devices within a target infrastructure**

#### Objectives

- *Discovery of Live Hosts*: Identifying active devices and hosts on the network. This involves determining which IP addresses are currently in use.

- I*dentification of Open Ports and Services*: Determining which ports are open on the discovered hosts and identifying the services running on those ports. This information helps pentesters understand the attack surface and potential vulnerabilities.

- *Network Topology Mapping*: Creating a map or diagram of the network topology, including routers, switches, firewalls, and other network infrastructure elements. 

How to do: Use Nmap 

# Host Discovery

- Ping Sweeps (ICMP Echo Requests): Sending ICMP Echo Requests (ping) (ICMP Echo Request: Type: 8, Code: 0)
	- ICMP Echo Reply:
		+ Type: 0
		+ Code: 0

- ARP Scanning: Using Address Resolution Protocol (ARP) requests to

-  TCP SYN Ping (Half-Open Scan): Sending TCP SYN packets to a specific port (often port 80) to check if a host is alive. If the host is alive, it responds with a TCP SYN-ACK. **This technique is stealthier than ICMP ping.**

- UDP Ping: Sending UDP packets to a specific port to check if a host is alive. This can be **effective for hosts that do not respond to ICMP or TCP probes.**

- TCP ACK Ping: Sending TCP ACK packets to a specific port to check if a host is alive. This technique expects no response, but if a TCP RST (reset) is received, it indicates that the host is alive.

- SYN-ACK Ping (Sends SYN-ACK packets): Sending TCP SYN-ACK packets to a specific port to check if a host is alive. If a TCP RST is received, it indicates that the host is alive.

# MySQL & Maria DB

Get DB information and structure : `SHOW DATABASES;`

# Evasion Techniques

Using Nmap to evade Firewalls and discover hosts stealthily

[[Nmap Firewall Evasion Cheat Sheet]]

---

#### Definitions

*Ping Sweeps* : A ping sweep is a network scanning technique used to discover live hosts, the basic idea is to send a series of ICMP Echo Request (ping) messages to a range of IP addresses and observe the responses