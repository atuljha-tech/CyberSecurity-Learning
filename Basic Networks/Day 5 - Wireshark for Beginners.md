# 🦈 Wireshark Analysis Guide

A comprehensive reference for network traffic analysis, attack detection, and security investigation using Wireshark.

---

## 📋 Table of Contents

- [Display Filters](#display-filters)
- [Most Important Display Filters](#most-important-display-filters)
- [Attack Indicators](#attack-indicators)
- [Key Wireshark Tools](#key-wireshark-tools)
- [Signs of Common Attacks](#signs-of-common-attacks)
- [Must-Know Protocol Fields](#must-know-protocol-fields)
- [tshark CLI Commands](#tshark-cli-commands)

---

## 🔍 Display Filters

Display filters are used for analysis — **95% of your work happens here**.

### Examples:

```
http
dns.qry.name == "google.com"
tcp.flags.syn == 1 && tcp.flags.ack == 0
ip.addr == 8.8.8.8
```

---

## 🌐 Most Important Display Filters

### General Traffic

```
ip
tcp
udp
icmp
```

**Why these matter:**
- `tcp` → scans & flags
- `udp` → DNS, DHCP, malware
- `icmp` → ping sweeps

### 🧭 DNS Analysis

```
dns
dns.flags.response == 0
dns.qry.name contains "example"
dns.qry.type == 16
```

**Why DNS matters:**
- Malware uses DNS tunneling
- Systems leak domain info
- TXT records used for data hiding

### 🌍 HTTP & HTTPS

```
http
http.request.method == "GET"
http.request.method == "POST"
```

**Use cases:**
- `GET` → retrieving pages
- `POST` → logins, forms, uploads

### 🔐 TLS (Encrypted Traffic)

```
tls
tls.handshake.type == 1   // ClientHello
tls.handshake.type == 2   // ServerHello
```

**Why analyze TLS:**
- See domains using SNI
- Detect malware using HTTPS

---

## 🚨 Attack Indicators

### 🛑 Port Scanning

```
tcp.flags.syn == 1 && tcp.flags.ack == 0
```

**Signs:**
- Many SYN packets
- No complete handshake

### 🎭 ARP Spoofing / MITM

```
arp.opcode == 2
```

**Signs:**
- Same IP → different MAC
- Many ARP replies

### 🛰 Malware Beaconing

```
ip.addr == <suspicious-ip>
```

**Signs:**
- Repeated small packets
- Fixed time intervals

### 📤 Data Exfiltration

```
frame.len > 1500
ip.dst != 192.168.0.0/16
```

**Signs:**
- Large outbound data
- To foreign/unusual servers

---

## 🧰 Key Wireshark Tools

### 🔍 1) Follow Stream

**Reconstructs:**
- HTTP sessions
- DNS conversations
- TLS handshake
- Chat messages (if unencrypted)

### 📊 2) Protocol Hierarchy

**Shows percentage of protocols.**

**Useful to detect:**
- Rare protocols
- Malware traffic patterns

### 🔎 3) Conversations

**Lists:**
- Source & Destination IPs
- Packet count
- Data transferred

**Helps detect:**
- Scanning
- Suspicious hosts

### 📈 4) IO Graphs

**Useful for:**
- Attack spikes
- Beaconing patterns
- Upload/download bursts

### 📁 5) Export Objects

**Extract files from:**
- HTTP
- SMB
- FTP

**Helpful for:**
- Recovering malware samples
- Downloaded images
- Attachments

---

## ⚔️ Signs of Common Attacks

### 🔥 Port Scanning

- Lots of SYN packets
- No full handshake
- Ports changing rapidly

### 🎭 ARP Spoofing / MITM

- Router IP → different MAC
- Burst of ARP replies

### 📡 Ping Sweep

- Many ICMP Echo Requests
- From 1 source → many IPs

### 🛰 DNS Tunneling

- Large DNS traffic
- Weird long subdomains
- Abuse of TXT records

### 👾 Malware Beaconing

- Same timestamp intervals
- Small data packets

### 🏴 Data Exfiltration

- Massive outbound data
- To unknown servers
- Often hidden in HTTPS

---

## 📊 Must-Know Protocol Fields

| Protocol | Field | Meaning | Purpose |
|----------|-------|---------|---------|
| **ARP** | `arp.src.ip` / `arp.dst.ip` | Who is asking who | Detect spoofing |
| **DNS** | `dns.qry.name` | Domain requested | Malware tunneling |
| **HTTP** | `http.request.method` | GET/POST | Credentials |
| **TCP** | `tcp.flags` | SYN/ACK/RST/FIN | Scanning & attacks |
| **TLS** | `tls.handshake.type` | Hello types | Analyze encrypted traffic |
| **ICMP** | `icmp.type` | Ping request/reply | Recon activity |

---

## 🖥 tshark (CLI Wireshark)

**tshark = Wireshark in terminal (useful for automation).**

### 🔧 Useful Commands

```bash
# Live capture
tshark -i eth0

# Read capture file
tshark -r file.pcapng

# Filter DNS packets
tshark -r file.pcapng -Y "dns"

# Show TCP conversations
tshark -z conv,tcp -r file.pcapng

# Extract DNS domains
tshark -T fields -e dns.qry.name -r file.pcapng
```

---

## 📝 Quick Tips

- **Start broad, filter down** — Begin with protocol-level filters, then narrow to specific fields
- **Use Follow Stream** — Essential for understanding context in conversations
- **Check time deltas** — Look for patterns in timing (beaconing, periodic connections)
- **Export objects** — Always check for downloadable files in HTTP traffic
- **Compare baselines** — Know what normal traffic looks like in your environment

---

## 🔗 Additional Resources

- [Wireshark Official Documentation](https://www.wireshark.org/docs/)
- [Wireshark Display Filter Reference](https://www.wireshark.org/docs/dfref/)
- [Sample Capture Files](https://wiki.wireshark.org/SampleCaptures)

---

**Happy Hunting! 🦈**
