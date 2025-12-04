# 🐧 Linux Filesystem & Commands — Cybersecurity Notes
A complete, structured, detailed reference for beginners and cybersecurity learners.  
Covers essential Linux commands and full filesystem hierarchy explained deeply.

---

# 🔥 1. Basic Linux Commands

## **whoami**
Shows the current logged-in user.  
Useful to check permissions before executing system-level commands.

---

## **clear**
Clears the terminal screen for better readability.

---

## **cat**
Displays file content.  
Commonly used to read:
- `/etc/passwd`
- `/etc/ssh/sshd_config`
- config files

---

## **cp (copy)**
Copies files or folders.  
Flags:
- `-r` → recursive (required for directories)
- `-p` → preserve permissions

---

## **rm (remove)**
Deletes files or directories.  
Dangerous flags:
- `rm -rf /` → destroys system  
Use with caution.

---

## **adduser**
Creates a new user and sets up:
- `/home/username`
- permissions
- password prompts

---

## **which**
Shows the path of a command’s executable.  
Good for locating binaries and recovering deleted commands.

---

# 🔥 2. Linux Filesystem — Deep Breakdown

Linux follows the **FHS (Filesystem Hierarchy Standard)**.  
Everything begins from the **root directory `/`**.

---

# 🗂️ Root Directory `/`
The top-most parent of the Linux filesystem.  
Every file or directory stems from here.

---

# 🗂️ `/bin` — Essential User Commands
Contains user essential programs:
- `ls`, `cp`, `mv`, `rm`, `bash`, `cat`

Always available even in recovery mode.

---

# 🗂️ `/sbin` — System/Admin Commands
Commands used mainly by root:
- `iptables`, `fdisk`, `mount`, `reboot`

Normal users can’t run these without sudo.

---

# 🗂️ `/usr` — Installed Software (Non-essential)
Contains apps installed by the system or user.

### `/usr/bin`
User applications like:
- `python`, `nmap`, `gcc`

### `/usr/sbin`
Admin programs not required at boot.

### `/usr/lib`
Libraries for `/usr/bin` and `/usr/sbin`.

### `/usr/local`
Manual or custom-installed software.

---

# 🗂️ `/boot` — Bootloader & Kernel
Contains:
- Linux kernel (`vmlinuz`)
- initramfs
- GRUB bootloader configs

Without `/boot`, the system cannot start.

---

# 🗂️ `/lib` — Essential Libraries
Libraries needed by `/bin` and `/sbin`.  
Includes:
- libc
- kernel modules

Corruption here breaks the OS.

---

# 🗂️ `/home` — User Home Directories
Personal directories:
/home/atul
/home/john

yaml
Copy code
Stores documents, SSH keys, configs, downloads.

---

# 🗂️ `/root` — Superuser’s Home
Home directory for **root** user.  
Stores sensitive admin data.

---

# 🗂️ `/etc` — Configuration Brain of Linux
Contains system-wide config files:
- `/etc/passwd`
- `/etc/shadow`
- `/etc/ssh/sshd_config`
- `/etc/hosts`
- `/etc/fstab`

Critical for cybersecurity, system hardening, and troubleshooting.

---

# 🗂️ `/dev` — Devices as Files
Represents hardware as files:
- `/dev/sda` → HDD/SSD
- `/dev/tty` → terminal
- `/dev/random`

Linux treats **everything as a file**.

---

# 🗂️ `/var` — Variable Data & Logs
Contains:
- `/var/log/` (system logs)
- mail
- web server files
- databases
- caches

Important for digital forensics & monitoring.

---

# 🗂️ `/tmp` — Temporary Files
Used for:
- app temp data
- caches
- session files

Often cleared automatically on reboot.  
Attackers frequently drop temporary payloads here.

---

# 🗂️ `/mnt` — Temporary Mount Point
Used by administrators to manually mount drives:
mount /dev/sdb1 /mnt

yaml
Copy code

---

# 🗂️ `/media` — Auto-Mount for USB/External Devices
Devices like:
- USB drives
- CDs/DVDs
- SD cards  
are auto-mounted here.

---

# 🗂️ Advanced Directories

## **/proc**
Virtual filesystem showing live system data:
- CPU info
- memory info
- running processes

Used in forensics & malware detection.

---

## **/sys**
Kernel and hardware information in real time.

---

## **/run**
Stores runtime process data:
- PID files
- service states

---

## **/srv**
Data for system services:
- web servers
- databases
- FTP

---

## **/opt**
Optional third-party or large software packages.

---

# 🔥 3. Why Everything Is a File (Core Linux Philosophy)
Linux treats:
- hardware
- processes
- devices
- kernel data  
all as files.

This makes the system:
- simple  
- predictable  
- powerful  
- easy to script  

---

# 🔥 4. Cybersecurity Relevance

### **Pentesting**
- Find misconfigured `/etc` permissions  
- Analyze logs `/var/log`  
- Check user data `/home`  
- Inspect `/proc` for hidden processes  

### **Malware Analysis**
- Malware often hides in `/tmp`  
- Modifies `/etc` for persistence  
- Drops binaries in `/usr/bin`  

### **Digital Forensics**
- Boot tampering in `/boot`  
- Log analysis in `/var/log`  
- User activity in `/home`  

---

# 🎯 5. Directory Quick Summary

| Directory | Purpose |
|----------|---------|
| `/bin` | Essential system commands |
| `/sbin` | Admin commands |
| `/etc` | Configuration files |
| `/home` | User data |
| `/root` | Root user home |
| `/usr` | Installed programs |
| `/var` | Logs & variable data |
| `/lib` | System libraries |
| `/boot` | Kernel & bootloader |
| `/dev` | Hardware devices |
| `/tmp` | Temporary files |
| `/mnt` | Manual mounts |
| `/media` | External media |

---

# ✅ End of README 
