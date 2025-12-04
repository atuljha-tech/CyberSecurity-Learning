🐧 Linux Terminal — Cybersecurity Notes (Detailed README)
📌 Overview

This section teaches you how to understand the Linux terminal deeply, use fundamental system-inspection commands, and learn how to retrieve help/documentation—all of which are crucial for cybersecurity, forensics, privilege escalation, and system auditing.

🧭 1. Getting to Know the Linux Terminal
✔ What is the Terminal?

The terminal is a text-based interface used for:

Issuing commands

Managing files, processes, networks, and users

Performing automation, forensics, and security operations

✔ Why Cybersecurity Needs the Terminal

Cyber experts rely heavily on the terminal to:

Inspect system activity

Detect intrusions (logs, processes, open ports)

Perform privilege escalation

Navigate servers without GUI

Automate security scripts

✔ Shells You Should Know

bash – default shell in most Linux distros

zsh – advanced shell with better completion

sh – lightweight POSIX shell

fish – user-friendly shell

Check your current shell:

echo $SHELL

🧪 2. NEW COMMAND: ps (Process Status)

The ps command shows running processes.
It's extremely important for malware detection, reverse engineering, and incident response.

🔹 Basic Usage
ps


Shows processes running under your current shell.

🔹 View all running processes
ps aux


a – all users

u – user-friendly format

x – include background/daemon processes

🔹 Check malicious activity example

Look for suspicious processes:

ps aux | grep python
ps aux | grep crypto

🔹 See process tree (great for detecting abnormal child processes)
ps axjf

⚡ 3. !!! NEW COMMANDS !!! (Essential Sysadmin + Security Commands)

Below are the core Linux reconnaissance commands every cybersecurity learner MUST know.

🆘 4. Getting Help in Linux (MAN & -h)
✔ man — manual pages

To read detailed documentation:

man ls
man ps
man ip


Exit with: q

✔ Quick Help (-h or --help)

Shows short explanations:

ls --help
ip -h

✔ whatis — one-line description
whatis ssh

✔ apropos — search for commands by keyword
apropos network
apropos user


Very useful in hacking labs when you don't know the exact command!

🛠 5. Essential Cybersecurity Commands (Detailed)

Below are the commands you listed — explained in detail with security relevance.

🔍 5.1 User & System Info Commands
🔹 id — Show user identity info
id


Shows:

UID (user ID)

GID (group ID)

Supplementary groups

Useful for privilege escalation.

🔹 hostname — System hostname
hostname


Attackers use this for enumeration during breaches.

🔹 uname — Kernel and OS information
uname

Common flags:
uname -r     # kernel version
uname -a     # EVERYTHING (kernel, OS, architecture)


➤ Extremely important for Kernel Exploit Research.

🌐 5.2 Network Commands
🔹 ifconfig (old tool)
ifconfig


Shows:

IP address

MAC address

Network interface status

🔹 ip (modern replacement for ifconfig)
ip a      # show all interfaces
ip r      # routing table
ip link   # interface hardware info

🔹 netstat (deprecated but still used in CTFs)
netstat -tulnp


Shows:

open ports

listening services

network connections

🔹 ss (modern netstat)
ss -tulnp


Much faster than netstat.

⚙ 5.3 Process & System Inspection
🔹 ps — process status

(covered above)

🔹 who — logged in users
who


Shows:

current logged-in users

remote login sessions
Used in incident response to detect unauthorized access.

🔹 env — environment variables
env


Used to detect:

PATH manipulation

malware persistence

misconfigurations

💾 5.4 Hardware & Storage Commands
🔹 lsblk — list block devices
lsblk


Shows:

disks

partitions

mount points
Use in forensics to inspect storage.

🔹 lsusb — connected USB devices
lsusb


Important for:

USB malware investigation

Hardware enumeration

🔹 lsof — list open files
lsof
lsof -i    # list network connections


Great for:

Detecting backdoors

Checking which processes use which ports

🏁 Summary Table (Quick Revision)
Command	Purpose	Cybersecurity Use
ps	Show processes	Detect malware, rogue processes
man	View manual pages	Learn features of commands
apropos	Find commands	Recon when unsure
id	User identity	Privilege escalation
hostname	System name	Enumeration
uname	Kernel info	Find kernel exploits
ifconfig / ip	Network info	IP, MAC, interface details
netstat / ss	Ports & connections	Detect open ports/backdoors
who	Logged-in users	Detect unauthorized access
env	Environment variables	Malware persistence detection
lsblk	Storage devices	Forensics & partitions
lsusb	USB devices	Hardware investigation
lsof	Open files & ports	Detect suspicious processes
