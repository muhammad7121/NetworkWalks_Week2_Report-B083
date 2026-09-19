# Networkwalks Academy — Cybersecurity Professional Program

## Week 02 Report — Reconnaissance & Footprinting Techniques

**Prepared By:** Muhammad Abdullahi Muhammad  
**Instructor:** Waqas Karim  
**Batch:** Cybersecurity Professional — B082  
**Organization:** Networkwalks Academy  
**Week:** Week 02

---

## Overview

This repository contains my Week 02 cybersecurity project for the Networkwalks Academy Cybersecurity Professional Program.

The project focused on **Reconnaissance and Footprinting**, an important early phase of penetration testing where information about a target is collected before exploitation or intrusive testing.

The practical work covered:

- Kali Linux multi-tool footprinting
- OSINT reconnaissance with Maltego
- Email and host harvesting with theHarvester
- Network discovery and port scanning with Zenmap/Nmap

> **Ethical Notice:** All activities were performed for educational and authorized cybersecurity training purposes.

---

## Learning Objectives

- Understand reconnaissance and footprinting techniques.
- Perform domain and DNS enumeration.
- Identify web technologies and server information.
- Detect Web Application Firewall (WAF) protection.
- Perform OSINT reconnaissance using Maltego.
- Harvest publicly available emails and hosts using theHarvester.
- Perform network host discovery and port scanning using Zenmap.
- Interpret reconnaissance results from a security perspective.
- Improve cybersecurity documentation and reporting skills.

---

## Tools Used

| Tool | Purpose |
|---|---|
| WHOIS | Domain registration information |
| WhatWeb | Web technology fingerprinting |
| nslookup | DNS resolution |
| curl | HTTP response and metadata analysis |
| WAFW00F | WAF detection |
| dnsrecon | DNS enumeration |
| Maltego | OSINT and relationship mapping |
| theHarvester | Email and host harvesting |
| Nmap | Network discovery and port scanning |
| Zenmap | Graphical interface for Nmap |

---

# 1. Kali Linux Multi-Tool Footprinting

The target domain used for the footprinting exercises was:

`networkwalks.com`

Six reconnaissance tools were used to collect different categories of information.

### WHOIS

WHOIS was used to identify publicly available domain registration information, including:

- Registrar information
- Domain creation and expiry information
- Name servers
- Domain status and locks

### WhatWeb

WhatWeb was used for web technology fingerprinting.

The scan identified technologies including:

- Apache
- WordPress
- WordPress Download Manager
- jQuery
- Google Tag Manager

### nslookup

`nslookup` was used with Google's DNS resolver to resolve the target domain and identify its IP address.

### curl

`curl` was used to retrieve the HTTP response and inspect publicly exposed web metadata, including:

- WordPress information
- SEO metadata
- Open Graph metadata
- Twitter Card metadata
- JSON-LD information

### WAFW00F

WAFW00F was used to identify whether a Web Application Firewall was protecting the target.

The scan identified:

**ModSecurity (SpiderLabs)**

### dnsrecon

`dnsrecon` was used for detailed DNS enumeration.

The results included:

- SOA records
- NS records
- MX records
- A records
- TXT records
- SPF information
- SRV records
- Mail infrastructure

### Result

Combining the six tools provided a broader footprint of the target rather than depending on a single reconnaissance technique.

---

# 2. OSINT Reconnaissance with Maltego

Maltego Graph was used to perform Open-Source Intelligence (OSINT) reconnaissance.

A domain entity for `networkwalks.com` was created and transforms were used to identify relationships between the domain and publicly available information.

The investigation identified the published contact email:

`info@networkwalks.com`

A separate OSINT graph was also created for a named individual as part of the authorized training exercise.

### Key Learning

Maltego makes OSINT investigation easier by visually representing relationships between entities such as:

- Domains
- Email addresses
- People
- Websites
- Social-media profiles

---

# 3. Email and Host Harvesting with theHarvester

theHarvester was used to collect publicly indexed:

- Email addresses
- Hostnames
- Subdomains
- IP addresses

## Test 1 — microsoft.com

The tool was first tested against `microsoft.com` to verify that it was working correctly.

The scan successfully returned publicly indexed email and host information.

## Test 2 — networkwalks.com

The same technique was then applied to `networkwalks.com`.

The selected Baidu source returned no results.

This demonstrated an important reconnaissance concept:

> No results from one source do not necessarily mean that a target has no publicly available information.

Results depend on the target's indexing and the data source being queried.

---

# 4. Network Scanning with Zenmap

Zenmap, the graphical interface for Nmap, was used for network reconnaissance.

Nmap installation was first verified from Windows Command Prompt.

Two scan profiles were then performed against an authorized local network target.

## Quick Scan

The Quick Scan identified the target host as active and detected:

| Port | Service |
|---:|---|
| 135 | MSRPC |
| 139 | NetBIOS Session Service |
| 445 | Microsoft-DS / SMB |

These ports are commonly associated with Windows networking services.

## Ping Scan

A Ping Scan was also performed for host discovery.

The scan confirmed that the target host was reachable without performing a port scan.

## Security Significance

Open ports such as 135, 139, and 445 can provide valuable information about a Windows system and should be appropriately restricted, especially on networks where untrusted devices may have access.

---

# Challenges Faced

### 1. Different theHarvester Results

theHarvester returned useful information for `microsoft.com` but no results for `networkwalks.com` when using the selected source.

This demonstrated that reconnaissance results depend heavily on the data source and how well a target is indexed.

### 2. Combining Multiple Tools

Each reconnaissance tool provided a different type of information.

The results from WHOIS, WhatWeb, DNS tools, WAFW00F, Maltego, theHarvester, and Zenmap had to be compared and connected to create a more complete picture.

### 3. Maltego Transform Credits

Maltego's available transform credits required careful selection of transforms during the investigation.

---

# Lessons Learned

Through this project, I learned that:

- Reconnaissance is an important first step in penetration testing.
- No single tool provides a complete target footprint.
- DNS information can reveal useful infrastructure details.
- Web technology fingerprinting can identify technologies that may require security attention.
- WAF detection helps understand the security controls protecting a web application.
- OSINT can reveal relationships between domains, people, emails, and online platforms.
- theHarvester results can vary depending on the source being queried.
- Network scanning helps identify active hosts and exposed services.
- SMB-related ports require careful security configuration.
- Reconnaissance should be performed systematically before moving toward active testing.

---

# Conclusion

Week 02 provided practical experience with reconnaissance and footprinting techniques used in cybersecurity and penetration testing.

The project covered:

**Kali Linux → WHOIS → WhatWeb → nslookup → curl → WAFW00F → dnsrecon → Maltego → theHarvester → Zenmap/Nmap**

The project strengthened practical understanding of:

- OSINT
- DNS enumeration
- Web fingerprinting
- WAF detection
- Email and host harvesting
- Network discovery
- Port scanning
- Technical cybersecurity documentation

---

# Repository Structure

```text
Networkwalks_Week2_Report/
│
├── Kali-Linux/
├── Maltego/
├── theHarvester/
├── Zenmap/
├── Networkwalks_CyberSec_Week02_Report.pdf
├── README.md
└── .gitignore
```

The folders can be used to store screenshots, command outputs, notes, and evidence for each practical module.

---

# References

- Kali Linux — https://www.kali.org
- Nmap — https://nmap.org
- Zenmap — https://nmap.org/zenmap/
- Maltego — https://www.maltego.com
- theHarvester — https://github.com/laramies/theHarvester
- WAFW00F — https://github.com/EnableSecurity/wafw00f
- dnsrecon — https://github.com/darkoperator/dnsrecon
- Networkwalks Academy — https://networkwalks.com

---

## Author

**Muhammad Abdullahi Muhammad**  
Cybersecurity Professional — B082  
Networkwalks Academy  
Week 02 — Reconnaissance & Footprinting Techniques
