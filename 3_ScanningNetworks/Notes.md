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