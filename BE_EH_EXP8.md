# Experiment 8
# Session Impersonation Using Burp Suite and Firefox

## Aim

To understand session management in web applications by demonstrating session impersonation through HTTP cookie manipulation using Burp Suite Community Edition in a controlled laboratory environment.

---

## Course Outcome Mapping

**CO5:** Demonstrate mobile hacking and implement its countermeasures.

> **Note:** This experiment replaces the obsolete Firefox Tamper Data add-on with **Burp Suite Community Edition**, while achieving the same learning objectives specified in the syllabus.

---

## Learning Objectives

After successful completion of this experiment, students will be able to:

- Understand web session management.
- Explain the role of cookies and session identifiers.
- Capture HTTP requests using Burp Suite.
- Observe session cookies exchanged between client and server.
- Demonstrate session impersonation in a controlled environment.
- Recommend secure session management practices.

---

## Prerequisites

Students should be familiar with:

- HTTP and HTTPS
- Web Browsers
- Cookies
- Authentication
- Burp Suite Basics
- Firefox Browser

---

# Theory

Most web applications identify authenticated users using **Session IDs** stored inside HTTP cookies.

Typical authentication process:

```
User Login
      │
      ▼
Server Verifies Credentials
      │
      ▼
Session ID Generated
      │
      ▼
Cookie Sent to Browser
      │
      ▼
Browser Sends Cookie
with Every Request
```

If an attacker obtains another user's session identifier, the attacker may impersonate that user without knowing the password.

This attack is known as **Session Hijacking** or **Session Impersonation**.

---

# Session Cookie Example

```
Cookie:

PHPSESSID=3f82cb27d914f6d5c41a
```

Every subsequent request contains:

```
Cookie: PHPSESSID=3f82cb27d914f6d5c41a
```

---

# Common Causes of Session Hijacking

- Insecure HTTP
- Cookie Theft
- Cross Site Scripting (XSS)
- Session Fixation
- Weak Session IDs
- Malware
- Public Wi-Fi

---

# Practical Scenario

You are working as a Web Security Analyst.

A development team wants to understand how insecure session management can lead to account impersonation.

Your tasks are to:

- Capture HTTP requests.
- Observe session cookies.
- Demonstrate controlled session impersonation.
- Study preventive measures.

> **Important:** Perform this experiment only on intentionally vulnerable web applications such as DVWA, OWASP Juice Shop, or bWAPP.

---

# Software Requirements

| Tool | Purpose |
|------|---------|
| Firefox Browser | Web Browser |
| Burp Suite Community Edition | HTTP Proxy |
| DVWA / Juice Shop / bWAPP | Vulnerable Web Application |
| Kali Linux | Testing Platform |

---

# Procedure

## Activity 1 – Configure Burp Suite

1. Launch Burp Suite.
2. Open Firefox.
3. Configure browser proxy.

```
IP Address : 127.0.0.1

Port : 8080
```

4. Turn **Intercept ON**.

---

### Expected Output

Students should observe:

- Browser traffic intercepted.
- HTTP requests displayed.

---

## Activity 2 – Login to Vulnerable Web Application

Open:

```
http://<Target-IP>/dvwa
```

Login using instructor-provided credentials.

Observe:

- Login Request
- HTTP Headers
- Cookies

---

### Expected Output

Students should observe:

- POST Request
- Response Headers
- Session Cookie

---

## Activity 3 – Capture Session Cookie

In Burp Suite

Navigate to:

```
Proxy
→ HTTP History
```

Locate:

```
Cookie:
```

Record the session identifier.

---

### Expected Output

Students should observe:

- Session Cookie
- Cookie Attributes
- Request Headers

---

## Activity 4 – Modify HTTP Request

Using Burp Suite Repeater:

1. Send captured request to Repeater.
2. Modify HTTP headers (only in the lab environment).
3. Replace the session cookie with another valid laboratory session ID provided by the instructor.
4. Forward the modified request.

---

### Expected Output

Students should observe:

- Modified HTTP Request
- Server Response
- Effect of Session Cookie Modification

---

## Activity 5 – Analyze Session Security

Observe:

- Session ID Length
- Cookie Flags
- Secure Attribute
- HttpOnly Attribute
- SameSite Attribute

Record your observations.

---

## Activity 6 – Study Countermeasures

Discuss the following preventive techniques.

- HTTPS
- Secure Cookies
- HttpOnly Cookies
- SameSite Cookies
- Session Timeout
- Session Regeneration
- Multi-Factor Authentication (MFA)
- Strong Session IDs

---

# Observation Table

| Activity | Tool Used | Observation |
|-----------|-----------|-------------|
| Request Interception | Burp Suite | |
| Session Cookie | Burp Suite | |
| HTTP Headers | Burp Suite | |
| Modified Request | Repeater | |
| Cookie Attributes | Browser | |

---

# Summary Table

| Activity | Tool | Purpose |
|----------|------|---------|
| Intercept Requests | Burp Suite | Capture HTTP Traffic |
| Analyze Cookies | Burp Suite | Study Session Management |
| Modify Requests | Repeater | Observe Session Behavior |
| Countermeasures | Study | Improve Session Security |

---

# Result

Session management was studied using Burp Suite by observing HTTP requests and session cookies in a controlled laboratory environment. Students understood how insecure session handling can lead to session impersonation and learned industry-standard techniques to secure web application sessions.

---

# Precautions

- Perform the experiment only on intentionally vulnerable web applications.
- Never intercept or modify traffic belonging to unauthorized users.
- Use only laboratory credentials.
- Do not test public websites.
- Follow institutional ethical hacking policies.

---

# Viva Questions

1. What is session management?
2. What is a session cookie?
3. What is session hijacking?
4. Differentiate between authentication and session management.
5. What is the purpose of Burp Suite?
6. What is the HttpOnly cookie attribute?
7. What is the Secure cookie attribute?
8. What is SameSite?
9. How does HTTPS help protect sessions?
10. Name four countermeasures against session hijacking.

---

# Conclusion

This experiment demonstrated session management and session impersonation concepts using Burp Suite Community Edition in a controlled laboratory environment. Students observed how session cookies identify authenticated users and learned best practices such as Secure, HttpOnly, SameSite cookies, HTTPS, and session regeneration to protect web applications from session hijacking attacks.