⚡ Linux Package Management — Hacker Notes
🧩 Overview

Linux packages are how tools, apps, libraries, and dependencies are installed.
For cybersecurity & hacking, package management is essential, because almost every tool you use comes from:

APT

dpkg

pip

git

gem

snap

This guide covers all of them — clean, fast, and hacker-focused.

🎯 1. What is a Linux Package?

A package =
program + files + metadata + version + dependencies

Contains:

Binaries

Config files

Libraries

Metadata

Dependency information

🔒 Why Hackers Care

Because most offensive/security tools (Nmap, SQLmap, Gobuster, Impacket, etc.) are installed as packages.

🛠️ 2. Package Managers (Your Arsenal)

Think of these like weapons to install / remove / update tools.

🔥 System-Level
Tool	Use-Case	Notes
dpkg	Install .deb manually	Low-level, dependency-blind
APT	Install from repos	Smart, safe, auto-deps
aptitude	Advanced APT	Great for dependency conflicts
snap	Universal sandbox apps	Heavy, isolated
🐍 Language-Level
Tool	Language	Purpose
pip	Python	Installs Python tool dependencies
gem	Ruby	For tools like wpscan
🌀 Git

Used to fetch hacking tools directly from GitHub.
Your “download any tool instantly” system.

🧩 3. dpkg — The Dumb Muscle

Use only when you downloaded a .deb manually

Commands
sudo dpkg -i tool.deb       # install
sudo dpkg -r tool           # remove
sudo dpkg -P tool           # purge config too
dpkg -l                     # list installed packages

❌ Why “Dumb”?

Doesn’t check dependencies

Can break your system if misused

Use sparingly.

⚙️ 4. APT — The Smart King

Hackers use APT the most because:

✔ Auto-fixes dependencies
✔ Stable
✔ Clean updates
✔ Large repos
✔ Safe

Daily Driver Commands
sudo apt update             # refresh repo list
sudo apt install nmap       # install tool
sudo apt remove nmap        # uninstall
sudo apt purge nmap         # uninstall + configs
sudo apt list --installed   # list everything
sudo apt upgrade            # normal update
sudo apt full-upgrade       # deep update (kernel etc.)

🏦 5. Repositories (Repos)

Your “tool shops.”

APT downloads from:

/etc/apt/sources.list
/etc/apt/sources.list.d/


Adding repos gives access to:

Newer versions

External tools

Vendor-specific packages

🚀 6. Snap (snapd)
Use Snap When:

You need the latest version

GUI applications

Tools not available in APT

Drawbacks:

Slow

Heavier

Sandboxed (isolated)

Install:
sudo snap install <tool>

🐍 7. pip & gem — For Scripted Tools
Python Workflow

Used by most GitHub hacking tools.

git clone <repo>
cd tool
pip3 install -r requirements.txt
python3 tool.py

Ruby Tools
gem install <package>


Example: wpscan

🌀 8. Git — The Hacker’s Lifeline

Used to download:

Recon tools

Exploits

Wordlists

Scripts

Frameworks

Commands:

git clone <repo-url>
cd repo

⚡ 9. Hacker Rules to Remember

✔ Use APT for 90% of installation

✔ Use dpkg only for .deb files

✔ Use pip for Python-based tools

✔ Use git clone for latest security tools

✔ Use snap only when nothing else exists

✔ Regularly update your system:

sudo apt update && sudo apt upgrade -y

💥 Super-Short Summary
Manager	Meaning	Best Use
APT	Smart Installer	Everyday tools
dpkg	Raw Installer	Manual .deb installs
snap	Sandboxed Installer	Apps not in APT
pip/gem	Language Installer	Python/Ruby tools
git	Fetch Code	Hacking tools from GitHub
