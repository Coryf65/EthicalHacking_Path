# Enumeration

Get started with the same test enviroment and tools by following along with the *Pre-Setup Guide*

1. Pre-Setup Guide [here](https://github.com/Coryf65/EthicalHacking_Path/tree/master/4_Enumeration/EnumerationPreconfiguration.pdf)


## What is it ?

Enumeration is the process of identifying usernames, system addresses, network resources, 
shares, services, and other characteristics of a target. It happens through open source intelligence, and also by direct probing of a target's system.

## Why ?

The reason for doing enumeration is to understand the target before testing it, and to obtain information to enable testing. 
For example, one outcome from this might be to identify a user account or system account for potential use in penetrating the target.

## Approcahes

- Local host
- Remote host
- Internet
- Port and service

## Useful Services to Enumerate

- Domain Name Server (DNS) : port 53
- Simple Mail Transfer Protocol (SMTP) : port 25
- Remote Procedure Calls (RPC) : port 135
- NetBIOS : port 137, 139
- Simple Network Management Protocol (SNMP) : port 161
- Lightweight Directory Access Protocol (LDAP) : port 389
- Server Message Block (SMB) : TCP port 445 

## Profiling a Linux Host

in Terminal ...

- `uname -a` -> gets system info

- `cat /proc/version` -> get versions

- `cat /etc/*-release` -> more info on Distro

- `cat /proc/cpuinfo` -> CPU details

- `df -a` -> File system details

- `cat /etc/shells`

- `whoami` -> who are we logged in as 

- `pwd` -> get our personal directory 

- `id` -> display user account details 

- `users` -> see what users are on currently

- `sudo cat /etc/shadow` -> List Password Hashs if we have sudo available

- `pinky` -> get user login time, source ips 

- `who -a` -> system running processes 

- `lastlog` -> get user history activity

- `ps aux` -> open processes 

- `top` -> current running process status

- `dpkg -l` -> get all installed pacakges 

- `sudo iptables -L` -> see firewall rules

### Investigating Linux Network Interface

in Terminal ...

- `netstat -h` -> see all flags/args, the help toggle

- `netstat -ie` -> see interfaces

- `netstat -rn` -> see routing tables

- `netstat -a` -> see all connections

can also use *ss* tool

- `ss -h` -> another tool to try, display help options


## Profiling a Windows Host

- Use a Tool called *PsTools* from sysinternals

### Investigating Windows Network Interface

in CMD ...

- `netstat -h` -> see all flags/args, the help toggle

- `net view` -> 

- `netstat` -> display all active TCP connections, there are many flags/args to use as well

- `netstat -rn` -> see interfaces