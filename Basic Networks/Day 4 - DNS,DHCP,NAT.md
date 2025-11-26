# 🔥 DNS, DHCP & NAT — Expert-Level Cybersecurity Notes

*Ultimate Revision Document for Professional Cybersecurity Learning*

---

## 🧩 1. DNS — Domain Name System (Networking + Security)

### ✅ What is DNS? (Core Concept)

**DNS = The Internet's Phonebook**  
It converts domain names → IP addresses so humans don't need to memorize numbers.

#### Why DNS Exists
- Websites use IP addresses; humans use names
- DNS translates names like `google.com` to an IP like `142.250.190.14`
- Without DNS → Internet becomes unusable

#### DNS Architecture (Hierarchy)
- **Root DNS Servers** (.)
- **TLD Servers** (.com, .net, .org, .in, .edu …)
- **Authoritative DNS Servers** (hold real records of domain)
- Distributed globally → fast, fault-tolerant, scalable

### 🔎 DNS Records — What DNS Stores

| Record | Purpose |
|--------|---------|
| A | Domain → IPv4 address |
| AAAA | Domain → IPv6 address |
| CNAME | Canonical alias name |
| NS | Shows which servers store DNS records for domain |
| MX | Mail servers for email |
| TXT | Arbitrary text (SPF, DKIM, DMARC etc.) |

### 🔐 DNS — Security Risks & Attack Vectors

1. **DNS Spoofing / Cache Poisoning**  
   Attacker injects fake DNS responses → redirects you to malicious IP

2. **DNS Hijacking / Rogue DNS**  
   Attacker forces client to use their DNS server → controls all lookups

3. **Phishing / Malware Distribution**  
   Fake DNS → fake website → credential theft / malware

4. **Blocking Updates / Censorship**  
   Malicious DNS may block OS updates or security tools

5. **DNS Rebinding Attack**  
   Domains resolve to internal IPs → attacker hacks local devices

### 🛡️ DNS Security Best Practices

- Use **DNS-over-HTTPS (DoH)** or **DNS-over-TLS (DoT)** → encrypted queries
- Use trusted DNS (Cloudflare, Google, Quad9, internal resolver)
- Patch + monitor DNS server activity
- Enable **DNSSEC** where possible (validates authenticity)
- Avoid public Wi-Fi (risk of DNS manipulation)
- Always check HTTPS certificate — mismatch = DNS attack alert

### 🎯 DNS — Cybersecurity Takeaways

- DNS is core internet infrastructure
- If DNS gets hacked → entire browsing gets hijacked
- DNS insecurity is a major vector for phishing & man-in-the-middle attacks
- Always combine DNS with SSL/TLS, DNSSEC & logging

---

## 🧩 2. DHCP — Dynamic Host Configuration Protocol

### ✅ What is DHCP? (Simple Explanation)

DHCP automatically assigns:
- IP address
- Subnet mask
- Gateway
- DNS server
- Lease time
- Optional configs (NTP, domain name, etc.)

No manual IP setup needed → scalable & flexible

### 🔄 How DHCP Works (DORA Process)

| Step | Meaning |
|------|---------|
| Discover | Client searches for DHCP server |
| Offer | Server offers IP lease |
| Request | Client accepts offered IP |
| Acknowledge | Server finalizes lease |

### 🛠️ DHCP Key Features

- Dynamic IP allocation
- Reservations (Static DHCP → same IP for specific MAC)
- Scopes / Pools for networks
- Lease renewal without manual config

### ⚠️ DHCP — Security Risks

1. **Rogue DHCP Server**  
   Attacker plugs into network → offers malicious IP, DNS, gateway → MITM attacks

2. **DHCP Spoofing**  
   Manipulates DHCP responses → redirects traffic

3. **DHCP Starvation (Pool Exhaustion)**  
   Attacker sends thousands of fake requests → IP pool exhausted → DoS attack

4. **Unauthorized Devices**  
   Open LAN/Wi-Fi + DHCP → attacker can join network easily

### 🛡️ DHCP Security Hardening

- Enable **DHCP Snooping** on switches
- Enable **Port Security** (sticky MAC)
- Use **VLAN segmentation**
- Use static IPs for servers / critical devices
- Monitor DHCP logs for abnormal requests
- Use **802.1X (Network Access Control)** authentication

### 🎯 DHCP — Cybersecurity Takeaways

- Easy but dangerous if not secured
- Rogue DHCP = biggest threat → MITM + DNS hijacking
- Use DHCP Snooping + VLANs to secure enterprise networks
- Dynamic IP = flexibility, but static IPs recommended for critical infrastructure

---

## 🧩 3. NAT — Network Address Translation

### ✅ What is NAT?

NAT translates private IP addresses ↔ public IP on a router

**Reason:** IPv4 shortage + security needs

**Example:**  
Your device: `192.168.1.20`  
Router replaces with public: `103.25.40.15`

### 🔄 How NAT Works (Simplified)

1. Internal device → sends traffic to internet
2. Router removes private IP → replaces with public IP
3. Router tracks mapping in NAT table
4. Response returns → router restores private IP → device receives data

This hides internal network structure

### 🔥 Types of NAT

1. **Static NAT**  
   Private ↔ Public (1:1 fixed mapping)

2. **Dynamic NAT**  
   Private ↔ any free public IP from pool

3. **PAT (Port Address Translation)**  
   Many private IPs → one public IP  
   Differentiated by ports  
   Most common (home routers)

### 🌐 Public vs Private IP

| Feature | Private IP | Public IP |
|---------|------------|-----------|
| Use | LAN only | Internet |
| Assigned by | Router | ISP |
| Security | Hidden | Exposed |
| Ranges | 10.x.x.x, 192.168.x.x, 172.16.x.x–31.x | All non-private IPs |

NAT converts private → public

### 🔄 IPv4 vs IPv6 (NAT Perspective)

| IPv4 | IPv6 |
|------|------|
| 32-bit (4.3B addresses) | 128-bit (enormous) |
| Needs NAT | No NAT needed |
| Limited | Future-proof |
| NAT hides devices | IPv6 exposes unless firewalled |

In IPv6, firewall is mandatory, NAT is not used

### 🛡️ NAT — Security Benefits

- ✔️ **Hides internal devices**  
  Attackers cannot see internal IPs

- ✔️ **Blocks unsolicited incoming traffic**  
  Unless port forwarding exists

- ✔️ **Reduces vulnerability exposure**  
  Only router is visible to internet

### ⚠️ NAT — Security Limitations

- NAT is **NOT a firewall**
- If device initiates connection → NAT allows return traffic
- Protocols embedding IP in payload break (FTP active, SIP, VoIP)
- Can create false sense of security
- With IPv6, NAT is removed → exposure increases

### 🎯 NAT — Cybersecurity Takeaways

- NAT = basic protection, **NOT real security**
- Always combine NAT with firewalls + IDS/IPS + segmentation
- Understand NAT behaviour for penetration testing & incident response
- With IPv6, rely entirely on firewalls

---

## ⭐ FINAL SUMMARY (Ultra-Quick Revision)

### **DNS**
- ✔ Translates domain → IP
- ✔ Attacks: Spoofing, Hijacking, Rebinding
- ✔ Defend using: DNSSEC, DoH/DoT, trusted resolvers

### **DHCP**
- ✔ Auto IP assignment via DORA
- ✔ Attacks: Rogue DHCP, Spoofing, Starvation
- ✔ Defend using: DHCP Snooping, VLANs, 802.1X

### **NAT**
- ✔ Private → Public IP translation
- ✔ Security by obscurity, not real defense
- ✔ Still essential in IPv4 networks

---

*Cybersecurity Professional Revision Document | DNS • DHCP • NAT*
