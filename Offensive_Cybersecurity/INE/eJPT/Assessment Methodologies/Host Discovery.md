#eJPT #INE #HostDiscovery

# Network Mapping

The process of identifying Network Infrastructure, Hosts and devices within a target infrastructure

#### Objectives

- Discovery of Live Hosts: Identifying active devices and hosts on the network. This involves determining which IP addresses are currently in use.

- Identification of Open Ports and Services: Determining which ports are open on the discovered hosts and identifying the services running on those ports. This information helps pentesters understand the attack surface and potential vulnerabilities.

- Network Topology Mapping: Creating a map or diagram of the network topology, including routers, switches, firewalls, and other network infrastructure elements. Understanding the layout of the network assists in planning further penetration testing activities.

How to do: Use Nmap 

# Host Discovery

- Ping Sweeps (ICMP Echo Requests): Sending ICMP Echo Requests (ping)
- ARP Scanning: Using Address Resolution Protocol (ARP) requests to
● TCP SYN Ping (Half-Open Scan): Sending TCP SYN packets to a specific
port (often port 80) to check if a host is alive. If the host is alive, it
responds with a TCP SYN-ACK. This technique is stealthier than ICMP
ping.
Host Discovery Techniques
● UDP Ping: Sending UDP packets to a specific port to check if a host is
alive. This can be effective for hosts that do not respond to ICMP or TCP
probes.
● TCP ACK Ping: Sending TCP ACK packets to a specific port to check if a
host is alive. This technique expects no response, but if a TCP RST
(reset) is received, it indicates that the host is alive.
● SYN-ACK Ping (Sends SYN-ACK packets): Sending TCP SYN-ACK
packets to a specific port to check if a host is alive. If a TCP RST is
received, it indicates that the host is alive.