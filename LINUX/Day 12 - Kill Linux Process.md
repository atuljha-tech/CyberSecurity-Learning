# 🐧 Linux Process Management — Pro Cybersecurity Notes
Clean • Sharp • Incident-Response Ready

---

## 🔍 1. The **ps** Command (Deep Recon)
`ps` = **Process Status**. Your first tool for investigating a Linux system.

### 🔥 Core Usage
```bash
ps aux          # ALL processes (most used)
```
**a** = all users  
**u** = owner + resource usage  
**x** = include processes without a terminal

### 🌲 Hierarchical / Tree View
```bash
ps axjf
```
Shows parent → child mappings. **Great for spotting fork bombs, reverse shells, or injected processes.**

### 📊 Sort by Resource Usage
```bash
ps aux --sort=-%mem
ps aux --sort=-%cpu
```

### 👤 View by User
```bash
ps -u username
```

### 🎯 Custom Columns
```bash
ps -eo pid,ppid,user,cmd,%cpu,%mem --sort=-%cpu
```

### ⚠ Cyber Tip
Attackers often hide malicious processes under **root-owned parents** → check tree views.

---

## 🗡 2. Killing Linux Processes (Basics)
### Normal kill
```bash
kill <PID>
```
Sends **SIGTERM (15)** → graceful shutdown.

### Forced kill
```bash
kill -9 <PID>
```
Sends **SIGKILL (9)** → cannot be ignored.

⚠ Use only when needed — malware sometimes traps SIGTERM.

---

## 🎯 3. Finding Processes with `pgrep`
### Find PID by name
```bash
pgrep firefox
```

### Show details
```bash
pgrep -a ssh
```

### Filter by user
```bash
pgrep -u root
```

### Cyber Use Case
```bash
pgrep -a python   # spot Python-based backdoors
```

---

## 📌 4. More Power with `ps`
### Process environment variables
```bash
ps e -p <PID>
```
Useful for detecting **malicious LD_PRELOAD** or injected vars.

### Show threads
```bash
ps -T -p <PID>
```

### Open files of a process (forensics)
```bash
lsof -p <PID>
```

### Quick filtering
```bash
ps aux | grep nginx
```

---

## 📈 5. Monitoring: `top` & `htop`
### `top`
```bash
top
```
**Keyboard shortcuts:**
- **P** → sort by CPU
- **M** → sort by memory
- **k** → kill process
- **u username** → filter by user

### `htop`
```bash
htop
```
Features:
- Tree view
- F9 → kill
- Shows per-core CPU usage
- Environment variables (E)
- Threads individually displayed

### Cyber Tip
Great for spotting:
- crypto miners
- rogue background scripts
- resource spikes indicating malware

---

## 🔀 6. Background & Foreground Processes
### Run in background
```bash
command &
```

### Bring to foreground
```bash
fg
```

### Pause & background
Press **CTRL + Z**, then:
```bash
bg
```

### List jobs
```bash
jobs
```

💡 Attackers often hide scripts using `&` or `nohup`.

---

## 💣 7. The `kill` Command — Deep Dive
### Common Signals
| Signal | Number | Meaning | Usage |
|--------|--------|---------|-------|
| **SIGTERM** | 15 | safe terminate | default kill |
| **SIGKILL** | 9 | force kill | malware / hung processes |
| **SIGSTOP** | 19 | pause process | freeze suspicious malware |
| **SIGCONT** | 18 | resume | after inspection |
| **SIGHUP** | 1 | reload config | daemons, web servers |
| **SIGINT** | 2 | interrupt | same as CTRL+C |

### Send specific signal
```bash
kill -SIGSTOP <PID>
```

### Kill by name
```bash
pkill nginx
```

### Kill by user
```bash
pkill -u username
```

### Kill matching full command
```bash
pkill -f python
```

### Cyber Tip
During malware investigation:
1️⃣ Freeze with **SIGSTOP** (safe)  
2️⃣ Investigate with `lsof`, `strace`, `top`  
3️⃣ Kill only after confirmation

---

## ⚡ Quick Summary
| Tool | Use |
|------|------|
| **ps** | list processes + deep inspection |
| **pgrep/pkill** | find/kill by name or pattern |
| **top/htop** | live monitoring |
| **kill** | signal-based process control |
| **lsof** | see files, sockets, malware activity |
| **jobs/fg/bg** | manage background tasks |

---

Made for ⚡ **cybersecurity analysts**, **pentesters**, and **Linux warriors**.
