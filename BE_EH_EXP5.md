# Experiment 5
# Metasploit Framework: ARP Poisoning Demonstration in a Windows Network

## Aim

To understand the concept of ARP Spoofing (ARP Poisoning) by performing a controlled Man-in-the-Middle (MITM) attack in a virtual laboratory environment using Ettercap and analyze the associated security risks and countermeasures.

---

## Course Outcome Mapping

**CO4:** Implement and demonstrate security attacks in Metasploit framework.

---

## Prerequisites

Students should be familiar with:

- TCP/IP Protocol Suite
- MAC Address and IP Address
- LAN Communication
- Ethernet
- Kali Linux
- Windows Operating System
- Wireshark Basics

---

# Theory

The **Address Resolution Protocol (ARP)** is used to map an IPv4 address to a physical MAC address within a Local Area Network (LAN).

Whenever a computer wants to communicate with another system on the same network, it first checks its ARP cache. If the MAC address is unknown, it broadcasts an ARP Request.

Example:

```
Who has 192.168.1.20?
Tell 192.168.1.10
```

The target replies with its MAC address.

---

# What is ARP Poisoning?

ARP Poisoning (ARP Spoofing) is a Man-in-the-Middle (MITM) attack in which an attacker sends forged ARP replies to associate their MAC address with another device's IP address.

As a result, network traffic intended for the victim is redirected through the attacker's system.

---

# Working of ARP Poisoning

```
Victim PC
     │
     │
     ▼
Attacker
(Forged ARP Replies)
     │
     ▼
Gateway / Router
```

The attacker becomes the intermediary between the victim and the gateway.

---

# Risks of ARP Poisoning

- Packet Sniffing
- Session Hijacking
- Credential Theft
- Data Manipulation
- Denial of Service

---

# Practical Scenario

You are working as a Network Security Analyst.

The organization wants to understand how ARP Spoofing affects communication inside a LAN so that appropriate security mechanisms can be implemented.

Your tasks are to:

- Perform ARP Poisoning in a virtual laboratory.
- Observe changes in ARP tables.
- Capture redirected traffic.
- Study preventive measures.

> **Important:** Perform this experiment only in an isolated virtual laboratory environment.

---

# Software Requirements

| Tool | Purpose |
|------|---------|
| Kali Linux | Attacking Machine |
| Windows 10 VM | Victim Machine |
| Virtual Router / Gateway | Network Gateway |
| Ettercap | ARP Poisoning |
| Wireshark | Packet Capture |
| Command Prompt | ARP Table Verification |

---

# Network Setup

```
               Virtual Network

      Windows Victim
             │
             │
      ------------------
             │
        Kali Linux
        (Attacker)
             │
      ------------------
             │
      Gateway / Router
```

---

# Procedure

## Activity 1 – Verify Network Connectivity

### Steps

Identify the IP address of both systems.

Windows

```cmd
ipconfig
```

Kali Linux

```bash
ip addr
```

Verify connectivity.

```bash
ping <Victim-IP>
```

### Expected Output

Students should observe:

- Successful Ping
- IP Addresses
- MAC Addresses

---

## Activity 2 – View ARP Cache

On the Windows machine

```cmd
arp -a
```

Observe:

- IP Address
- Physical Address (MAC)
- Interface

Record the gateway MAC address before the attack.

---

## Activity 3 – Perform ARP Poisoning

### Tool Used

Ettercap

Launch Ettercap with root privileges.

```bash
sudo ettercap -G
```

Steps

1. Select the network interface.
2. Perform Host Scan.
3. Add the victim as **Target 1**.
4. Add the gateway as **Target 2**.
5. Navigate to:

```
Mitm
→ ARP Poisoning
```

Enable:

- Sniff Remote Connections

Start the attack.

---

### Expected Output

Students should observe:

- Successful ARP Poisoning
- Traffic redirected through attacker
- Active MITM session

---

## Activity 4 – Capture Network Traffic

### Tool Used

Wireshark

Steps

1. Start packet capture.
2. Generate web traffic from the victim machine.
3. Stop packet capture.

Observe:

- HTTP Packets
- DNS Requests
- TCP Connections

---

### Expected Output

Students should observe:

- Network packets flowing through the attacker.
- Protocol details.
- Source and destination addresses.

---

## Activity 5 – Verify Modified ARP Table

Again execute:

```cmd
arp -a
```

Compare the MAC address with the previous observation.

Students should identify the modified ARP entries.

---

## Activity 6 – Study Countermeasures

Study the following protection mechanisms.

- Static ARP Entries
- Dynamic ARP Inspection (DAI)
- DHCP Snooping
- Port Security
- Secure Switch Configuration
- VPN
- HTTPS
- Network Segmentation

Discuss how each mechanism helps prevent ARP Spoofing.

---

# Observation Table

| Activity | Tool Used | Observation |
|-----------|-----------|-------------|
| Network Verification | Ping | |
| ARP Table Before Attack | arp | |
| ARP Poisoning | Ettercap | |
| Packet Capture | Wireshark | |
| ARP Table After Attack | arp | |
| Security Measures | Study | |

---

# Summary Table

| Activity | Tool | Purpose |
|----------|------|---------|
| Network Verification | Ping | Verify connectivity |
| ARP Cache Analysis | arp | View MAC-IP mapping |
| ARP Poisoning | Ettercap | Demonstrate MITM attack |
| Packet Capture | Wireshark | Analyze intercepted traffic |
| Countermeasures | DAI, Static ARP, VPN | Prevent ARP Spoofing |

---

# Result

ARP Poisoning was successfully demonstrated in an isolated virtual laboratory environment using Ettercap. The changes in the ARP table and redirected network traffic were observed. Appropriate security mechanisms to mitigate ARP Spoofing attacks were also studied.

---

# Precautions

- Perform the experiment only in an isolated virtual network.
- Never perform ARP Poisoning on public or production networks.
- Stop packet capture after completing the experiment.
- Restore normal network configuration after the experiment.
- Follow institutional ethical hacking guidelines.

---

# Viva Questions

1. What is ARP?
2. What is the purpose of the ARP protocol?
3. Explain ARP Poisoning.
4. What is a Man-in-the-Middle attack?
5. What is the role of Ettercap?
6. How can Wireshark help during ARP Poisoning?
7. What changes occur in the ARP cache after poisoning?
8. What is Dynamic ARP Inspection (DAI)?
9. Name four countermeasures against ARP Spoofing.
10. Why should ARP Poisoning be demonstrated only in a virtual laboratory?

---

# Conclusion

This experiment demonstrated the working of ARP Poisoning in a controlled virtual environment. Students observed how forged ARP replies enable a Man-in-the-Middle attack, analyzed intercepted network traffic, and studied effective techniques for preventing ARP Spoofing attacks in enterprise networks.