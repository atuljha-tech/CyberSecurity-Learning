# 🚀 Linux Processes, Daemons & systemd — Pro Notes
Clean, minimal, and powerful notes for cybersecurity, DevOps, SOC analysts, and Linux pros.

---

## 1️⃣ What is a Linux Process?
A **process** = a running program.

Every process has:
- **PID** (Process ID)
- **User** (running under)
- **CPU / RAM usage**
- **State** (running, sleeping, zombie)

### Types of Processes
✔ **Foreground** — attached to your terminal  
✔ **Background** — daemons/services running silently

---

## 2️⃣ Listing Processes
Most important commands:
```bash
ps              # processes in current shell
ps aux          # ALL system processes (most used)
ps -ef          # full-format listing
top             # real-time usage monitor
htop            # better top (colorful, interactive)
pstree          # parent → child hierarchy
```

---

## 3️⃣ Linux Daemons
**Daemons** = background services **with no terminal (no TTY)**.

Examples:
- `sshd` — SSH server
- `cron` — task scheduler
- `nginx`, `apache2` — web servers
- `mysql`, `postgres` — databases

### Pro Tip
In `ps aux` — **daemons show `?` under TTY**.

---

## 4️⃣ systemd — The Master Daemon
`systemd` = **PID 1**, the parent of *all* processes.

Controls:
- Boot process
- Starting/stopping services
- Logging
- Timers
- Mounts
- Sessions

Almost all modern Linux distros use `systemd`.

---

## 5️⃣ systemctl — Control Panel for Services
Use `systemctl` to manage **all daemons/services**.

---

### 🔧 Service Management Commands
```bash
sudo systemctl stop <service>       # stop service
sudo systemctl start <service>      # start service
sudo systemctl restart <service>    # restart service
sudo systemctl status <service>     # check status
sudo systemctl enable <service>     # enable at boot
sudo systemctl disable <service>    # disable at boot
```

---

## 🔍 Hunt for Daemons / Services
```bash
systemctl list-units --type=service        # active services
systemctl list-unit-files --type=service   # all installed services
ps aux | grep <keyword>                    # find suspicious processes
systemctl list-unit-files | grep enabled   # what starts at boot
```

---

## 🛠 Troubleshooting Services
### 1. Check logs
```bash
journalctl -u <service>
```

### 2. Monitor live behavior
```bash
top
htop
```

### 3. Restart cleanly
```bash
sudo systemctl restart <service>
```

### 4. Disable or stop suspicious processes
```bash
sudo systemctl disable <service>
sudo systemctl stop <service>
```

### 5. Inspect recent failures
```bash
systemctl --failed
```

---

## ⚡ Quick Summary
| Concept | Meaning |
|--------|---------|
| **Process** | Running program with PID |
| **Daemon** | Background service with no TTY |
| **systemd** | PID 1, manages entire system |
| **systemctl** | Command to control services |
| **ps aux** | Full process list |
| **journalctl** | View logs |

---

Made for ⚡ **hackers**, **admins**, **students**, and **Linux warriors**.
