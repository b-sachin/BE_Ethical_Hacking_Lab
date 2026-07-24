# Experiment 2
# Attacks and Countermeasures: Footprinting, RSA Cryptography and SQL Injection

## Aim

To understand information gathering techniques, demonstrate RSA encryption and decryption, and study SQL Injection attacks in a controlled environment while learning appropriate security countermeasures.

---

## Course Outcome Mapping

**CO2:** Conduct a web security attack and demonstration of attack detection techniques.

---

## Prerequisites

Students should be familiar with:

- Computer Networks
- TCP/IP Protocol Suite
- HTTP and HTTPS
- Basic Database Concepts
- SQL Queries
- Web Applications
- Basic Cryptography Concepts

---

# Theory

Ethical hackers collect information about target systems before attempting any security assessment. This process is called **Footprinting** or **Reconnaissance**. Once sufficient information is collected, vulnerabilities are identified and verified in an authorized environment.

Security professionals also use cryptographic techniques to protect sensitive information. One of the most widely used public-key cryptographic algorithms is **RSA**, which provides confidentiality and secure communication.

Modern web applications are highly dependent on databases. Improper validation of user input may lead to **SQL Injection**, allowing attackers to manipulate database queries. Understanding these attacks helps security professionals design secure applications.

---

# Part A – Footprinting and Reconnaissance

Footprinting is the process of collecting publicly available information about a target organization.

Information gathered may include:

- Domain Name
- IP Address
- DNS Records
- Email Addresses
- Technologies Used
- Web Server Information
- Network Information

Footprinting can be classified into:

### Passive Footprinting

Information is collected without directly interacting with the target.

Examples:

- Search Engines
- WHOIS Lookup
- DNS Records
- Public Websites

### Active Footprinting

Information is collected by directly communicating with the target.

Examples:

- Port Scanning
- Network Scanning
- Banner Grabbing
- Service Enumeration

---

# Part B – RSA Cryptography

RSA is an asymmetric encryption algorithm that uses two keys:

- Public Key
- Private Key

The Public Key is used for encryption, while the Private Key is used for decryption.

### Advantages

- Secure communication
- Digital Signatures
- Authentication
- Confidentiality

Applications include:

- HTTPS
- Secure Email
- VPN
- Digital Certificates

---

# Part C – SQL Injection

SQL Injection is one of the most common web application attacks.

It occurs when user input is directly included in SQL queries without proper validation.

Example of vulnerable query:

```sql
SELECT * FROM users
WHERE username='admin'
AND password='password';
```

If input validation is absent, an attacker may manipulate the SQL query.

Example:

```text
' OR '1'='1
```

This may modify the original query and bypass authentication in intentionally vulnerable applications.

---

# SQL Injection Prevention

Common countermeasures include:

- Parameterized Queries (Prepared Statements)
- Input Validation
- Stored Procedures
- Least Privilege Principle
- Web Application Firewall (WAF)
- Proper Error Handling

---

# Practical Scenario

You are working as a Cyber Security Analyst.

The organization has requested you to:

- Collect publicly available information about a target domain.
- Demonstrate RSA encryption and decryption.
- Study SQL Injection using a vulnerable web application.
- Recommend appropriate security countermeasures.

---

# Software Requirements

| Tool | Purpose |
|------|---------|
| Kali Linux | Penetration Testing Environment |
| whois | Domain Information |
| nslookup / dig | DNS Enumeration |
| theHarvester (Optional) | Email & Subdomain Discovery |
| Python 3 | RSA Demonstration |
| SQLite / MySQL | Database |
| XAMPP / Apache | Web Server |
| DVWA (Damn Vulnerable Web Application) or bWAPP | SQL Injection Practice |

> **Note:** Perform all experiments only in an authorized laboratory environment or virtual machine.

---

# Procedure

## Activity 1 – Footprinting and Reconnaissance

### Tool Used

- WHOIS
- nslookup
- dig (Linux)
- theHarvester (Optional)

### Steps

Display domain registration information.

```bash
whois example.com
```

Retrieve DNS records.

```bash
nslookup example.com
```

OR

```bash
dig example.com
```

(Optional)

Collect publicly available email addresses.

```bash
theHarvester -d example.com -b bing
```

### Expected Output

Students should observe:

- Domain Registrar
- Name Servers
- IP Address
- DNS Records
- Public Email Addresses (if available)
- Subdomains (if available)

---

## Activity 2 – RSA Encryption and Decryption

### Tool Used

Python 3

### Install Required Package

```bash
pip install rsa
```

### Sample Program

```python
import rsa

public_key, private_key = rsa.newkeys(512)

message = "Ethical Hacking Lab"

encrypted = rsa.encrypt(message.encode(), public_key)

print("Encrypted Message:")
print(encrypted)

decrypted = rsa.decrypt(encrypted, private_key)

print("Decrypted Message:")
print(decrypted.decode())
```

### Expected Output

Students should observe:

- Public Key Generated
- Private Key Generated
- Encrypted Message
- Successfully Decrypted Original Message

---

## Activity 3 – SQL Injection Demonstration

### Tool Used

DVWA (or bWAPP)

### Steps

Start Apache and MySQL.

Open DVWA.

Navigate to:

```
SQL Injection
```

Enter a normal input.

Example:

```
ID = 1
```

Observe the result.

Now try an SQL Injection payload.

Example:

```text
1' OR '1'='1
```

Observe how the application responds.

> **Note:** Perform SQL Injection only on intentionally vulnerable applications provided for educational purposes.

### Expected Output

Students should observe:

- Database Records Returned
- Modified SQL Query Behavior
- Vulnerability Demonstration

---

## Activity 4 – Study of SQL Injection Countermeasures

Study how prepared statements prevent SQL Injection.

### Vulnerable PHP Code

```php
$query = "SELECT * FROM users WHERE id = '$id'";
```

### Secure PHP Code

```php
$stmt = $conn->prepare("SELECT * FROM users WHERE id = ?");
$stmt->bind_param("i", $id);
```

### Expected Output

Students should understand:

- Difference between vulnerable and secure queries.
- Importance of parameterized statements.
- Prevention of SQL Injection attacks.

---

# Observation Table

| Activity | Tool Used | Observation |
|-----------|-----------|-------------|
| Footprinting | WHOIS / nslookup | |
| DNS Enumeration | nslookup / dig | |
| RSA Encryption | Python | |
| RSA Decryption | Python | |
| SQL Injection | DVWA / bWAPP | |
| SQL Injection Prevention | Prepared Statements | |

---

# Summary Table

| Activity | Tool | Purpose |
|----------|------|---------|
| Footprinting | WHOIS | Domain Information Gathering |
| DNS Enumeration | nslookup / dig | Retrieve DNS Records |
| Reconnaissance | theHarvester | Email and Subdomain Discovery |
| Cryptography | Python RSA | Encryption and Decryption |
| SQL Injection | DVWA | Study Web Vulnerability |
| Countermeasures | Prepared Statements | Prevent SQL Injection |

---

# Result

Information gathering techniques were successfully performed using footprinting tools. RSA encryption and decryption were demonstrated using Python, and SQL Injection was studied in a controlled vulnerable web application. Appropriate countermeasures for preventing SQL Injection attacks were also understood.

---

# Precautions

- Perform all activities only in an authorized laboratory environment.
- Never perform reconnaissance on unauthorized targets.
- Conduct SQL Injection only on intentionally vulnerable applications.
- Use virtual machines whenever possible.
- Never attack production servers.
- Follow ethical hacking guidelines and institutional policies.

---

# Viva Questions

1. What is Footprinting?
2. Differentiate between Passive and Active Footprinting.
3. What information can be obtained using WHOIS?
4. What is DNS Enumeration?
5. What is RSA Cryptography?
6. Differentiate between Public Key and Private Key.
7. What is SQL Injection?
8. Explain how SQL Injection works.
9. What are Prepared Statements?
10. List any four countermeasures against SQL Injection.

---

# Conclusion

This experiment introduced students to information gathering through footprinting and reconnaissance techniques, demonstrated RSA public-key cryptography for secure communication, and explored SQL Injection attacks in a controlled environment. Students also learned practical countermeasures to protect web applications against SQL Injection vulnerabilities.