# 🌐 Ultimate Networking & Cybersecurity Fundamentals Notes  
### *(Complete Guide — Ports, IP Addressing, NAT, IPv6, Binary & Subnetting)*

---

## 📑 Table of Contents
1. [Ports & Protocols: The Digital Doors](#1-ports--protocols-the-digital-doors)  
2. [IPv4 Addressing: The Foundation](#2-ipv4-addressing-the-foundation)  
3. [IPv4 Crisis & Solutions (NAT & IPv6)](#3-ipv4-crisis--solutions-nat--ipv6)  
4. [Binary & Decimal Conversion](#4-binary--decimal-conversion-the-language-of-machines)  
5. [Subnetting: Designing Secure Networks](#5-subnetting-designing-secure-networks)

---

## 1. Ports & Protocols: The Digital Doors

### 1.1 What Are Ports?
A **port** is a logical communication endpoint on a device — like a specific **room number** inside a building.

- **IP Address → Building**
- **Port Number → Room inside the building**

**Range:** `0 – 65535`  
Used mainly in: **TCP** and **UDP**

| Range | Name | Usage |
|-------|-------|--------|
| 0–1023 | Well-Known Ports | System & core services |
| 1024–49151 | Registered Ports | Applications & vendors |
| 49152–65535 | Dynamic Ports | Temporary client connections |

### 1.2 Why Ports Matter in Cybersecurity
- Every **open port = attack surface**
- Attackers run **port scans** to detect:
  - Running services  
  - Software versions  
  - Vulnerabilities  
- Firewalls allow/deny traffic based on:
  - **Port**
  - **Protocol**
  - **IP**

A closed/filtered port → smaller attack surface.

### 1.3 TCP vs UDP (Cybersecurity View)

| Feature | TCP | UDP |
|---------|-----|-----|
| Connection | ✔ Connection-oriented | ❌ No connection |
| Reliability | ✔ Guaranteed delivery | ❌ Not guaranteed |
| Speed | Slow (overhead) | Fast (minimal overhead) |
| Examples | HTTP/S, SSH, FTP | DNS, VoIP, gaming, streaming |
| When to Use | Accuracy | Speed |

### 1.4 ⚠ Cybersecurity Essential Ports List (MEMORIZE THESE)

| Port | Proto | Service | Why Important |
|------|-------|---------|---------------|
| **20/21** | TCP | FTP | Insecure; plaintext creds |
| **22** | TCP | SSH | Secure login; brute-force target |
| **23** | TCP | Telnet | Fully insecure |
| **25** | TCP | SMTP | Email sending; spam attacks |
| **53** | TCP/UDP | DNS | DNS spoofing/poisoning risks |
| **67/68** | UDP | DHCP | Rogue DHCP attacks |
| **80** | TCP | HTTP | Web attack surface |
| **110** | TCP | POP3 | Email retrieval |
| **123** | UDP | NTP | DDoS amplification |
| **135–139** | TCP/UDP | NetBIOS | Windows exploitation |
| **143** | TCP | IMAP | Email sync |
| **161/162** | UDP | SNMP | Weak community strings |
| **389** | TCP/UDP | LDAP | Directory auth attacks |
| **443** | TCP | HTTPS | Secure web |
| **445** | TCP | SMB | WannaCry target |
| **3306** | TCP | MySQL | Database hacking |
| **3389** | TCP | RDP | Remote desktop hacking |
| **5900** | TCP | VNC | Weak remote desktop security |

### 1.5 What is a Protocol?
A **protocol** is a set of communication rules.

**Examples:**
- HTTP (web)
- DNS (names → IP)
- SSH (secure login)
- TCP/UDP (transport layer)

### 1.6 🔍 Port Scanning (Core Cyber Skill)

#### 🛠️ Popular Port Scanning Tools
- **Nmap** - Most comprehensive network scanner
- **Masscan** - Extremely fast Internet-scale scanner
- **RustScan** - Modern, fast port scanner written in Rust

#### 💻 Example Command
```bash
nmap -sV -O <target>
# -sV = Service version detection
# -O  = OS detection
## 2. IPv4 Addressing: The Foundation

### 2.1 Why IPv4 Is Limited
- **IPv4 = 32-bit addressing**
- **Total = 4.3 billion addresses** (not enough for modern internet)

### 2.2 Classful Addressing (Old System)

| Class | Range | Default Mask | Use |
|-------|-------|--------------|-----|
| A | 1.0.0.0 – 126.255.255.255 | /8 | Big networks |
| B | 128.0.0.0 – 191.255.255.255 | /16 | Medium networks |
| C | 192.0.0.0 – 223.255.255.255 | /24 | Small networks |
| D | 224.0.0.0 – 239.255.255.255 | N/A | Multicast |
| E | 240.0.0.0 – 255.255.255.255 | N/A | Experimental |

### 2.3 CIDR (Modern System)
CIDR replaced classful addressing with more flexible approach.

#### 🔧 CIDR Notation Examples:
- **/24** = 255.255.255.0
- **/25** = 255.255.255.128
- **/27** = 255.255.255.224
- **/28** = 255.255.255.240

#### ✅ CIDR Benefits:
- No wasted IPs
- Efficient routing
- Required for subnetting

### 2.4 Special IP Ranges

#### 🔁 Loopback Address
- **127.0.0.1** → Test your own system

#### 🏠 Private IP Ranges
Used inside networks (LAN)

| Range | CIDR |
|-------|------|
| 10.0.0.0 | /8 |
| 172.16.0.0 | /12 |
| 192.168.0.0 | /16 |

---

## 3. IPv4 Crisis & Solutions (NAT & IPv6)

### 3.1 NAT — The Band-Aid Solution

#### ❌ Problem:
Not enough IPv4 addresses

#### ✅ Solution:
Use private IPs + NAT

#### 🔄 NAT Translation:
```vbnet
Private IP → Public IP (outbound)
Public IP  → Private IP (inbound)
