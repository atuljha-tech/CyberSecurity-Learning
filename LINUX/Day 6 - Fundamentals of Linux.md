# 🐧 Linux Basics for Cybersecurity — Complete Notes

A structured and beginner-friendly guide for hackers, pentesters & cybersecurity learners.

---

## Introduction

Linux is the foundation of cybersecurity. Every cybersecurity tool (Metasploit, Nmap, Wireshark CLI, Hydra, Nikto, etc.) works best on Linux-based systems.

### Why Linux matters for cybersecurity:

- Open-source (full transparency)
- Powerful command-line tools
- Used in servers, cloud, IoT, devops, hacking labs
- Faster automation & scripting
- Gives low-level control over the system

---

## FREE HACKING LAB (Linux)

To practice safely, you must use a virtual environment.

### ✔ Recommended Free Labs

| Platform | What You Get | Why Use It? |
|----------|--------------|-------------|
| Kali Linux VM (VirtualBox / VMware) | Full pentesting OS | Industry-standard hacking distro |
| Parrot OS Home/Security Edition | Lightweight security OS | Good for low-spec laptops |
| Ubuntu + Security Tools | Custom setup | Best for beginners |
| TryHackMe (Free Rooms) | Online virtual labs | No installation needed |
| HackTheBox Academy | Guided cybersecurity labs | Great for structured learning |

⚠ **Always practice inside labs — never on real systems.**

---

## What is Linux?

Linux = Open-source operating system like Windows/macOS but more powerful for developers & hackers.

### 🧩 Key Linux Concepts

- **Kernel** → Heart of Linux (manages hardware)
- **Shell** → Interface between user & OS
- **Terminal** → Where you type commands
- **File System** → Everything is a file (`/home`, `/etc`, `/bin`, `/root`)

### 🏗 Linux File-System Hierarchy (Important!)
```
/
├── home       (user files)
├── root       (root user home)
├── etc        (config files)
├── bin        (basic commands)
├── usr        (user programs)
├── var        (logs, cached data)
└── opt        (optional software)
```

---

## Introducing the Linux Terminal

The terminal is where real hacking starts. It's faster and more powerful than GUI.

### Why hackers prefer the terminal?

- Run powerful tools (Nmap, Hydra, Gobuster, Metasploit)
- Automate with scripts
- Access system internals
- Control permissions & processes

**Shortcut:** `Ctrl + Alt + T` → Open Terminal (Ubuntu/Kali)

---

## Linux Command: `pwd`

`pwd` = Print Working Directory

Shows the current directory you are in.

**Example:**
```bash
pwd
```

**Output:**
```
/home/atul
```

Useful when you're navigating deeply inside folders and forget where you are.

---

## Linux Command: `ls`

`ls` = List files & directories

### Common uses
```bash
ls           # list items
ls -l        # list with details (permissions, size)
ls -a        # show hidden files
ls -lh       # human readable sizes
```

**Example Output:**
```
drwxr-xr-x Documents
-rw-r--r-- notes.txt
```

**Why it's important in hacking:** You constantly inspect directories while locating configs, keys, scripts, logs, etc.

---

## Linux Command: `cd`

`cd` = Change Directory

### Basic navigation
```bash
cd foldername       # move inside folder
cd ..               # go back one directory
cd /etc             # absolute path
cd ~                # go to home directory
cd /                # go to root
```

**Example:**
```bash
cd /var/log
```

Used heavily in cybersecurity while exploring important directories like:

- `/etc/passwd`
- `/var/log/auth.log`
- `/home/user/`
- `/tmp/` (attacker-controlled files)

---

## Test Your Skills (Self-Practice Tasks)

Try these without looking at answers:

### ✔ Beginner Tasks

1. Use `pwd` to check your current path.
2. Use `ls -la` and identify hidden files.
3. Navigate:
   - `/home`
   - then `/etc`
   - then back to `/home`.

### ✔ Medium Tasks

1. Create a folder `cyberlab` and move inside it.
2. Create a file `notes.txt`.
3. Display all items in long format.

### ✔ Pro Tasks (For Hackers)

1. Locate the file `/etc/passwd` using only navigation.
2. Navigate to `/var/log` and find `auth.log`.
3. List all directories where logs are stored.

---

## ⭐ Final Summary

This module teaches:

- What Linux is
- How the terminal works
- Essential navigation commands (`pwd`, `ls`, `cd`)
- Hands-on Linux practice for cybersecurity
- How to build your own hacking lab

**These are core skills every hacker must master before learning Nmap, Wireshark, Metasploit, Burp Suite, etc.**

---

## 📚 Additional Resources

- [Linux Journey](https://linuxjourney.com/)
- [OverTheWire: Bandit](https://overthewire.org/wargames/bandit/)
- [Kali Linux Documentation](https://www.kali.org/docs/)
- [TryHackMe: Linux Fundamentals](https://tryhackme.com/)

---

## 🤝 Contributing

Feel free to contribute by submitting pull requests or opening issues for improvements.

---

## 📝 License

This guide is open-source and available for educational purposes.

---

**Happy Hacking! 🚀**
