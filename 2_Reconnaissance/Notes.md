# Course 2

Topics that will be covered

- Competitive Intelligence
- Google Hacking
- Websites
- Email Data

*Only test systems where you have explicit written permission when preforming tests. Otherwise use your own systems*

## Reconnaissance Overview

- The first phases is to learn as much as possible about a target
- Footprinting - *Learning as much as possible about the target, 
including remote access capabilities, open ports and services, and what security mechanisms are in place*
- Reconnaissance - *Gathering information abou tthe location of a target by scouting or 
by setting up covert observation posts*
- Passive and Active tactics
- Document your findings

### Sequence of steps 

1. Gather information
2. Locate the network range
3. Discover active machines
4. Determine operating systems
5. See what services are running
6. Map the network

### How to find info ?

- Use public resources

    - Websites, directories, email addresses, job sites, and social networks

- On the logical side

    - Network architecture, defense mechanisms (firewalls, network intrusion detections systems), operating systems, and applications

### Questions to ask before starting

- Who is the target ?
    - Is it a company, a cell phone service, a car or a local business? 
- What is the target ?
    -  Once we get in, what are we looking for, social security numbers, bank account numbers, social media accounts, or even medical information? Identifying what the target is might help in locating the target. If there's no actual target, it's more of a dumpster diving attempt, searching until something interesting is found. 
- Where is the target ?
    -  Start with the IP address and the IP address range, any domain name information, including physical addresses and DNS records.
- When should we attack? 
    - Now when the stakes are high, get in, obtain the target, or late at night? Do you have the persistence to test at odd hours? And how, well, how we do the attack is really going to be after we do the recon.

### Using Competitive Intelligence

- Ethical Hacking uses the same methods as competitive intelligence
- facts found publicly
- look at job postings
- using the job description we could see issues with versions and old versions
- detailed company info
- EDGAR - public searchable database
- Google earth / maps

### Search Engine tricks

- Advanced Searching: https://www.google.com/advanced_search
- https://www.exploit-db.com/
- looking for file types and keywords in google search bar
- example XLS about Networking, *ext:xls networking*
- *inurl:view/index.shtml*, that'll access unprotected cameras -> It's the default public page for network cameras from Axis.
- *inurl:(service | authors | administrators | users) ext:pwd "# -FrontPage-"* this one is good for password searching

### Social Engineering

- Scam artists, hackers, salespeople
- persuastion, dumpster diving, shoulder surfing, eavesdropping, phishing, pharming > redirects to a bogus site fake logins, impersonating
- spyware, maleware

### Searching public records

- enter name 
- narrow the scope
- on public domain
- SEC filings
- phone numbers
- press releases
- buisness profile statistics

examples: Anywho - info about people, Spokeo - people finder, pipl - People search, webhose.io - reputation gathering

### Email Footprinting

- found on the companys website
- generated
- use a companies email list to do Spear Phishing
- can craft an email list, some way to contact a company
- a Sender Policy Framework prevents spammers from spamming with Forged Emails, spoofing


for example look for an email, JSchmo@company.com First Initial and Last Name @ Company Name

### Forging an Email

- deliver payloads via links and downloads
- companies check the email headers for validity
- Read an Email header from Bottom TO Top
- Depending on email client there are different ways to look at the emails header
- The header tells you about the emails path to reaching you
- Tool to Analyze a Emails Header for you: https://www.whatismyip.com/email-header-analyzer/


### Website Mirroring

- Download the entrie website
- using an website downloader tools like, HTTrack, Wget
- hard to stop it, could prevent it
- Best way it to carefully review the site and make sure not to add anything hidden


### Reconnaissance Tools

- Shodan -> which devices are connected to the internet, who is using them. webcams, tv, others
- Metagoofil -> is a pretty strong information gathering tool. It'll take metadata from the target and then it puts it into the form of a web page.
- FOCA -> which is fingerprinting organizations with collective archives examines metadata so you can tell what software is being used, again, such as .doc, pdf, PowerPoint files, along with determining what operating system is in use and other information.
- Linux tool "theHarvester" -> collects emails, employee names, hosts, available ports and banners from various public sources, such as search engines, key servers and databases.
- *dnsrecon -h* -> a linux tool for grnrating a domain name
- ICMP Ping Command -> used to see which hosts are alive, a very chatty protocol
- *Ping* uses ICMP -> used to test the reachability of ICMP
- *Tracert* -> Traces route and provides path and transit times
- *PathPing* -> combines Ping + Tracert
- Namp
- *nslookup* -> used to diagnose DNS


#### DNS 

- uses port 53 over UDP or TCP
    - UDP: used for more frequent requests
    - TCP: only used for a zone transfer

- has multiple Threats
    - Zone file compromise
    - Flood Attack
    - Cache Poisoning
    - DNS Footprinting

| Type | Function |
| ------------- | ------------- |
| A | Maps a hostname to a 32-bit IPv4 address of the host |
| AAAA | Maps a hostname to a 128-bit IPv6 address of the host |
| PTR | Pointer-most common use for implementing reverse DNS lookups |
| MX | Mail exchange record |
| SOA | Start of Authority |

