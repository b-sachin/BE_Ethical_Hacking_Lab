# Experiment 7
# Network Scanning Using Nmap: ACK, SYN, FIN, NULL, and XMAS Port Scans

## Aim

To understand different TCP port scanning techniques and perform various Nmap scans (ACK, SYN, FIN, NULL, and XMAS) to analyze the state of target ports in an authorized laboratory environment.

---

## Course Outcome Mapping

**CO5:** Demonstrate mobile hacking and implement its countermeasures.

> **Note:** As per the prescribed university laboratory syllabus, this experiment is mapped to **CO5**.

---


## Prerequisites

Students should be familiar with:

- TCP/IP Protocol Suite
- TCP Three-Way Handshake
- Ports and Services
- Linux Commands
- Basic Networking
- Nmap Basics

---

# Theory

Port scanning is one of the most important phases of network reconnaissance. It helps identify open ports, running services, and potential entry points into a target system.

Nmap (Network Mapper) is one of the most widely used network scanning tools used by network administrators and penetration testers.

Different scanning techniques send different TCP flags to determine the status of ports while attempting to remain less detectable than a standard TCP connection.

---

# TCP Three-Way Handshake

```
Client                  Server

SYN  -------------------->

     <-------------------- SYN + ACK

ACK  -------------------->
```

A complete TCP connection is established after the three-way handshake.

---

# Types of Port Scans

## 1. SYN Scan

Also called **Half-Open Scan**.

- Sends SYN packet.
- Does not complete the TCP handshake.
- Faster than a full TCP connection.
- Difficult to detect.

Command:

```bash
nmap -sS <Target-IP>
```

---

## 2. ACK Scan

Used to determine firewall rules and packet filtering.

Command:

```bash
nmap -sA <Target-IP>
```

---

## 3. FIN Scan

Sends a TCP packet with only the FIN flag set.

Open ports generally ignore the packet, while closed ports return an RST response.

Command:

```bash
nmap -sF <Target-IP>
```

---

## 4. NULL Scan

Sends a packet without any TCP flags.

Command:

```bash
nmap -sN <Target-IP>
```

---

## 5. XMAS Scan

Sends packets with FIN, PSH, and URG flags set.

The packet appears "lit up" like a Christmas tree.

Command:

```bash
nmap -sX <Target-IP>
```

---

# Practical Scenario

You are working as a Security Analyst.

The organization has requested a network assessment to identify open ports, running services, and firewall behavior of laboratory systems.

You are required to perform multiple scanning techniques using Nmap and compare their results.

> **Important:** Perform all scans only on authorized laboratory systems.

---

# Software Requirements

| Tool | Purpose |
|------|---------|
| Kali Linux | Attacker Machine |
| Nmap | Port Scanning |
| Windows / Linux VM | Target Machine |
| Wireshark (Optional) | Packet Analysis |

---

# Network Setup

```
Kali Linux
      │
      │
Virtual Network
      │
      ▼
Windows/Linux Target
```

---

# Procedure

## Activity 1 – Verify Connectivity

Check communication with the target system.

```bash
ping <Target-IP>
```

Example

```bash
ping 192.168.56.101
```

### Expected Output

- Successful Ping Reply
- Network Connectivity Verified

---

## Activity 2 – Perform SYN Scan

Execute:

```bash
nmap -sS <Target-IP>
```

Example

```bash
nmap -sS 192.168.56.101
```

### Expected Output

Students should observe:

- Open Ports
- Closed Ports
- Filtered Ports

---

## Activity 3 – Perform ACK Scan

Execute:

```bash
nmap -sA <Target-IP>
```

### Expected Output

Students should observe:

- Firewall Detection
- Filtered / Unfiltered Ports

---

## Activity 4 – Perform FIN Scan

Execute:

```bash
nmap -sF <Target-IP>
```

### Expected Output

Students should observe:

- Open|Filtered Ports
- Closed Ports

---

## Activity 5 – Perform NULL Scan

Execute:

```bash
nmap -sN <Target-IP>
```

### Expected Output

Students should observe:

- Open|Filtered Ports
- Closed Ports

---

## Activity 6 – Perform XMAS Scan

Execute:

```bash
nmap -sX <Target-IP>
```

### Expected Output

Students should observe:

- Open|Filtered Ports
- Closed Ports

---

## Activity 7 – Compare Scan Results

Record the results obtained from each scanning technique.

| Scan Type | Open Ports | Closed Ports | Filtered Ports |
|-----------|------------|--------------|----------------|
| SYN Scan | | | |
| ACK Scan | | | |
| FIN Scan | | | |
| NULL Scan | | | |
| XMAS Scan | | | |

---

## Activity 8 – Study Countermeasures

Study the following security measures used to detect or prevent unauthorized scanning.

- Firewall Rules
- Intrusion Detection System (IDS)
- Intrusion Prevention System (IPS)
- Port Filtering
- Network Monitoring
- Rate Limiting
- Logging and Alerting

Discuss how each mechanism helps protect a network.

---

# Observation Table

| Activity | Tool Used | Observation |
|-----------|-----------|-------------|
| Connectivity Test | Ping | |
| SYN Scan | Nmap | |
| ACK Scan | Nmap | |
| FIN Scan | Nmap | |
| NULL Scan | Nmap | |
| XMAS Scan | Nmap | |

---

# Summary Table

| Scan Type | Command | Purpose |
|-----------|---------|---------|
| SYN Scan | `nmap -sS` | Half-open TCP scan |
| ACK Scan | `nmap -sA` | Firewall detection |
| FIN Scan | `nmap -sF` | Stealth scan |
| NULL Scan | `nmap -sN` | Stealth scan |
| XMAS Scan | `nmap -sX` | Stealth scan |

---

# Result

Various TCP port scanning techniques were successfully performed using Nmap. The responses obtained from SYN, ACK, FIN, NULL, and XMAS scans were analyzed to understand port states and firewall behavior. The effectiveness and limitations of each scanning technique were also studied.

---

# Precautions

- Perform scans only on authorized laboratory systems.
- Never scan public or production networks without permission.
- Use virtual machines whenever possible.
- Record scan observations carefully.
- Follow institutional ethical hacking policies.

---

# Viva Questions

1. What is port scanning?
2. What is the purpose of Nmap?
3. Differentiate between SYN Scan and ACK Scan.
4. Why is SYN Scan called a Half-Open Scan?
5. What is the purpose of an ACK Scan?
6. Explain FIN Scan.
7. Explain NULL Scan.
8. Why is it called an XMAS Scan?
9. Which scan is commonly used for firewall detection?
10. Name four countermeasures against unauthorized port scanning.

---

# Conclusion

This experiment introduced students to various TCP port scanning techniques using Nmap. By performing SYN, ACK, FIN, NULL, and XMAS scans, students learned how different TCP flags affect scan results and how these techniques are used during network reconnaissance. The experiment also emphasized the importance of implementing security mechanisms to detect and prevent unauthorized scanning activities.