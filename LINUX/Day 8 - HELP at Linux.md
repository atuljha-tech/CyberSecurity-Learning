# 🐧 Linux Terminal — Cybersecurity Notes (README.md)

A clean, polished, professional Linux terminal guide — ready to copy‑paste into **README.md**.
Perfect for **Pentesting, CTFs, Forensics, Privilege Escalation, and System Auditing**.

---

# 📌 Overview

This document helps you master essential Linux terminal concepts and commands required in:

* **Cybersecurity**
* **Digital Forensics**
* **Incident Response**
* **System Administration**
* **Privilege Escalation**

You will learn how to analyze processes, inspect system info, check network activity, detect malicious behavior, and use help/manual systems.

---

# 🧭 1. Getting to Know the Linux Terminal

## ✔ What is the Terminal?

A text‑based interface used for:

* Running commands
* Managing files, users, processes and networks
* Performing forensics and security investigations
* Automating tasks with scripts

## ✔ Why Cybersecurity Requires Terminal Skills

Cyber experts depend on the terminal for:

* Checking logs & system activity
* Detecting intrusions
* Performing privilege escalation
* Navigating servers without GUI
* Investigating malware or backdoors

## ✔ Shells You Should Know

* **bash** — Default shell on most Linux distros
* **zsh** — Modern, customizable
* **sh** — Minimal POSIX shell
* **fish** — User-friendly shell

Check your current shell:

```bash
echo $SHELL
```

---

# 🧪 2. `ps` — Process Status (Extremely Important)

`ps` shows running processes. Critical for:

* Malware detection
* Reverse engineering
* Incident response

## 🔹 Basic Usage

```bash
ps
```

## 🔹 View all processes

```bash
ps aux
```

Flags:

* `a` — all users
* `u` — user-friendly format
* `x` — show background/daemon processes

## 🔹 Detect malicious activity

```bash
ps aux | grep python
ps aux | grep crypto
```

## 🔹 Process tree (spot hidden parents)

```bash
ps axjf
```

---

# ⚡ 3. Essential Reconnaissance Commands

These must be memorized — used in all cybersecurity tasks:

* `id`
* `hostname`
* `uname`
* `who`
* `env`
* `ip`
* `ss`

Each is explained below.

---

# 🆘 4. Getting Help in Linux (MAN, HELP Flags)

Mastering documentation = mastering Linux.

## ✔ `man` — Manual Pages

```bash
man ls
man ps
man ip
```

Exit → press **q**

## ✔ Quick help flags

```bash
ls --help
ip -h
```

## ✔ `whatis` — One-line command summary

```bash
whatis ssh
```

## ✔ `apropos` — Search commands by keyword

```bash
apropos user
apropos network
```

Useful when you don’t know the exact command.

---

# 🛠 5. Essential Cybersecurity Commands (Detailed)

These commands are the core of system enumeration and forensics.

---

## 🔍 5.1 User & System Info

### 🔹 `id` — User identity

```bash
id
```

Shows:

* UID, GID
* Groups
  Used heavily in **privilege escalation**.

### 🔹 `hostname` — Machine name

```bash
hostname
```

Useful during system mapping.

### 🔹 `uname` — Kernel / OS details

```bash
uname -r   # kernel version
uname -a   # all details
```

Used for kernel exploit research.

---

## 🌐 5.2 Network Commands (Critical for Recon)

### 🔹 `ifconfig` — Legacy network tool

```bash
ifconfig
```

Shows IP, MAC, interface status.

### 🔹 `ip` — Modern replacement

```bash
ip a      # interface info
ip r      # routing table
ip link   # hardware link
```

### 🔹 `netstat` — Deprecated but used in CTFs

```bash
netstat -tulnp
```

Shows:

* Open ports
* Active connections

### 🔹 `ss` — Faster netstat

```bash
ss -tulnp
```

Recommended for modern systems.

---

## ⚙ 5.3 Process & System Inspection

### 🔹 `who` — Logged-in sessions

```bash
who
```

Detect unauthorized logins.

### 🔹 `env` — Environment variables

```bash
env
```

Used for detecting:

* PATH manipulation
* Persistence
* Misconfigurations

---

## 💾 5.4 Hardware & Storage Commands

### 🔹 `lsblk` — Block devices

```bash
lsblk
```

Shows disks, partitions, mount points.

### 🔹 `lsusb` — USB devices

```bash
lsusb
```

Helpful in USB malware investigations.

### 🔹 `lsof` — Open files / ports

```bash
lsof
lsof -i
```

Used to trace:

* Backdoors
* Suspicious processes
* Files used by malware

---

# 🏁 Summary Table (Quick Revision)

| Command           | Purpose               | Cybersecurity Use          |
| ----------------- | --------------------- | -------------------------- |
| `ps`              | Process list          | Malware/backdoor detection |
| `man`             | Manuals               | Learn command usage        |
| `apropos`         | Search by keyword     | Find unknown commands      |
| `id`              | User identity         | Privilege escalation       |
| `hostname`        | System name           | Recon & enumeration        |
| `uname`           | Kernel info           | Kernel exploit research    |
| `ifconfig` / `ip` | Network info          | IP/MAC/interface discovery |
| `netstat` / `ss`  | Ports & connections   | Detect backdoors           |
| `who`             | Logged-in users       | Detect intruders           |
| `env`             | Environment variables | Persistence detection      |
| `lsblk`           | Storage devices       | Disk forensics             |
| `lsusb`           | USB devices           | Hardware investigation     |
| `lsof`            | Open files/ports      | Trace suspicious processes |

---

# 📚 Resources

### ✔ Practice

Use commands inside:

* VirtualBox/VMware Linux VM
* WSL (Windows Subsystem for Linux)
* Docker containers

### ✔ CTF Practice

* TryHackMe
* HackTheBox
* VulnHub

### ✔ Documentation

Always read manual pages:

```bash
man <command>
```

---

If you want:

* A **PDF version**
* A **colored cheat sheet**
* A **command-by-command flashcard set**
* Or an **advanced version (Privilege Escalation Edition)**

Just tell me — I'll generate it instantly. 🚀
