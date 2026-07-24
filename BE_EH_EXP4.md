# Experiment 4
# Web Server Vulnerabilities and Exploitation: DoS Attack Demonstration and Preventive Measures

## Aim

To understand the concept of Denial of Service (DoS) attacks by performing a controlled demonstration on a Windows server in a virtual laboratory environment and implement appropriate preventive measures.

---

## Course Outcome Mapping

**CO3:** Measure the performance and troubleshoot cyber security systems.

---

## Prerequisites

Students should be familiar with:

- Computer Networks
- TCP/IP Protocol Suite
- Windows Operating System
- Client-Server Architecture
- Basic Cyber Security Concepts
- Virtual Machines (VMware/VirtualBox)

---

# Theory

A **Denial of Service (DoS)** attack is a cyber attack in which an attacker attempts to make a computer, server, or network resource unavailable to legitimate users by overwhelming it with excessive requests.

The primary objective is **service disruption**, not data theft.

A DoS attack generally targets:

- Web Servers
- Database Servers
- DNS Servers
- Email Servers
- Network Devices

---

# DoS Attack Lifecycle

```
Attacker
    │
    ▼
Large Number of Requests
    │
    ▼
Server Resources Exhausted
    │
    ▼
Legitimate Users Denied Service
```

---

# Types of DoS Attacks

### 1. SYN Flood

- Exploits the TCP three-way handshake.
- Consumes server connection resources.

### 2. ICMP Flood

- Sends excessive ICMP Echo Requests (Ping).

### 3. UDP Flood

- Floods the target with UDP packets.

### 4. HTTP Flood

- Generates a large number of HTTP requests to overload a web server.

---

# DoS vs DDoS

| DoS | DDoS |
|------|-------|
| Single attacking system | Multiple attacking systems |
| Easier to detect | Difficult to detect |
| Lower traffic volume | Extremely high traffic volume |
| Limited impact | Large-scale impact |

---

# Practical Scenario

You are working as a Security Analyst.

The system administrator has observed that users are unable to access the organization's internal web server during peak hours.

You are required to:

- Simulate a controlled DoS attack in a virtual lab.
- Monitor server performance.
- Identify the impact of the attack.
- Recommend suitable preventive measures.

> **Important:** Perform this experiment **only in an isolated virtual laboratory environment.** Never perform DoS attacks on public or production systems.

---

# Software Requirements

| Tool | Purpose |
|------|---------|
| Windows Server / Windows 10 VM | Target Machine |
| Kali Linux VM | Attacking Machine |
| hping3 | Packet Generation |
| Apache / IIS Web Server | Target Service |
| Task Manager / Resource Monitor | Monitor CPU, RAM, Network |
| Wireshark | Packet Analysis |

---

# Network Setup

```
Kali Linux VM
      │
      │
Virtual Network
      │
      ▼
Windows Server VM
Running Apache / IIS
```

---

# Procedure

## Activity 1 – Verify Connectivity

### Steps

Check communication between attacker and target.

```bash
ping <Target-IP>
```

Example

```bash
ping 192.168.56.101
```

### Expected Output

Students should observe:

- Successful Ping Reply
- Network Connectivity

---

## Activity 2 – Monitor Server Performance

On the Windows server:

Open:

```
Task Manager
```

or

```
Resource Monitor
```

Observe:

- CPU Usage
- Memory Usage
- Network Utilization

Record the values before starting the attack.

---

## Activity 3 – Demonstration of SYN Flood (Controlled)

### Tool Used

hping3

Execute the following command from Kali Linux:

```bash
sudo hping3 -S --flood -V <Target-IP>
```

Example

```bash
sudo hping3 -S --flood -V 192.168.56.101
```

Allow the demonstration to run for a short duration (30–60 seconds), then stop it using **Ctrl + C**.

### Expected Output

Students should observe:

- Large number of SYN packets transmitted.
- Increased CPU and network usage on the server.
- Possible slowdown in server response.

---

## Activity 4 – Analyze Traffic Using Wireshark

### Tool Used

Wireshark

Steps:

1. Start packet capture.
2. Repeat the SYN flood demonstration.
3. Stop packet capture.
4. Apply the following filter:

```
tcp.flags.syn == 1
```

### Expected Output

Students should observe:

- Continuous SYN packets.
- Large number of incomplete TCP connection requests.

---

## Activity 5 – Observe Server Performance

Record the following observations during the attack.

| Parameter | Before Attack | During Attack |
|-----------|---------------|---------------|
| CPU Usage | | |
| Memory Usage | | |
| Network Usage | | |
| Server Response | | |

---

## Activity 6 – Study Preventive Measures

Study the following mitigation techniques:

- Firewall Rules
- SYN Cookies
- Intrusion Detection Systems (IDS)
- Intrusion Prevention Systems (IPS)
- Rate Limiting
- Load Balancing
- Reverse Proxy
- Web Application Firewall (WAF)
- Network Monitoring
- DDoS Protection Services

Discuss how each technique helps reduce the impact of DoS attacks.

---

# Observation Table

| Activity | Tool Used | Observation |
|-----------|-----------|-------------|
| Connectivity Test | Ping | |
| Resource Monitoring | Task Manager | |
| SYN Flood | hping3 | |
| Packet Analysis | Wireshark | |
| Preventive Measures | Study | |

---

# Summary Table

| Activity | Tool | Purpose |
|----------|------|---------|
| Connectivity Verification | Ping | Verify communication |
| Resource Monitoring | Task Manager | Observe system performance |
| SYN Flood Demonstration | hping3 | Simulate DoS attack |
| Packet Analysis | Wireshark | Analyze network traffic |
| Countermeasures | Firewall, IDS, WAF | Protect against DoS attacks |

---

# Result

A controlled DoS attack was demonstrated in an isolated virtual laboratory environment. The impact of excessive SYN requests on server performance was observed using system monitoring tools and Wireshark. Various preventive measures against DoS attacks were studied and discussed.

---

# Precautions

- Perform this experiment only in an isolated virtual lab.
- Never launch DoS attacks against public or production servers.
- Stop the attack immediately after observation.
- Monitor resource usage continuously.
- Use only authorized systems.
- Follow institutional ethical hacking policies.

---

# Viva Questions

1. What is a Denial of Service (DoS) attack?
2. Differentiate between DoS and DDoS.
3. What is a SYN Flood attack?
4. Which TCP flag is abused in a SYN Flood attack?
5. What is the purpose of Wireshark in this experiment?
6. How can Task Manager help identify a DoS attack?
7. What are SYN Cookies?
8. Name four techniques used to prevent DoS attacks.
9. Why should DoS demonstrations be performed only in virtual environments?
10. Explain the role of IDS and IPS in mitigating DoS attacks.

---

# Conclusion

This experiment demonstrated the working principle of a Denial of Service attack in a controlled virtual environment. Students observed the effect of excessive network requests on server performance, analyzed network traffic using Wireshark, and studied industry-standard techniques for preventing and mitigating DoS attacks.