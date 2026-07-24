# Experiment 9
# Network Traffic Capture and Analysis Using Wireshark

## Aim

To capture live network traffic using Wireshark, analyze common network protocols, and interpret packet-level communication in an authorized laboratory environment.

---

## Course Outcome Mapping

**CO6:** Prepare penetration report.

> **Note:** This experiment focuses on packet capture and protocol analysis, which serves as the foundation for preparing network security reports.

---

## Prerequisites

Students should be familiar with:

- TCP/IP Protocol Suite
- OSI Model
- HTTP and HTTPS
- DNS
- ICMP
- Basic Networking
- Windows or Linux Operating System

---

# Theory

Wireshark is one of the most widely used network protocol analyzers. It captures packets transmitted over a network interface and provides detailed information about network communication.

Security professionals use Wireshark for:

- Network Troubleshooting
- Protocol Analysis
- Performance Monitoring
- Incident Response
- Digital Forensics
- Malware Investigation

---

# Packet Capture Workflow

```
Network Traffic
       │
       ▼
Network Interface
       │
       ▼
Wireshark Capture
       │
       ▼
Protocol Analysis
       │
       ▼
Security Report
```

---

# Common Network Protocols

### ICMP

Used for diagnostic communication.

Example:

- Ping
- Echo Request
- Echo Reply

---

### DNS

Resolves domain names into IP addresses.

Example:

```
www.google.com
```

↓

```
142.x.x.x
```

---

### HTTP

Transfers web pages using plain text.

Default Port:

```
80
```

---

### HTTPS

Secure version of HTTP using TLS.

Default Port:

```
443
```

---

### TCP

Provides reliable communication.

Features:

- Connection Oriented
- Error Detection
- Flow Control

---

### UDP

Provides faster communication.

Features:

- Connectionless
- Low Overhead
- No Delivery Guarantee

---

# Practical Scenario

You are working as a Network Security Analyst.

Your organization wants to understand the traffic flowing through its network.

You are required to:

- Capture packets.
- Analyze different protocols.
- Apply display filters.
- Identify communication patterns.
- Prepare a summary of observations.

---

# Software Requirements

| Tool | Purpose |
|------|---------|
| Wireshark | Packet Capture and Analysis |
| Windows / Linux | Host Machine |
| Internet Connection | Generate Network Traffic |
| Web Browser | Generate HTTP/HTTPS Requests |

---

# Procedure

## Activity 1 – Start Packet Capture

Launch Wireshark.

Select the active network interface.

Click **Start Capture**.

Generate network traffic by:

- Opening websites
- Pinging another system
- Browsing web pages

Stop the capture after one to two minutes.

---

### Expected Output

Students should observe:

- Live packets
- Source and Destination IP Addresses
- Protocol Types

---

## Activity 2 – Analyze ICMP Traffic

Open Command Prompt or Terminal.

Execute:

```bash
ping google.com
```

Apply the display filter:

```
icmp
```

---

### Expected Output

Students should observe:

- Echo Request
- Echo Reply
- Source IP
- Destination IP

---

## Activity 3 – Analyze DNS Traffic

Apply the display filter:

```
dns
```

Visit several websites.

Observe:

- DNS Query
- DNS Response
- Domain Name
- Resolved IP Address

---

### Expected Output

Students should identify DNS resolution requests.

---

## Activity 4 – Analyze HTTP Traffic

If HTTP traffic is available, apply:

```
http
```

Observe:

- GET Request
- POST Request
- Response Code
- Headers

---

### Expected Output

Students should identify web requests and responses.

---

## Activity 5 – Analyze HTTPS Traffic

Apply the filter:

```
tls
```

or

```
ssl
```

Observe:

- TLS Handshake
- Client Hello
- Server Hello
- Certificate Exchange

---

### Expected Output

Students should observe encrypted communication.

---

## Activity 6 – Analyze TCP Connections

Apply the filter:

```
tcp
```

Observe:

- Source Port
- Destination Port
- Sequence Number
- Acknowledgement Number

---

### Expected Output

Students should identify TCP communication between hosts.

---

## Activity 7 – Analyze UDP Traffic

Apply the filter:

```
udp
```

Observe:

- Source Port
- Destination Port
- Packet Length

---

### Expected Output

Students should identify UDP-based communication.

---

## Activity 8 – Apply Display Filters

Apply the following filters one by one.

```
icmp
```

```
dns
```

```
http
```

```
tls
```

```
tcp
```

```
udp
```

Observe how Wireshark filters packets based on protocol.

---

# Observation Table

| Activity | Filter Used | Observation |
|-----------|-------------|-------------|
| ICMP Analysis | icmp | |
| DNS Analysis | dns | |
| HTTP Analysis | http | |
| HTTPS Analysis | tls | |
| TCP Analysis | tcp | |
| UDP Analysis | udp | |

---

# Summary Table

| Protocol | Default Port | Purpose |
|----------|-------------|---------|
| ICMP | — | Diagnostics |
| DNS | 53 | Name Resolution |
| HTTP | 80 | Web Communication |
| HTTPS | 443 | Secure Web Communication |
| TCP | Various | Reliable Transport |
| UDP | Various | Fast Transport |

---

# Result

Live network traffic was successfully captured using Wireshark. Various protocols including ICMP, DNS, HTTP, HTTPS, TCP, and UDP were analyzed using display filters. The captured packets were examined to understand network communication and document observations for security analysis.

---

# Precautions

- Capture traffic only on authorized systems.
- Avoid capturing sensitive production traffic.
- Use a controlled laboratory environment.
- Do not share packet capture files containing confidential information.
- Follow institutional ethical hacking policies.

---

# Viva Questions

1. What is Wireshark?
2. What is packet sniffing?
3. Differentiate between capture filters and display filters.
4. What is the purpose of DNS?
5. What is ICMP used for?
6. Which protocol uses port 80?
7. Which protocol uses port 443?
8. How do TCP and UDP differ?
9. What information can be obtained from a packet capture?
10. Why is Wireshark widely used in network security?

---

# Conclusion

This experiment introduced students to network packet capture and protocol analysis using Wireshark. Students captured live traffic, analyzed commonly used network protocols, applied display filters, and interpreted packet-level communication, providing a strong foundation for network troubleshooting, security monitoring, and digital forensics.