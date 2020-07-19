All about Managing Risks

Hacker was first coined at MIT in 1960
- now has a bad connotation

There are many sub groups

Sans.org has a start up for creating a security policy

*there are more kinds, but these are the most common*
1. Black Hat - The bad guys, malicious intent
2. Grey Hat - Borderline unknown intent, curious
3. White Hat - The Good guys, Protecting / Good intent

# Understanding Vunerabilities
- Risks
- Threats, something that might happen
- OWASP, has a list of top tens

# Penatration Testing
- White hats use the same tools as Black hats
- Understanding threats
- using tools
- Testing apps, Databases, network devices and more
- answers how vulnerables you are
- are you running unnecessary ports/protocols

# Hacking Concepts
- gain entry into a system
- using the Dark web *aka TOR* a flow of traffic on the TOR Nodes [link](https://torflow.uncharted.software/)
- only scan on your own network, or ones you have access to

# The Human Factor
- Someone will need to read the report
- a scan does not chack all attack vectors
- scans should be run on a time basis, monthly, etc
- what can be done for counter measures
- warnings for company
- cybercrime is more lucrative than drug traffiking
- Ensure a defensive posture

# Hacking Phases
- typically 5 phases

    1. Reconnaissance
        - Who, what, where, when, and how
    2. Scanning
        - identifying weaknesses, makes and models, looking for packets
        - TCP scans, footprinting
    3. Gaining Access
        - Luanching Exploits
        - XSS, buffer overflows
    4. Maintaing Access
        - Privilge escalation
        - add backdoor
    5. Covering Tracks
        - cleanup evidence, 
        - on linux
            - Mteasploit *meterpeter > clearev* 
            - open log files are stored in the */var/log* directory remove with Backtrack:*kwrite /var/log/messages*
            - Erase the command history and set it to 0 *export HISTSIZE=0*
            - shred the history file *shred -zu root/.bash_history*
        - on Windows
            - clear all log files