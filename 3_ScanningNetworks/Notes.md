# Scaninng

- start with the well-known ports
- mostly ports 1 - 1023

| Port | Service |
| ------------- | ------------- |
| 21 | FTP Control File Transfer |
| 22 | SSH Remote Login Protocol |
| 53 | DNS |
| 80 | HTTP |
| 88 | Kerberos |

- Ports 1024 -> 49151 are registered ports
    - Meaning that these are Vendor ports, for certain applications
    - like 3389 for RDP

- Never scan Federal or Government IPs, there is a list online

## Overview

### Techniques

- Ping Sweep
- Port Scan
- Network Mapping
- OS Fingerprinting

### How to scan IPv6 networks

- standard min subnet size for a LAN: /64
- the potential for up to 18.4 quintillion addresses
- configuring these IPs can be done

    #### Manually configured

    - If manually configured they are usually in a pattern
    - likely ::1, ::2, ::3
    - It is application specific
    - example a mail server might have the address ::5:25
    - an IPv4 address can be embedded in the address

    #### Stateless Address Autoconfiguration (SLAAC)

    - Uses an Extended Unique Identifier (EUI)
    - Assigns itself a unique 64-bit IPv6 address
    - uses a FFFE in the 4th and 5th bytes
    - a group of hosts on a network commonly share same NIC card Vendor

    ### DHCPv6

    - Issues an address from the pool
    - Many times has a predictable pattern
    - ::2000-3300 or ::300-400

### IPv6 Scanning Tools

- IPv6 packets containing unrecognized extensions
- WHOIS
- Reverse Mapping
- Emails may leak IPv6 addresses

# Identifying Live Systems Using Protocols

- Three way handshakes -> when Clients communicate to servers,
    1. SYN - Begining
    2. SYN, ACK
    3. ACK - END


## scanning ports

- 65,535 TCP and UDP ports
- Used to identify a specific application or process
- almost always scan well-known ones
- UDP is scanned less frequent
- TCP offers more opportunities to manipluate the header
- UDP is connection-less protocol
- TCP is a connection oriented protocol
- A TCP header has 11 fields and contains a one byte field for the flags. 

| Type | Ports | Common Uses (Protocols) |
| ---- | ----- | ------------- |
| Well-Known Ports | 1 - 1023 | FTP, DNS and HTTP |
| Registered Ports | 1024 - 49151 | SOCKS, OpenVPN, and gaming applications |
| Dynamic or Ephemeral | 49152 - 65535 |  |

## Flags

- *Reserved* for future use and should be set to zero
- *Nonce* is experimental possible use with Explicit Congestion Notification
- *Congestion Window Reduced* this flag is set by the sending host to indicate that it received 
    a TCP segment with the Explicit Congestion Notification flag set, and have responded in congestion-controlled mechanism
- *Urgent* this indicates the packet should have priority
- *Acknowledgement* this is an acknowledgement of packets received
- *Push* generally a buffer holds data until it has a decent sized packet to send. 
- *Reset* this is designed to allow a station to abort the TCP connection with another station
- *SYN* the SYN flag synchronizes the sequence number
- *FIN* this means the process is complete. There is no more data from the sender

## TCP Flags for Scans
| Type | Flags | Open Port Response | Closed Port Response |
| ---- | ----- | ------------------ | -------------------- |
| Full Connect | SYN | SYN-ACK | RST |
| SYN Stealth | SYN | SYN-ACK | RST |
| FIN | FIN | NONE | RST/ACK |
| NULL | NONE | RST | NONE |
| ACK | ACK | RST | NONE |
| XMAS | FIN/URG/PSH | NONE | RST/ACK |

1. Stealth Mode: Idle Scan

- find a Suitable Zombie

## Good Practices for DNS Servers

- Resrict Zone Transfers
- Deny inbound connections to TCP port 53 (a DNS zone transfer)
- Consider using DNSSec
- Conceal info at the registrars on file
- Use split horizon or split DNS
- Don't provide recursive services to the public 
- Monitor your DNS server

## Scan using ICMP

Used to discover info about a system or network

Types like

- Echo
- Timestamp
- Information
- Subnet Mask

## Banner Grabbing

obtaining info from a target host like OS Open Ports and Services running

- tools
    - Netcat
    - Nmap
    - DMitry
    - CURL
    - Armitage

- should prevent banner grabbing
- hide file extensions on services

# Blueprint the Network

- Nmap (CLI)

    - scans the network
    - displays open ports
    - running services

- ZenMap (GUI based)

- You can save the output to a txt file
    `nmap 192.168.10.1 > scan.txt`

## Identify the OS

- Nmap can tell us OS's
- Passive Discovery
- It is known from the Header
- Can also look at the HTTP headers

# Vulnerability Scanning

- Probes targets on the network
    - detects open ports
    - determines software, OSs and versions
    - Identifies known vulnerabilities

# Scanning Tools

- nslookup - to get IPs
- Hping - craft and send Packets
- Nikto - web server scanner 
- Netscan

# Evading Detection

- many companies use Intrusion Detection Systems (IDS)
- Scanning can generate signatures
- don't send 1,000's of packets
- Cloak with Decoys
- -D option can hide your IP
- Spoof your data
- Xmas tree attack, large number of packets
- IP Fragmentation Scan, can avoid detection, splits up TCP headers into many packets
- Stay Anonymous, InPrivate Browsing
- use Password Managers
- Use Duck Duck Go as a search Engine
- HTTP is stateless
- Cookies can store data
- use a personal VPN
- Phones track a lot of data, use a Burner Phone
- Don't use GPS
- Use 10 Minute Email, for pointless items

# Concealing and Spoofing

- torproject.org (darkweb/deepweb)
- TOR / Onion Routing, a privacy focused browser
- Don't Torrent
- Don't install plugins
- only use HTTPS not HTTP
- Don't open Documents
- Proxy's to obfuscate your IP

example of using proxy and nmap in Kali/Linux
`proxychains nmap -sS 45.33.32.156`

- Spoof your Address, fake your IPs
- no possibility of getting a reply
- ARP spoofing

# Tunneling

- they bypass most firewall and proxy restrictions
- only allow per-approved software
- set group policies
- close uneeded ports and services
- use an AV software
- use an IDS
- inspect the log files
- build statistics
- set connection timeouts
- don't alloe HTTP-CONNECT queris
- disable SSH port forwarding

1. HTTP
    - Teredo IPv6 over UDP Tunneling
    - IPSec, SSL for Encryption
    
2. SSH

