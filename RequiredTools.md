# Installation of Required Tools

> **Note:** Install these tools only on your personal computer or an authorized laboratory machine. Do not use them on unauthorized networks or systems.

---

## 1. Nmap

### Windows

1. Visit: https://nmap.org/download.html
2. Download the latest Windows installer.
3. Run the installer.
4. Keep default settings.
5. Verify installation:

```bash
nmap --version
```

---

## 2. Angry IP Scanner

### Windows/Linux/macOS

1. Visit: https://angryip.org/
2. Download the installer.
3. Install using default settings.
4. Launch Angry IP Scanner.

---

## 3. Burp Suite Community Edition

1. Visit:
https://portswigger.net/burp/communitydownload

2. Download Community Edition.

3. Install.

4. Launch Burp Suite.

---

## 4. Metasploit Framework

### Kali Linux

Already Installed.

Verify

```bash
msfconsole
```

### Ubuntu

```bash
curl https://raw.githubusercontent.com/rapid7/metasploit-framework/master/msfinstall | sudo bash
```

Verify

```bash
msfconsole
```

---

## 5. Ettercap

### Kali Linux

```bash
sudo apt update
sudo apt install ettercap-graphical
```

Launch

```bash
ettercap -G
```

---

## 6. NetStumbler

Download from the official website or use an equivalent Wi-Fi scanner such as:

- Acrylic Wi-Fi Home
- inSSIDer
- WiFi Analyzer

Install using default settings.

---

## 7. GFI LANguard

1. Download the installer from the official website.
2. Install using default options.
3. Activate the evaluation license (if applicable).
4. Launch the application.

---

## Verification

Verify successful installation of each tool before starting the experiment.

| Tool | Verification |
|------|--------------|
| Nmap | `nmap --version` |
| Metasploit | `msfconsole` |
| Burp Suite | Launch GUI |
| Angry IP Scanner | Launch GUI |
| Ettercap | `ettercap -G` |
| LANguard | Launch Application |
| NetStumbler | Launch Application |