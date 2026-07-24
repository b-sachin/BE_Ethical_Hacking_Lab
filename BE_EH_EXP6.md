# Experiment 6
# Metasploit Framework: Vulnerability Assessment and Exploitation of Target Systems

## Aim

To understand the Metasploit Framework by identifying and safely verifying vulnerabilities on Windows, Linux, and Android target machines in a controlled laboratory environment.

---

## Course Outcome Mapping

**CO4:** Implement and demonstrate security attacks in Metasploit framework.

---

## Prerequisites

Students should be familiar with:

- Linux Commands
- TCP/IP Networking
- Windows and Linux Operating Systems
- Virtual Machines (VirtualBox / VMware)
- Nmap Basics
- Basic Vulnerability Assessment

---

# Theory

The **Metasploit Framework (MSF)** is an open-source penetration testing platform used to discover, verify, and validate security vulnerabilities.

It provides a collection of modules that assist security professionals throughout different phases of penetration testing.

The framework consists of:

- Exploits
- Payloads
- Auxiliary Modules
- Encoders
- Post-Exploitation Modules
- NOP Generators

Metasploit allows ethical hackers to safely verify vulnerabilities in authorized systems before recommending remediation.

---

# Metasploit Architecture

```
               Metasploit Framework
                       │
      ┌───────────────┼───────────────┐
      │               │               │
  Exploits       Auxiliary       Payloads
      │               │               │
      └───────────────┼───────────────┘
                      │
                 Target System
```

---

# Types of Modules

## Exploit Modules

Used to verify known vulnerabilities.

## Auxiliary Modules

Used for:

- Port Scanning
- Service Enumeration
- SMB Enumeration
- FTP Enumeration
- Vulnerability Checking

## Payloads

Code executed after successful exploitation.

Examples:

- Meterpreter
- Reverse TCP
- Bind TCP

## Post Modules

Used for post-exploitation activities on authorized systems.

---

# Practical Scenario

You are working as a Penetration Tester.

A client has requested a vulnerability verification of Windows, Linux, and Android laboratory machines.

You are required to:

- Scan the systems.
- Search for suitable Metasploit modules.
- Configure the modules.
- Verify vulnerabilities.
- Document your observations.

> **Important:** Perform this experiment only on intentionally vulnerable virtual machines such as Metasploitable 2/3, OWASP BWA, or other instructor-provided lab systems.

---

# Software Requirements

| Tool | Purpose |
|------|---------|
| Kali Linux | Attacker Machine |
| Metasploit Framework | Penetration Testing |
| Metasploitable 2 / 3 | Linux Target |
| Windows VM | Windows Target |
| Android Emulator / Android VM | Android Target |
| Nmap | Port Scanning |

---

# Network Setup

```
Kali Linux
      │
      │
Virtual Network
      │
      ├──────── Windows VM
      │
      ├──────── Linux VM
      │
      └──────── Android Emulator
```

---

# Procedure

## Activity 1 – Launch Metasploit

Open Terminal.

Start Metasploit.

```bash
msfconsole
```

### Expected Output

Students should observe:

- Metasploit Banner
- msf6 Prompt

---

## Activity 2 – Discover Target Services

Scan the target system using Nmap.

Example:

```bash
nmap -sV 192.168.56.101
```

Record:

- Open Ports
- Services
- Versions

---

## Activity 3 – Search for Exploit Modules

Example:

```bash
search smb
```

or

```bash
search ftp
```

or

```bash
search vsftpd
```

Observe the available exploit modules.

---

## Activity 4 – Configure an Exploit Module

Example:

```bash
use exploit/unix/ftp/vsftpd_234_backdoor
```

Display required parameters.

```bash
show options
```

Configure the target.

```bash
set RHOSTS 192.168.56.101
```

Verify the vulnerability.

```bash
check
```

> If the selected module does not support the `check` command, consult the module documentation or choose a module that supports safe vulnerability verification.

---

## Activity 5 – Configure a Payload

Display available payloads.

```bash
show payloads
```

Select a payload.

```bash
set payload cmd/unix/interact
```

Display the configuration.

```bash
show options
```

---

## Activity 6 – Study Meterpreter

Search for Meterpreter payloads.

```bash
search meterpreter
```

Observe:

- Reverse TCP
- Bind TCP
- HTTP Payloads
- HTTPS Payloads

Discuss the features of Meterpreter.

---

## Activity 7 – Analyze Results

Record:

- Target Operating System
- Open Services
- Exploit Module Used
- Payload Selected
- Vulnerability Verification Status
- Recommended Countermeasures

---

# Observation Table

| Activity | Tool Used | Observation |
|-----------|-----------|-------------|
| Launch Metasploit | msfconsole | |
| Service Discovery | Nmap | |
| Module Search | Metasploit | |
| Vulnerability Check | Metasploit | |
| Payload Configuration | Metasploit | |
| Result Analysis | Metasploit | |

---

# Summary Table

| Activity | Tool | Purpose |
|----------|------|---------|
| Start Framework | msfconsole | Launch Metasploit |
| Service Discovery | Nmap | Identify running services |
| Module Search | search | Find exploit modules |
| Vulnerability Verification | check | Verify vulnerability |
| Payload Configuration | show payloads | Study payload options |
| Result Analysis | Report | Document findings |

---

# Result

The Metasploit Framework was successfully used to identify and verify vulnerabilities on laboratory systems. Students learned how to search for exploit modules, configure targets and payloads, perform safe vulnerability verification, and analyze the results to recommend appropriate security measures.

---

# Precautions

- Perform the experiment only on authorized laboratory systems.
- Use intentionally vulnerable virtual machines.
- Do not target production or public systems.
- Prefer the `check` command to verify vulnerabilities whenever supported.
- Do not execute destructive exploits.
- Follow institutional ethical hacking policies.

---

# Viva Questions

1. What is the Metasploit Framework?
2. What are the major components of Metasploit?
3. Differentiate between Exploit and Payload.
4. What is the purpose of Auxiliary modules?
5. What is Meterpreter?
6. What is the function of the `search` command?
7. What information does the `show options` command provide?
8. Why is Nmap commonly used before Metasploit?
9. What is the purpose of the `check` command?
10. Why should penetration testing be performed only on authorized systems?

---

# Conclusion

This experiment introduced students to the Metasploit Framework for safe vulnerability verification in a controlled laboratory environment. Students learned how to discover services, identify suitable exploit modules, configure payloads, verify vulnerabilities, and document their findings while adhering to ethical hacking principles.