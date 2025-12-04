# 🐧 Linux Terminal — Cybersecurity Notes

## 📌 Overview
This document teaches you how to understand the Linux terminal deeply, use fundamental system-inspection commands, and retrieve help/documentation — all of which are crucial for:

- **Cybersecurity**
- **Forensics**
- **Privilege Escalation**
- **System Auditing**
- **Incident Response**

---

## 🧭 1. Getting to Know the Linux Terminal

### ✔ What is the Terminal?
The terminal is a text-based interface used for:

- Issuing commands
- Managing files, processes, networks, and users
- Performing automation, forensics, and security operations

### ✔ Why Cybersecurity Needs the Terminal
Cyber experts rely heavily on the terminal to:

- Inspect system activity
- Detect intrusions (logs, processes, open ports)
- Perform privilege escalation
- Navigate servers without GUI
- Automate security scripts

### ✔ Shells You Should Know
- **bash** – Default shell in most Linux distros
- **zsh** – Enhanced shell with better completion
- **sh** – Lightweight POSIX shell
- **fish** – Modern, user-friendly shell

Check your current shell:
```bash
echo $SHELL
🧪 2. ps Command (Process Status)
ps displays running processes. Extremely important for:

Malware detection

Reverse engineering

Incident response

🔹 Basic Usage
bash
ps
🔹 View all running processes
bash
ps aux
a → all users

u → user-friendly format

x → include background/daemon processes

🔹 Check for malicious activity
bash
ps aux | grep python
ps aux | grep crypto
🔹 Process tree (detects abnormal parent–child processes)
bash
ps axjf
⚡ 3. Essential Reconnaissance Commands
These are the core Linux reconnaissance commands every cybersecurity learner MUST know.

🆘 4. Getting Help in Linux (MAN & -h)
✔ man — Manual Pages
Read detailed command documentation:

bash
man ls
man ps
man ip
Exit → Press q.

✔ Quick Help (-h, --help)
bash
ls --help
ip -h
✔ whatis — One-line description
bash
whatis ssh
✔ apropos — Search by keyword
bash
apropos network
apropos user
Very useful in hacking labs when you don’t know the exact command!

🛠 5. Essential Cybersecurity Commands (Detailed)
These commands help with system recon, privilege escalation, defense, and forensics.

🔍 5.1 User & System Info Commands
🔹 id — Show user identity info
bash
id
Shows:

UID

GID

Groups

Used in privilege escalation.

🔹 hostname — System hostname
bash
hostname
Used in system enumeration during breaches.

🔹 uname — Kernel and OS info
bash
uname
Common flags:

bash
uname -r   # kernel version
uname -a   # full system info
Extremely important for kernel exploit research.

🌐 5.2 Network Commands
🔹 ifconfig (old tool)
bash
ifconfig
Shows:

IP address

MAC address

Interface status

🔹 ip (modern replacement for ifconfig)
bash
ip a      # show interfaces
ip r      # routing table
ip link   # hardware link info
🔹 netstat (deprecated, but common in CTFs)
bash
netstat -tulnp
Shows:

Open ports

Listening services

Current connections

🔹 ss — Modern netstat
bash
ss -tulnp
Faster and more accurate.

⚙ 5.3 Process & System Inspection
🔹 ps — Process status
(Covered above)

🔹 who — Logged-in users
bash
who
Shows:

Local sessions

Remote SSH logins

Used to detect unauthorized access.

🔹 env — Environment variables
bash
env
Used to detect:

PATH manipulation

Malware persistence

Misconfigurations

💾 5.4 Hardware & Storage Commands
🔹 lsblk — Block devices
bash
lsblk
Shows:

Disks

Partitions

Mount points

Used in forensic analysis.

🔹 lsusb — USB devices
bash
lsusb
Useful for:

USB malware investigation

Hardware enumeration

🔹 lsof — Open files & ports
bash
lsof
lsof -i   # list network connections
Great for:

Detecting backdoors

Tracing suspicious processes

🏁 Summary Table (Quick Revision)
Command	Purpose	Cybersecurity Use
ps	Show processes	Detect malware/backdoors
man	Manual pages	Learn commands/features
apropos	Find commands	Recon during tasks
id	User identity	Privilege escalation
hostname	System name	System enumeration
uname	Kernel info	Kernel exploit research
ifconfig / ip	Network info	IP/MAC/interface discovery
netstat / ss	Ports & connections	Detect open ports/backdoors
who	Logged-in users	Unauthorized access detection
env	Environment variables	Persistence detection
lsblk	Storage devices	Disk forensics
lsusb	USB devices	Hardware investigation
lsof	Open files	Trace suspicious processes
📚 Resources
Practice: Try these commands in a Linux VM or Docker container

CTFs: Use these for enumeration in platforms like TryHackMe, HackTheBox

Documentation: Always check man pages for deeper understanding

