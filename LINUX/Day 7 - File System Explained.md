🐧 Linux Terminal — Cybersecurity Mastery Guide
📖 Table of Contents
Introduction

Terminal Basics

Process Management

Help & Documentation

User & System Info

Network Analysis

Hardware & Storage

Quick Reference

Resources

🎯 Introduction
This guide teaches Linux terminal commands specifically for cybersecurity operations. Essential for:

Penetration Testing 🔓

Incident Response 🚨

Forensic Analysis 🔍

System Auditing 📊

CTF Challenges 🏴‍☠️

🖥️ Terminal Basics
What is the Terminal?
A text-based interface for controlling Linux systems. Used for:

Command execution

File management

Process control

Network operations

Security automation

Why Cybersecurity Needs the Terminal
Direct system access

Lightweight & fast

Scriptable operations

Remote access capability

Granular control

Shell Types
bash
# Check current shell
echo $SHELL
Shell	Purpose
bash	Default Linux shell
zsh	Enhanced completion
sh	POSIX compliant
fish	User-friendly
🔬 Process Management
ps — Process Status
Shows running processes. Critical for:

Malware detection

Reverse engineering

Incident response

Basic Usage
bash
ps
ps -ef
View All Processes
bash
ps aux
a → all users

u → user-friendly format

x → include background processes

Check for Malicious Activity
bash
ps aux | grep python
ps aux | grep crypto
Process Tree
bash
ps axjf
ps -ef --forest
🆘 Help & Documentation
man — Manual Pages
bash
man ls
man ps
man ssh
Exit with q

Quick Help
bash
ls --help
ip -h
whatis — One-line Description
bash
whatis ssh
apropos — Search by Keyword
bash
apropos network
apropos user
Great when you don't know the exact command

👤 User & System Info
id — User Identity
bash
id
Shows:

UID

GID

Groups

Used in privilege escalation

hostname — System Name
bash
hostname
Used in system enumeration

uname — Kernel Info
bash
uname -a
uname -r   # kernel version
Critical for kernel exploit research

who — Logged-in Users
bash
who
Detect unauthorized access

env — Environment Variables
bash
env
Find PATH manipulation and persistence

🌐 Network Analysis
ifconfig (Legacy Tool)
bash
ifconfig
Shows:

IP address

MAC address

Interface status

ip (Modern Tool)
bash
ip a      # show interfaces
ip r      # routing table
ip link   # hardware info
netstat (Deprecated but Common)
bash
netstat -tulnp
Shows:

Open ports

Listening services

Current connections

ss — Modern Replacement
bash
ss -tulnp
Faster and more accurate

💾 Hardware & Storage
lsblk — Block Devices
bash
lsblk
Shows:

Disks

Partitions

Mount points

Used in forensic analysis

lsusb — USB Devices
bash
lsusb
USB malware investigation

lsof — Open Files & Ports
bash
lsof
lsof -i   # network connections
Detect backdoors and trace processes

🏁 Quick Reference
Command	Purpose	Cybersecurity Use
ps	Show processes	Detect malware/backdoors
man	Manual pages	Learn commands
apropos	Find commands	Reconnaissance
id	User identity	Privilege escalation
hostname	System name	System enumeration
uname	Kernel info	Exploit research
ifconfig/ip	Network info	IP/MAC discovery
netstat/ss	Ports & connections	Backdoor detection
who	Logged-in users	Access monitoring
env	Environment variables	Persistence detection
lsblk	Storage devices	Disk forensics
lsusb	USB devices	Hardware investigation
lsof	Open files	Process tracing
📚 Resources
Practice Environments
Linux VM

Docker containers

Online Linux terminals

Learning Platforms
TryHackMe

HackTheBox

OverTheWire

Documentation
Always check man pages

Linux documentation project

Command cheat sheets

