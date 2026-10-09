# NETWORKWALKS-B083-WK2-PM1-PM5-FOOTPRINTING-SCANNING-
# Footprinting, Reconnaissance & Network Scanning

A hands-on cybersecurity project focused on **footprinting, reconnaissance, and network scanning** using Kali Linux tools and Zenmap.

This project covers two practical areas:

- **Project Module 1 – Footprinting & Reconnaissance with Multiple Kali Tools**
- **Project Module 5 – Network Scanning with Zenmap**

The main objective was to understand how information can be gathered during reconnaissance and how active hosts can be identified, analyzed, and visualized within a network.

# Project Module 1 – Footprinting & Reconnaissance

## Overview

Footprinting and reconnaissance involve collecting information about a target before performing further security analysis.

In this module, I used six different tools available in **Kali Linux** to gather and analyze information about a target domain. Each tool provided a different type of information, including domain registration details, web technologies, DNS information, HTTP response headers, and Web Application Firewall detection.

## Tools Used

- WHOIS
- WhatWeb
- Nslookup
- cURL
- Wafw00f
- DNSRecon

---

## 1. WHOIS

WHOIS was used to find publicly available domain registration information.

It helped identify information such as the registrar, registration and expiry details, and name servers associated with the domain.

### Command Used

    whois networkwalks.com

### Result

The command displayed publicly available registration and domain-related information.

<img width="1366" height="768" alt="whois" src="https://github.com/user-attachments/assets/6bab84df-f96f-44f2-8668-eda434018ba3" />

---

## 2. WhatWeb

WhatWeb was used to fingerprint the target website and identify the technologies running on it.

It helped identify technologies such as the web server, CMS, plugins, frameworks, and other components detected on the website.

### Command Used

    whatweb networkwalks.com

### Result

The output provided information about the technologies and components detected on the target website.

<img width="1366" height="768" alt="whatweb" src="https://github.com/user-attachments/assets/5d8b8d4f-df95-4147-8ede-08ce1f19a966" />

---

## 3. Nslookup

Nslookup was used to resolve the target domain name to its associated IP address.

This helped me understand how DNS resolution connects a domain name with its corresponding IP address.

### Command Used

    nslookup networkwalks.com

### Result

The command returned the DNS information and IP address associated with the target domain.

<img width="1366" height="768" alt="nslookup" src="https://github.com/user-attachments/assets/fd47e404-7d2e-4d78-9bf6-4d83da6c668f" />

---

## 4. cURL

cURL was used with the `-I` option to examine the HTTP response headers returned by the target website.

This allowed me to observe information such as the HTTP response status, server information, redirects, and other response headers.

### Command Used

    curl -I https://networkwalks.com

### Result

The response headers provided additional information about how the web server responded to the request.

<img width="1366" height="768" alt="curl" src="https://github.com/user-attachments/assets/dffcfba6-cfd4-4c7d-a5ed-c741bd855419" />

---

## 5. Wafw00f

Wafw00f was used to check whether a **Web Application Firewall (WAF)** was protecting the target website.

This helped me understand how security tools can identify whether a protective layer is present in front of a web application.

### Command Used

    wafw00f networkwalks.com

### Result

The scan identified the WAF protecting the target website.

<img width="1366" height="768" alt="wafw00f" src="https://github.com/user-attachments/assets/1f1987bf-6a5f-4138-a666-f0cce7eabfb0" />

---

## 6. DNSRecon

DNSRecon was used to enumerate DNS records associated with the target domain.

The activity included examining information such as name servers, mail servers, TXT/SPF records, and service records.

### Command Used

    dnsrecon -d networkwalks.com

### Result

The output provided information about the DNS records and infrastructure associated with the target domain.

<img width="1366" height="768" alt="dnsrecon" src="https://github.com/user-attachments/assets/2082ecb0-8dd0-4212-9bf9-59cb5185d41f" />

---

## What I Learned from Footprinting & Reconnaissance

This module helped me understand how different reconnaissance tools can reveal different types of information about a target.

I gained practical experience in:

- Domain information gathering
- Web technology fingerprinting
- DNS resolution
- DNS enumeration
- HTTP header analysis
- Web Application Firewall detection

Using multiple tools together helped me understand how different pieces of publicly available information can be collected and combined to build a broader picture of a target.

# Project Module 5 – Network Scanning with Zenmap

## Overview

This module focused on **network scanning and host discovery using Zenmap**.

Zenmap is the graphical interface for Nmap and provides a visual way to configure and analyze network scans.

The objective was to identify active hosts within my local network, determine their IP and MAC addresses, and visualize the discovered hosts using the network topology feature.

## 1. Zenmap Installation

I installed **Zenmap** on my Windows system to perform the network scanning activities.

Zenmap provides a graphical interface for Nmap and makes it easier to configure scans and analyze their results.

## 2. Finding the Local IP Address and LAN Subnet

Before performing the scan, I used the Windows `ipconfig` command to identify my local IP address and LAN subnet.

The active Wi-Fi interface had the following network configuration:

- **Local IP:** `192.168.0.101`
- **Subnet Mask:** `255.255.255.0`
- **LAN Subnet:** `192.168.0.0/24`
- **Default Gateway:** `192.168.0.1`

This information was used to determine the network range for the scan.

### Command Used

    ipconfig

## 3. Performing a Ping Scan

I entered my local LAN subnet in Zenmap and selected the **Ping Scan** profile.

The scan was performed to identify hosts that were active and responding within the selected subnet.

### Scan Configuration

- **Target:** `192.168.0.0/24`
- **Profile:** Ping Scan

## 4. Identifying Live Hosts

After completing the scan, I examined the results to determine how many hosts were active within the subnet.

The scan identified **3 live hosts**, including my PC.

The IP addresses identified during the scan were:

- `192.168.0.1`
- `192.168.0.100`
- `192.168.0.101`

## 5. Identifying MAC Addresses

After configuring Npcap, Zenmap was able to display MAC address information for the discovered hosts.

This provided additional information about the devices identified during the network discovery process.

The scan results displayed MAC addresses for the discovered network devices.

## 6. Creating Network Topology

Finally, I used Zenmap's **Topology** feature to visualize the discovered hosts and their relationship within the network.

The topology view displayed the discovered hosts along with the local host.

The network topology was saved as a PDF as part of the activity.

This helped me understand how network scan results can be represented visually and how discovered hosts can be viewed in relation to the local system.

<img width="1365" height="717" alt="zenmap_scan_results" src="https://github.com/user-attachments/assets/ce0c26d1-0ea9-4a42-96e2-4fce2a06a68b" />

<img width="1365" height="717" alt="zenmap_topology" src="https://github.com/user-attachments/assets/4d85877c-d6ce-41dc-8540-04a20105182e" />

## What I Learned from Network Scanning

This module gave me practical experience with network scanning and host discovery using Zenmap.

I learned how to:

- Identify a local IP address
- Determine a LAN subnet
- Perform a Ping Scan
- Discover live hosts
- Identify IP addresses of discovered hosts
- Examine MAC addresses
- Visualize network topology
- Interpret basic network scanning results

# Tools & Technologies Used

## Operating Systems

- Kali Linux
- Windows

## Reconnaissance Tools

- WHOIS
- WhatWeb
- Nslookup
- cURL
- Wafw00f
- DNSRecon

## Network Scanning Tools

- Nmap
- Zenmap
- Npcap

---

# Concepts Practiced

- Footprinting
- Reconnaissance
- Domain Information Gathering
- Network Scanning
- Host Discovery
- IP Address Identification
- MAC Address Identification
- Network Topology

---

# Key Takeaways

This project helped me gain practical experience in **reconnaissance and network scanning**, two important areas of cybersecurity.

The footprinting and reconnaissance activities helped me understand how different tools can be used to gather information about a domain, its DNS records, web technologies, HTTP responses, and security mechanisms.

The network scanning activities helped me understand how active hosts can be discovered within a network, how IP and MAC address information can be collected, and how scan results can be analyzed and visualized using Zenmap.

Overall, this project improved my familiarity with **Kali Linux, cybersecurity tools, DNS, web technologies, Nmap, Zenmap, Npcap, and network discovery**.

---

## Disclaimer

All activities documented in this project were performed for **educational and ethical cybersecurity learning purposes** in a controlled environment. Network scanning was performed only on my local network.
