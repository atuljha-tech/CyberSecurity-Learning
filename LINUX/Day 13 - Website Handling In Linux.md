# 🌐 One‑Command Website + cURL — Cybersecurity Pro Notes
Fast • Practical • Offensive‑Security Ready

---

## ⚡ 1. One‑Command Web Server
Quickest way to host files for testing exploits, payloads, and PoCs.

### Python (most used in hacking)
```bash
python3 -m http.server
```
Runs on **port 8000**.

### Node.js
```bash
npx http-server
```

### Why Hackers Use It
- Host payloads / malware PoCs
- Test XSS, CSRF, CORS bypasses
- Serve exploit HTML/JS files
- Create local CTF challenges
- Share files instantly over LAN

---

## 📁 2. Changing Directories (Your Web Root)
Move into the folder before starting the server.
```bash
cd <folder>
cd ..
cd ~/Desktop/project
pwd
ls
```
The directory you are in = **your web root**.

💡 **Cyber Tip:** Place rogue JS, HTML, payloads here when testing browser attacks.

---

## 🖥 3. Multiple Terminals = Better Workflow
Use **two terminals**:
- **Terminal A** → run your web server
- **Terminal B** → send cURL requests / attacks

This simulates **attacker ↔ victim**, **client ↔ server**, **request ↔ response**.

---

## 🔁 4. Changing Ports
Use custom ports:
```bash
python3 -m http.server 9001
```

Check if port is in use:
```bash
sudo lsof -i :9001
```

Kill that process:
```bash
sudo kill -9 <PID>
```

💡 **Cyber Tip:** Malware often hides on nonstandard ports: `8443`, `9002`, `1337`.

---

## 💬 5. Talking to Your Local Website
Every site visit = an HTTP request. You can simulate it using `curl`.

Basic request:
```bash
curl http://localhost:8000
```

Follow redirects:
```bash
curl -L http://example.com
```

Save output:
```bash
curl -o out.html http://localhost:8000
```

---

## 🌪 6. cURL — Ultimate Cybersecurity Toolkit
`curl` is essential for pentesting, bug bounties, and debugging.

### 1️⃣ View Response Headers
```bash
curl -I http://localhost:8000
```

### 2️⃣ Send Custom HTTP Methods
```bash
curl -X POST http://localhost:8000
curl -X PUT http://localhost:8000
curl -X DELETE http://localhost:8000
```

### 3️⃣ Send Form Data
```bash
curl -d "username=admin&password=admin" http://target/login
```

### 4️⃣ Send JSON
```bash
curl -H "Content-Type: application/json" \
     -d '{"name":"atul"}' \
     http://localhost:8000/api
```

### 5️⃣ Add Custom Headers (Spoofing)
```bash
curl -H "User-Agent: EvilBot" http://localhost:8000
```

### 6️⃣ Verbose Debugging
```bash
curl -v http://localhost:8000
```

### 7️⃣ Full SSL Handshake + Detail
```bash
curl -vvv https://site
```

### 8️⃣ Downloading Files
```bash
curl -O http://localhost:8000/file.zip
```

---

## 🎯 Why cURL Matters in Hacking
- Directory enumeration
- Host‑header attacks
- Misconfiguration testing
- Custom verb testing
- CSRF & CORS research
- Checking cookies & security flags
- SSRF exploitation payloads
- Debugging proxies, CDNs, firewalls

---

## 🔍 7. Inspecting Raw Request & Response Headers
Verbose output:
```bash
curl -v http://localhost:8000
```

### Request Headers (Client → Server)
Examples:
- `GET / HTTP/1.1`
- `Host: localhost`
- `User-Agent: curl/8.0`
- `Accept: */*`

### Response Headers (Server → Client)
Examples:
- `HTTP/1.0 200 OK`
- `Server: SimpleHTTP/0.6 Python`
- `Content-Type: text/html`
- `Date: <server time>`

---

## 🛡 Why Headers Matter in Cybersecurity
Headers reveal:
- underlying server tech
- vulnerable frameworks
- security misconfigs
- cookie protections (HttpOnly, Secure, SameSite)
- directory listing
- proxy/CDN leaks

Attackers manipulate headers to:
- bypass authentication
- fake identity (User‑Agent spoofing)
- exploit weak CORS rules
- poison caches
- break host‑based firewalls

---

## ⚡ Quick Summary
| Concept | Purpose |
|--------|---------|
| **http.server** | instant local web server |
| **http-server** | Node.js alternative |
| **cd** | choose web root |
| **curl** | test requests, headers, payloads |
| **curl -v** | debug request/response |
| **lsof** | check port usage |
| **kill -9** | free up a port |

---

Made for ⚡ **pentesters**, **CTF players**, **bug hunters**, and **cybersecurity learners**.
# 🌐 One‑Command Website + cURL — Cybersecurity Notes

A clean, minimal, professional reference for **offensive security**, **bug bounty**, and **CTF work**.

---

## ⚡ 1. One‑Command Web Server
Quickest way to host files, payloads, HTML PoCs, or malicious JS.

### **Python (Most used in hacking)**
```
python3 -m http.server
```
Default → **port 8000**.

### **Node.js**
```
npx http-server
```

### Why Hackers Use These
- Host payloads
- Serve exploit pages (XSS, CSRF, Clickjacking)
- Deliver malicious JS
- Run PoC servers for CTF challenges
- Quick local testing of vulnerabilities

---

## 📁 2. Changing Directories (Web Root)
Whatever folder you're inside becomes the **web root**.

```
cd <folder>
cd ..
cd ~/Desktop/project
pwd
ls
```

**Cyber Tip:** Put malicious/PoC HTML+JS here while testing attacks.

---

## 🖥 3. Using Two Terminals (Attack vs Server)
**Terminal A** → Runs your server  
**Terminal B** → Runs attacks (`curl`, payloads, scripts)

Emulates:
- attacker vs victim  
- client vs server  
- request vs response

---

## 🔁 4. Changing Ports
Use alternate ports for stealth, PoCs, or privilege issues.

### Python
```
python3 -m http.server 9001
```

### Check if port is busy
```
sudo lsof -i :9001
```

### Kill the conflicting process
```
sudo kill -9 <PID>
```

**Cyber Tip:**  
Malware often runs servers on ports like **8443, 9002, 1337, 6969**.

---

## 💬 5. Talking to Your Website (Command Line HTTP)
Every website visit = HTTP request.  
You can simulate it manually with `curl`.

### Basic request
```
curl http://localhost:8000
```

### Follow redirects
```
curl -L http://example.com
```

### Save response to a file
```
curl -o out.html http://localhost:8000
```

---

## 🌪 6. cURL — Cybersecurity Toolkit
Your most powerful web‑attack tool.

### 1️⃣ View response headers
```
curl -I http://localhost:8000
```

### 2️⃣ Send custom verbs
```
curl -X POST http://localhost
curl -X PUT http://localhost
curl -X DELETE http://localhost
```

### 3️⃣ Send form data
```
curl -d "username=admin&password=admin" http://target/login
```

### 4️⃣ Send JSON
```
curl -H "Content-Type: application/json" \
     -d '{"name":"atul"}' \
     http://localhost:8000/api
```

### 5️⃣ Custom headers (spoofing)
```
curl -H "User-Agent: EvilBot" http://localhost
```

### 6️⃣ Verbose
```
curl -v http://localhost
```

### 7️⃣ Ultra verbose (SSL handshake too)
```
curl -vvv https://site
```

### 8️⃣ Download files
```
curl -O http://localhost/file.zip
```

### Why cURL Is Critical
- Directory brute forcing
- Testing CORS/CSRF
- Host header attacks
- Injecting custom headers
- Checking misconfiguration
- SSRF payload tests
- Debugging authentication flows

---

## 🔍 7. Inspecting HTTP Headers
Get full request + response details:
```
curl -v http://localhost:8000
```

### **Request Headers (Client → Server)**
Shows:
- method (GET/POST/etc.)
- URL
- `Host`
- `User-Agent`
- `Accept`

### **Response Headers (Server → Client)**
Shows:
- HTTP status
- server type
- content-type
- cookies
- CORS policy

### Why Headers Matter in Cybersecurity
- Identify backend technology
- Detect vulnerable frameworks
- Check CORS misconfig
- Analyse cookies (`HttpOnly`, `Secure`, `SameSite`)
- Spot directory listing leaks
- Fingerprint servers (Python, Node, Apache, Nginx)
- Attackers use header spoofing to:  
  - bypass auth  
  - fake browsers  
  - exploit misconfigured proxies

---

## 📌 End of Notes
Clean, minimal, high‑value for cyber learning.


