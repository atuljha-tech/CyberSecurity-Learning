# 🌐 Ultimate Networking & Cybersecurity Fundamentals Notes  
### *(Complete Guide — Ports, IP Addressing, NAT, IPv6, Binary & Subnetting)*

---

# 📑 Table of Contents
1. [Ports & Protocols: The Digital Doors](#1-ports--protocols-the-digital-doors)  
2. [IPv4 Addressing: The Foundation](#2-ipv4-addressing-the-foundation)  
3. [IPv4 Crisis & Solutions (NAT & IPv6)](#3-the-ipv4-crisis--solutions-nat--ipv6)  
4. [Binary & Decimal Conversion](#4-binary--decimal-conversion-the-language-of-machines)  
5. [Subnetting: Designing Secure Networks](#5-subnetting-designing-secure-networks)

---

# 1. Ports & Protocols: The Digital Doors

## 1.1 What Are Ports?
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

---

## 1.2 Why Ports Matter in Cybersecurity
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

---

## 1.3 TCP vs UDP (Cybersecurity View)

| Feature | TCP | UDP |
|--------|-----|-----|
| Connection | ✔ Connection-oriented | ❌ No connection |
| Reliability | ✔ Guaranteed delivery | ❌ Not guaranteed |
| Speed | Slow (overhead) | Fast (minimal overhead) |
| Examples | HTTP/S, SSH, FTP | DNS, VoIP, gaming, streaming |
| When to Use | Accuracy | Speed |

---

## 1.4 ⚠ Cybersecurity Essential Ports List (MEMORIZE THESE)

| Port | Proto | Service | Why Important |
|------|--------|---------|----------------|
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

---

## 1.5 What is a Protocol?
A **protocol** is a set of communication rules.

Examples:
- HTTP (web)
- DNS (names → IP)
- SSH (secure login)
- TCP/UDP (transport layer)

---

## 1.6 Port Scanning (Core Cyber Skill)

Tools: **Nmap, Masscan, RustScan**

Example:
```bash
nmap -sV -O <target>
# -sV = Service version detection
# -O  = OS detection
2. IPv4 Addressing: The Foundation
2.1 Why IPv4 Is Limited
IPv4 = 32-bit addressing
Total = 4.3 billion addresses (not enough today)

2.2 Classful Addressing (Old System)
Class	Range	Default Mask	Use
A	1.0.0.0 – 126.255.255.255	/8	Big networks
B	128.0.0.0 – 191.255.255.255	/16	Medium
C	192.0.0.0 – 223.255.255.255	/24	Small
D	224.0.0.0 – 239.255.255.255	N/A	Multicast
E	240.0.0.0 – 255.255.255.255	N/A	Experimental

2.3 CIDR (Modern System)
CIDR replaced classes.

Examples:

/24

/25

/27

/28

Benefits:

No wasted IPs

Efficient routing

Required for subnetting

2.4 Special IP Ranges
✔ Loopback
127.0.0.1 → test your own system

✔ Private IP Ranges
Used inside networks (LAN)

Range	CIDR
10.0.0.0	/8
172.16.0.0	/12
192.168.0.0	/16

3. The IPv4 Crisis & Solutions (NAT & IPv6)
3.1 NAT — The Band-Aid Solution
Problem: Not enough IPv4 addresses
Solution: Use private IPs + NAT

NAT translates:

vbnet
Copy code
Private IP → Public IP (outbound)
Public IP  → Private IP (inbound)
Benefits (Cybersecurity)
Hides internal network

Reduces attack exposure

Conserves IPv4 address usage

3.2 IPv6 — The Permanent Solution
128-bit addressing

2^128 possible addresses (practically unlimited)

No need for NAT

Built-in security features

Cybersecurity must understand both IPv4 and IPv6.

4. Binary & Decimal Conversion: The Language of Machines
4.1 IPv4 = 4 Octets (8 bits each)
Example:
192.168.1.10

4.2 Bit Place Values
Copy code
128 64 32 16 8 4 2 1
4.3 Decimal ➝ Binary
Example: 155 → Binary

makefile
Copy code
155 - 128 = 27  (1)
27 - 16 = 11    (1)
11 - 8 = 3      (1)
3 - 2 = 1       (1)
1 - 1 = 0       (1)

Result: 10011011
4.4 Binary ➝ Decimal
Example: 11000000

Copy code
128 + 64 = 192
5. Subnetting: Designing Secure Networks
Subnetting divides a big network into smaller secure segments:

Controls traffic

Enhances security

Reduces broadcast noise

Efficient IP allocation

🔥 Example Scenario
Network: 192.168.1.0/24
Need: 5 subnets

Step 1 — Convert Mask to Binary
255.255.255.0
Binary:
11111111.11111111.11111111.00000000

Network bits: 24
Host bits: 8

Step 2 — Borrow Host Bits
Need 5 subnets

Copy code
2^3 = 8  (>= 5)
Borrow 3 bits.

Step 3 — New Subnet Mask
Borrowed bits → 11100000

128 + 64 + 32 = 224

New mask:

makefile
Copy code
255.255.255.224
CIDR: /27
Hosts per subnet:

Copy code
2^5 - 2 = 30
Step 4 — Find Increment
Copy code
256 - 224 = 32
Step 5 — All Possible Subnets (8 Total)
Network	Host Range	Broadcast
192.168.1.0	1–30	31
192.168.1.32	33–62	63
192.168.1.64	65–94	95
192.168.1.96	97–126	127
192.168.1.128	129–158	159
192.168.1.160	161–190	191
192.168.1.192	193–222	223
192.168.1.224	225–254	255
