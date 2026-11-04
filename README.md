# Host Scanning and Enumeration Using Nmap

## Overview

This lab focuses on host scanning and network enumeration using **Nmap (Network Mapper)**, a widely used tool for network discovery and security auditing.

The exercise explores how Nmap identifies open ports, detects running services, determines service versions, and attempts to identify the operating system of a target host.

## Lab Objectives

- Understand the fundamentals of host scanning using Nmap.
- Identify open ports on a target host.
- Discover services running on open ports.
- Perform service version detection.
- Attempt operating system detection.
- Explore different Nmap scanning options and their functions.

## Lab Environment

| Component | Details |
|---|---|
| Operating System | Kali Linux |
| Tool | Nmap |
| Target Host | scanme.nmap.org |
| Lab Category | Network Scanning and Enumeration |

## Practical Implementation

### Task 1: Basic Host Scanning

The first task involved performing a basic scan against the target host to identify open ports and associated services.

**Command:**

```bash
nmap scanme.nmap.org
```

**Command Breakdown:**

- `nmap`: Initiates the Network Mapper tool.
- `scanme.nmap.org`: Specifies the target hostname.

By default, Nmap scans the 1,000 most commonly used TCP ports and reports discovered port states and associated service names.

**Purpose:**

- Determine whether the target host is reachable.
- Identify open TCP ports.
- Discover services associated with the identified ports.

This provides an initial overview of the target's exposed network services.

### Task 2: Advanced Scanning and Enumeration

The second task involved performing a more detailed scan to identify service versions and gather operating system information.

**Command:**

```bash
sudo nmap -v -sT -sV -O scanme.nmap.org
```

**Flag Breakdown:**

| Flag | Description |
|---|---|
| `sudo` | Executes Nmap with elevated privileges. |
| `-v` | Enables verbose output. |
| `-sT` | Performs a TCP connect scan. |
| `-sV` | Detects service versions running on open ports. |
| `-O` | Attempts to identify the target operating system. |

**Information Gathered:**

This scan helps identify:

- Open TCP ports.
- Services running on discovered ports.
- Software versions associated with detected services.
- Probable operating system information.

**Why This Matters:**

Service version detection helps security professionals identify potentially outdated software and investigate known vulnerabilities.

Operating system detection uses network-response fingerprinting to estimate the target's operating system. Its accuracy depends on available responses and network conditions.

### Additional Scanning Option: Aggressive Detection

Nmap also provides the `-A` option for more comprehensive scanning.

**Command:**

```bash
sudo nmap -A scanme.nmap.org
```

The `-A` option enables several advanced features, including:

- Operating system detection.
- Service version detection.
- Default script scanning.
- Traceroute.

It provides additional information about the target compared to a basic scan.

### Task 3: Exploring Additional Nmap Scanning Options

The final task involves exploring different Nmap scanning options and understanding how they influence scanning behaviour and output.

**Official Nmap Documentation:**

https://nmap.org/book/port-scanning-options.html

Some commonly used Nmap options include:

| Flag | Function |
|---|---|
| `-sS` | Performs a TCP SYN scan. |
| `-sT` | Performs a TCP connect scan. |
| `-sU` | Performs a UDP scan. |
| `-sV` | Detects service versions. |
| `-O` | Attempts operating system detection. |
| `-A` | Enables advanced detection and scanning features. |
| `-p` | Specifies ports to scan. |
| `-F` | Performs a fast scan using fewer ports. |
| `-Pn` | Skips host discovery and treats the target as online. |

Understanding these options helps security professionals select appropriate scanning techniques based on their assessment objectives.

## Key Learning Outcomes

Through this lab, I explored:

1. The fundamentals of host discovery and network scanning.
2. How to identify open ports and associated services.
3. The difference between basic port scanning and service version detection.
4. How Nmap attempts to identify operating systems through network fingerprinting.
5. How different Nmap flags affect scanning techniques and collected information.
6. The importance of network reconnaissance in cybersecurity assessments.

## Security Relevance

Nmap plays an important role in network reconnaissance and security assessments.

Its capabilities support:

- **Network Discovery:** Identifying active hosts and network assets.
- **Port Scanning:** Discovering exposed network ports.
- **Service Enumeration:** Identifying services and their versions.
- **Attack Surface Assessment:** Understanding externally exposed services.
- **Vulnerability Assessment:** Identifying software versions that may require further security investigation.

## Conclusion

This lab introduced the practical use of Nmap for host scanning and network enumeration.

It covered basic scanning, TCP connect scanning, service version detection, operating system detection, and additional Nmap scanning options.

These techniques provide a foundation for understanding network reconnaissance and identifying potential security weaknesses within network infrastructure.

## Tools and Resources

- **Operating System:** Kali Linux
- **Tool:** Nmap
- **Target:** scanme.nmap.org
- **Official Documentation:** https://nmap.org/book/port-scanning-options.html

## Security Note

scanme.nmap.org is provided by the Nmap project for testing and learning.

Always obtain appropriate permission before scanning other systems or networks.
