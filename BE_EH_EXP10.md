# Experiment 10
# Network Traffic Analysis and Wireshark Challenges

## Aim

To analyze captured network traffic using Wireshark and solve packet analysis challenges by identifying network events, protocols, suspicious activities, and communication patterns from a packet capture (PCAP) file.

---

## Course Outcome Mapping

**CO6:** Prepare penetration report.

---

## Prerequisites

Students should be familiar with:

- TCP/IP Protocol Suite
- HTTP and HTTPS
- DNS
- ICMP
- TCP and UDP
- Wireshark Basics
- Display Filters

---

# Theory

Network traffic analysis is one of the most important skills in cybersecurity, digital forensics, and incident response. Instead of capturing live traffic, security analysts often investigate previously captured packet files (PCAP) to reconstruct events, detect attacks, and identify suspicious behavior.

Wireshark provides powerful filtering and analysis capabilities that allow investigators to inspect individual packets, conversations, and application-layer data.

---

# Practical Scenario

You are working as a Security Analyst.

Your organization has provided a packet capture file (PCAP) collected from a suspected compromised network. Your task is to analyze the capture and answer a series of investigation questions.

The instructor will provide a PCAP file for analysis.

---

# Software Requirements

| Tool | Purpose |
|------|---------|
| Wireshark | Packet Analysis |
| Sample PCAP File | Investigation |
| Windows / Linux | Host Machine |

---

# Procedure

## Activity 1 – Open the PCAP File

1. Launch Wireshark.
2. Select:

```
File → Open
```

3. Open the provided `.pcap` or `.pcapng` file.

---

### Expected Output

Students should observe:

- Total Packets
- Packet List
- Packet Details
- Packet Bytes

---

## Activity 2 – Identify Basic Capture Information

Determine:

- Total number of packets
- Capture duration
- Source IP addresses
- Destination IP addresses
- Network protocols present

Record your observations.

---

## Activity 3 – Apply Display Filters

Apply the following filters and observe the corresponding packets.

```
icmp
```

```
dns
```

```
tcp
```

```
udp
```

```
http
```

```
tls
```

```
arp
```

---

## Activity 4 – Follow TCP Stream

Select an HTTP or TCP packet.

Navigate to:

```
Right Click
→ Follow
→ TCP Stream
```

Observe:

- Complete conversation
- Request
- Response

---

## Activity 5 – Analyze DNS Traffic

Apply the filter:

```
dns
```

Identify:

- Queried domain names
- DNS server IP
- Returned IP addresses

---

## Activity 6 – Analyze HTTP Requests

Apply:

```
http
```

Identify:

- Requested URLs
- HTTP Methods
- Response Codes
- User-Agent

---

## Activity 7 – Analyze TLS Traffic

Apply:

```
tls
```

Observe:

- Client Hello
- Server Hello
- TLS Version
- Certificates (if available)

---

# Wireshark Investigation Challenges

Answer the following questions using the provided PCAP file.

### Challenge 1

What is the IP address of the client?

Answer:

______________________

---

### Challenge 2

What is the IP address of the server?

Answer:

______________________

---

### Challenge 3

Which protocol generated the highest number of packets?

Answer:

______________________

---

### Challenge 4

Which DNS server was used?

Answer:

______________________

---

### Challenge 5

How many HTTP GET requests were observed?

Answer:

______________________

---

### Challenge 6

Which website was accessed first?

Answer:

______________________

---

### Challenge 7

Which transport layer protocol was used most frequently?

Answer:

______________________

---

### Challenge 8

Was encrypted HTTPS traffic observed?

Answer:

Yes / No

---

### Challenge 9

How many TCP conversations were present?

Answer:

______________________

---

### Challenge 10

Was any suspicious or unusual activity observed?

Explain briefly.

_____________________________________________________

_____________________________________________________

---

# Observation Table

| Activity | Observation |
|-----------|-------------|
| Total Packets | |
| Protocols Observed | |
| Source IP | |
| Destination IP | |
| HTTP Requests | |
| DNS Queries | |
| TCP Streams | |
| Suspicious Activity | |

---

# Sample Investigation Report

| Parameter | Observation |
|------------|-------------|
| Capture File | |
| Date of Analysis | |
| Analyst Name | |
| Total Packets | |
| Major Protocols | |
| Suspicious Traffic | |
| Recommendations | |

---

# Result

The provided packet capture file was successfully analyzed using Wireshark. Network protocols, TCP streams, DNS queries, HTTP requests, and communication patterns were identified. The investigation challenges were completed, and the observations were documented in a structured analysis report.

---

# Precautions

- Analyze only instructor-provided packet capture files.
- Do not modify original PCAP files.
- Record observations carefully.
- Maintain confidentiality of captured network data.
- Follow institutional ethical hacking policies.

---

# Viva Questions

1. What is a PCAP file?
2. What is the purpose of Wireshark?
3. How do you follow a TCP stream?
4. What information can be obtained from DNS packets?
5. How can HTTP requests be identified?
6. What is the purpose of display filters?
7. Differentiate between TCP and UDP traffic in Wireshark.
8. How can suspicious traffic be detected?
9. What is network forensics?
10. Why is packet analysis important during incident response?

---

# Conclusion

This experiment provided hands-on experience in analyzing packet capture files using Wireshark. Students applied protocol filters, followed TCP streams, investigated DNS and HTTP communication, and solved practical network analysis challenges. The experiment reinforced the importance of packet analysis in cybersecurity, incident response, and digital forensics.