# 🔥 WIRESHARK — Beginner to Ethical Hacker  
### 🧠 Detailed Notes in Easy Language (Perfect for Students & Cybersecurity Learners)

---

## 🚀 1. What Wireshark Actually Is (Simple Explanation)

**Wireshark = Packet Analyzer**

A tool that **captures** and **shows** every packet travelling through your network.

👉 Think of it like **CCTV for your network traffic**.

### 🎯 What Cybersecurity Uses Wireshark For
- Detecting attacks  
  *(port scans, MITM, ARP spoofing)*  
- Investigating malware communication  
- Finding suspicious or unknown connections  
- Analyzing **DNS, HTTP, TLS, ICMP** protocols  
- Reconstructing files/credentials (if unencrypted)  
- Understanding real-time network behaviour  

---

## 🧩 2. Basics of Packets (Very Important)

A **packet** = a small piece of data sent over the internet.

### 📚 Layers & Packet Units

| Layer | Unit | Meaning |
|-------|-------|---------|
| **L2 — Data Link** | Frame | Data between **MAC → MAC** |
| **L3 — Network** | Packet | Data between **IP → IP** |
| **L4 — Transport** | TCP Segment / UDP Datagram | Uses ports (80, 443, 53...) |

### 🔑 Important Terms  
- **MAC Address** → Unique ID of your network card  
- **IP Address** → Identifies your device in a network  
- **Port** → Logical channel (Ex: Port 80 = HTTP)  

---

## 🛰 3. Capture Modes (Super Important for Hacking)

### 🟦 **1) Promiscuous Mode**
- Captures **all packets your NIC can see**, not only yours  
- Works well on **wired networks**  

### 🟧 **2) Monitor Mode (Wi-Fi Hacking)**
Captures **raw wireless frames**, including:  
- Beacons  
- Probe requests  
- Deauthentication frames  

👉 Used heavily in Wi-Fi hacking tools.

---

## 🧪 4. Capture Filters vs Display Filters

### 🟩 **Capture Filters (Before Capture)**
Use when you want to **capture only specific traffic**.

✔ Faster  
✔ Saves storage  
✔ Skips unwanted packets  

**Examples:**
```c
tcp
udp port 53
host 192.168.1.10
port 80
🟦 Display Filters (After Capture)
Used for analysis.
Most important for hacking.

Examples:

c
Copy code
http
dns.qry.name == "google.com"
tcp.flags.syn == 1 && tcp.flags.ack == 0
ip.addr == 8.8.8.8
🔑 Important Terms
BPF Syntax → Capture filter language

Display Filter Language → Wireshark’s analysis filter language

📡 5. Most Important Display Filters
🌐 General Traffic
c
Copy code
ip
tcp
udp
icmp
What they reveal:

tcp → connections, scans, flags

udp → DNS/DHCP/malware traffic

icmp → ping sweeps & reconnaissance

🧭 DNS Analysis
c
Copy code
dns
dns.flags.response == 0
dns.qry.name contains "example"
dns.qry.type == 16      // TXT record
Why important?

Malware uses DNS tunneling

PCs leak domain info

TXT records used for hidden data

Terms:

DNS Query: "What is the IP of google.com?"

DNS Response: "Here is the IP."

🌍 HTTP & HTTPS
c
Copy code
http
http.request.method == "GET"
http.request.method == "POST"
GET → retrieving data

POST → uploading data (logins, forms)

🔐 TLS (Encrypted Traffic)
c
Copy code
tls
tls.handshake.type == 1   // ClientHello
tls.handshake.type == 2   // ServerHello
Why analyze TLS?

See domains using SNI

Detect malware using HTTPS

Term:
SNI (Server Name Indication): shows which domain the client wants even when encrypted.

🚨 6. Attack Indicators (Very Important)
🛑 A) Port Scanning
c
Copy code
tcp.flags.syn == 1 && tcp.flags.ack == 0
Signs:

Many SYN packets

Fast port sweeps

📝 SYN packet = 1st step of TCP handshake

🕵️‍♂️ B) ARP Spoofing / MITM
c
Copy code
arp.opcode == 2
Signs:

Same IP → different MAC

Many ARP replies

Terms:

MITM: attacker sits between victim & router

ARP: maps IP → MAC

👾 C) Malware Beaconing
c
Copy code
ip.addr == <suspicious-ip>
Signs:

Small repeated packets

Exact time intervals

Usually TLS/UDP

📤 D) Data Exfiltration
c
Copy code
frame.len > 1500
ip.dst != 192.168.0.0/16
Signs:

Large outbound data

To foreign countries

Over HTTPS (common)

🧰 7. Key Wireshark Tools (Explained Simply)
🔍 1) Follow Stream
Reconstructs:

HTTP sessions

DNS conversations

TLS handshake

Chat messages (if unencrypted)

📊 2) Protocol Hierarchy
Shows percentage of protocols.
Useful to detect:

Rare protocols

Malware traffic patterns

🔎 3) Conversations
Lists:

Source & Destination IPs

Packet count

Data transferred

Helps detect:

Scanning

Suspicious hosts

📈 4) IO Graphs
Useful for:

Attack spikes

Beaconing patterns

Upload/download bursts

📁 5) Export Objects
Extract files from:

HTTP

SMB

FTP

Helpful for:

Recovering malware samples

Downloaded images

Attachments

⚔️ 8. Signs of Common Attacks (Easy Explanation)
🔥 Port Scanning
Lots of SYN packets

No full handshake

Ports changing rapidly

🎭 ARP Spoofing / MITM
Router IP → different MAC

Burst of ARP replies

📡 Ping Sweep
Many ICMP Echo Requests

From 1 source → many IPs

🛰 DNS Tunneling
Large DNS traffic

Weird long subdomains

Abuse of TXT records

👾 Malware Beaconing
Same timestamp intervals

Small data packets

🏴 Data Exfiltration
Massive outbound data

To unknown servers

Often hidden in HTTPS

🧪 9. MUST KNOW Protocol Fields (Explained)
Protocol	Field	Meaning	Purpose
ARP	arp.src.ip / arp.dst.ip	Who is asking who	Detect spoofing
DNS	dns.qry.name	Domain requested	Malware tunneling
HTTP	http.request.method	GET/POST	Credentials
TCP	tcp.flags	SYN/ACK/RST/FIN	Scanning & attacks
TLS	tls.handshake.type	Hello types	Analyze encrypted traffic
ICMP	icmp.type	Ping request/reply	Recon activity

🖥 10. tshark CLI (Command-Line Wireshark)
tshark = Wireshark in terminal (useful for automation).

🔧 Useful Commands
bash
Copy code
tshark -i eth0                        # Live capture
tshark -r file.pcapng                 # Read capture file
tshark -r file.pcapng -Y "dns"        # Filter DNS packets
tshark -z conv,tcp -r file.pcapng     # Show TCP conversations
tshark -T fields -e dns.qry.name      # Extract DNS domains
