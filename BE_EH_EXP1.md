# Experiment 1
# Overview of Ethical Hacking Methodology and Demonstration of Security Tools

## Aim

To understand the Ethical Hacking Methodology and demonstrate the basic usage of commonly used ethical hacking tools used during a penetration testing process.

---

## Course Outcome Mapping

**CO1:** Analyse and evaluate the cyber security needs of an organization.

---

## Learning Objectives

After successful completion of this experiment, students will be able to:

- Understand the phases of Ethical Hacking.
- Identify the purpose of different ethical hacking tools.
- Perform basic host discovery and network scanning.
- Observe web traffic using a proxy tool.
- Study vulnerability assessment and penetration testing frameworks.
- Prepare a basic security assessment summary.

---

## Prerequisites

Students should be familiar with:

- Basic Computer Networks
- TCP/IP Protocol Suite
- IP Addressing
- Client-Server Architecture
- Operating System Basics

---

# Theory

Ethical Hacking is the process of identifying vulnerabilities in computer systems, applications, or networks with proper authorization to improve their security. Ethical hackers follow a structured methodology to identify weaknesses, verify vulnerabilities, and recommend suitable countermeasures.

The Ethical Hacking lifecycle consists of the following phases.

```text
Reconnaissance
      │
      ▼
Scanning
      │
      ▼
Enumeration
      │
      ▼
Vulnerability Assessment
      │
      ▼
Exploitation
      │
      ▼
Maintaining Access
      │
      ▼
Reporting
```

### Reconnaissance

Information gathering phase where details about the target network are collected.

Examples:

- IP Address
- Domain Name
- DNS Information
- Technologies Used

---

### Scanning

Scanning identifies:

- Live hosts
- Open ports
- Running services
- Operating System

---

### Enumeration

Enumeration extracts detailed information from discovered services such as users, shared resources, and network services.

---

### Vulnerability Assessment

This phase identifies security weaknesses using vulnerability scanners.

---

### Exploitation

Ethical hackers verify vulnerabilities only in authorized environments.

---

### Reporting

A detailed report containing vulnerabilities, evidence, risk level, and recommendations is prepared.

---

# Practical Scenario

You are working as a Cyber Security Analyst in an organization.

The network administrator has requested an initial security assessment of the laboratory network.

Your tasks are to:

1. Discover active hosts.
2. Scan open ports.
3. Observe web requests.
4. Study vulnerability scanning.
5. Explore the Metasploit Framework.
6. Observe network monitoring tools.
7. Prepare a summary of your findings.

---

# Software Requirements

| Tool | Purpose |
|------|---------|
| Nmap | Network Scanner |
| Angry IP Scanner | Host Discovery |
| Burp Suite Community Edition | Web Security Testing |
| Metasploit Framework | Penetration Testing Framework |
| Ettercap | Network Monitoring |
| GFI LANguard | Vulnerability Scanner |
| NetStumbler (or Equivalent) | Wireless Network Discovery |

> **Note:** Refer to the installation guide provided by the instructor if any software is not already installed.

---

# Procedure

## Activity 1 – Host Discovery

### Tool Used

**Angry IP Scanner**

### Steps

1. Launch Angry IP Scanner.
2. Enter the network range.

Example:

```
192.168.1.0 - 192.168.1.254
```

3. Click **Start**.
4. Observe the list of active hosts.

### Expected Output

- Live Hosts
- Host Names
- Response Time

---

## Activity 2 – Port Scanning

### Tool Used

**Nmap**

Open Command Prompt or Terminal.

Scan a host.

```bash
nmap 192.168.1.10
```

Detect service versions.

```bash
nmap -sV 192.168.1.10
```

Detect operating system.

```bash
nmap -O 192.168.1.10
```

### Expected Output

- Open Ports
- Running Services
- Operating System

---

## Activity 3 – Web Traffic Analysis

### Tool Used

**Burp Suite Community Edition**

### Steps

1. Launch Burp Suite.
2. Enable **Proxy → Intercept**.
3. Configure browser proxy settings.
4. Open a sample web page.
5. Observe intercepted HTTP requests.

### Expected Output

Students should observe:

- HTTP Method
- URL
- Headers
- Cookies
- Request Parameters

---

## Activity 4 – Vulnerability Assessment

### Tool Used

**GFI LANguard**

### Steps

1. Launch LANguard.
2. Enter the target IP address.
3. Start the scan.
4. Wait for the report.

### Expected Output

- Missing Security Updates
- Vulnerabilities
- Security Recommendations

---

## Activity 5 – Study of Metasploit Framework

### Tool Used

**Metasploit Framework**

Launch Metasploit.

```bash
msfconsole
```

Display available commands.

```bash
help
```

Search FTP modules.

```bash
search ftp
```

Search SMB modules.

```bash
search smb
```

### Expected Output

Observe:

- Exploit Modules
- Auxiliary Modules
- Payload Options

> **Note:** Do not perform exploitation on unauthorized systems.

---

## Activity 6 – Network Monitoring

### Tool Used

**Ettercap**

### Steps

1. Launch Ettercap.
2. Select the network interface.
3. Perform host discovery.
4. Observe discovered devices.

### Expected Output

- Active Hosts
- MAC Addresses
- Network Interface

---

## Activity 7 – Wireless Network Discovery

### Tool Used

**NetStumbler (or Equivalent)**

### Steps

1. Launch the software.
2. Start scanning.
3. Observe nearby wireless networks.

### Expected Output

- SSID
- Channel
- Signal Strength
- Encryption Type

---

# Observation Table

| Activity | Tool Used | Observation |
|-----------|-----------|-------------|
| Host Discovery | Angry IP Scanner | |
| Port Scanning | Nmap | |
| Web Analysis | Burp Suite | |
| Vulnerability Assessment | LANguard | |
| Exploitation Framework | Metasploit | |
| Network Monitoring | Ettercap | |
| Wireless Discovery | NetStumbler | |

---

# Summary Table

| Ethical Hacking Phase | Tool Used | Purpose |
|------------------------|-----------|---------|
| Reconnaissance | Angry IP Scanner | Identify live hosts |
| Scanning | Nmap | Scan ports and services |
| Web Security Testing | Burp Suite | Inspect HTTP requests |
| Vulnerability Assessment | LANguard | Identify vulnerabilities |
| Exploitation | Metasploit | Study exploit modules |
| Network Monitoring | Ettercap | Observe network devices |
| Wireless Discovery | NetStumbler | Detect Wi-Fi networks |

---

# Result

The Ethical Hacking Methodology was studied successfully. The basic functionality of commonly used ethical hacking tools was demonstrated, and each tool was mapped to the appropriate phase of the penetration testing lifecycle.

---

# Precautions

1. Perform all activities only in an authorized laboratory environment.
2. Never scan public or unauthorized networks.
3. Do not exploit vulnerabilities on production systems.
4. Use virtual machines whenever possible.
5. Follow ethical hacking guidelines and institutional policies.

---

# Viva Questions

1. What is Ethical Hacking?
2. Explain the phases of Ethical Hacking Methodology.
3. What is the purpose of Nmap?
4. Differentiate between Reconnaissance and Scanning.
5. What information can be obtained using Angry IP Scanner?
6. What is Burp Suite used for?
7. What is the purpose of the Metasploit Framework?
8. What is a vulnerability scanner?
9. Explain the role of Ettercap in network security.
10. Why is reporting considered the final and most important phase of Ethical Hacking?

---

# Conclusion

This experiment introduced the Ethical Hacking Methodology and familiarized students with commonly used ethical hacking tools. Students learned how each tool supports different stages of a security assessment, including host discovery, network scanning, web application analysis, vulnerability assessment, penetration testing, network monitoring, and wireless network discovery.