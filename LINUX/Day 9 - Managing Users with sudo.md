# 🛡️ Linux Users, Groups & Privileges — Cybersecurity Notes

### **Professional README.md — Clean, Structured & Perfect for GitHub**

---

## **1. The Linux User (2:26)**

Linux is a **multi‑user operating system**, meaning multiple accounts can work simultaneously.

### **Types of Users**

| Type            | Description                         | Example            |
| --------------- | ----------------------------------- | ------------------ |
| **Root User**   | Superuser with unlimited privileges | `uid=0`            |
| **Normal User** | Assigned to actual human users      | `uid=1000+`        |
| **System User** | Created for services/daemons        | `www-data`, `sshd` |

### **Why Cybersecurity Cares**

* Attackers always try to escalate from **normal → root**.
* Weak/misconfigured users = open door for unauthorized access.

---

## **2. UNDER ATTACK!! (3:11)**

Attackers commonly search for:

* Passwordless accounts
* Default users
* Misconfigured `/etc/passwd`, `/etc/shadow`, `sudoers`
* Weak or world-writable privileges

### **Security Goal:**

Audit, detect, and lock down user accounts.

---

## **3. NEW COMMAND — `adduser` (3:49)**

```
sudo adduser alice
```

Interactive method to create a user.

### **What it does:**

* Creates home directory
* Sets default shell
* Sets password
* Adds to default groups

### **Cybersecurity Impact:**

Enforces strong passwords and secure home permissions.

---

## **4. Finding Users in Linux (5:10)**

### **View all users:**

```
cat /etc/passwd
```

### **Logged in users:**

```
who
w
```

### **Current user:**

```
whoami
```

### **Security Use:**

* Enumerate suspicious accounts.
* Verify no attacker-created accounts exist.

---

## **5. Exploring `/etc/passwd` (6:00)**

Contains basic user account info.

### **Format:**

```
username:x:UID:GID:comment:home:shell
```

### **Red Flag:**

⚠️ **Any user with UID 0 besides root = backdoor superuser.**

---

## **6. `/etc/shadow` — Hashed Passwords (6:25)**

Only root can read.

### **Red Flags in Security:**

* Empty password field = **extremely dangerous**
* Old hash types (like MD5 `$1$`)
* Attackers try to steal this file for offline cracking

---

## **7. NEW COMMAND — `useradd` (7:50)**

Low-level alternative to `adduser`.

```
sudo useradd -m -s /bin/bash bob
sudo passwd bob
```

### **Used For:**

Scripts, automation, fast provisioning.

---

## **8. NEW COMMAND — `passwd` (9:16)**

### **Change Password:**

```
sudo passwd alice
```

### **Lock Account:**

```
sudo passwd -l alice
```

### **Force Reset:**

```
sudo passwd -e alice
```

### **Cybersecurity Use:**

Lock compromised or unused accounts.

---

## **9. NEW COMMAND — `usermod` (10:30)**

```
sudo usermod -l newname oldname
sudo usermod -s /bin/zsh alice
sudo usermod -d /new/home alice
```

### **Security Use:**

* Disable login shell for risky accounts:

```
sudo usermod -s /usr/sbin/nologin apache
```

---

## **10. The `sudo` Command (13:05)**

Allows execution as another user (default root). Example:

```
sudo apt update
```

### **Security Warning:**

Avoid:

```
ALL=(ALL) NOPASSWD: ALL
```

This gives **passwordless root**, extremely dangerous.

---

## **11. NEW COMMAND — `su` (14:20)**

Switch user:

```
su bob
su -
su root
```

### **Notes:**

* Fewer logs than sudo → attackers prefer it.

---

## **12. The sudoers File (16:03)**

Location: `/etc/sudoers`

Controls **who can run what** as which user.

### **Edit only using:**

```
sudo visudo
```

---

## **13. NEW COMMAND — `visudo` (16:21)**

Safely edits sudoers; prevents misconfigurations.

### **Example Rule:**

```
alice ALL=(ALL:ALL) ALL
```

---

## **14. NEW COMMAND — `userdel` (19:10)**

Delete user:

```
sudo userdel alice
```

Delete user + home directory:

```
sudo userdel -r alice
```

### **Security:**

Remove inactive accounts quickly.

---

## **15. NEW COMMAND — `groupadd` (20:06)**

Create new group:

```
sudo groupadd devteam
```

---

## **16. Exploring `/etc/group` (20:41)**

Contains system group info.

```
group_name:x:GID:user1,user2
```

### **Security Risk:**

Attackers add themselves to:

* `sudo`
* `docker`
* `lxd`
  These effectively give **root privileges**.

---

## **17. NEW COMMAND — `groups` (21:27)**

Check groups:

```
groups
```

Check another user's groups:

```
groups alice
```

---

## **18. Breaking sudoers (22:20)**

A single incorrect line can:

* Break sudo
* Lock everyone (except root) out of privilege escalation

### **Security Lesson:**

Always use **visudo**.

---

## **19. NEW COMMAND — `usermod -aG` (23:39)**

Add user to group:

```
sudo usermod -aG docker alice
sudo usermod -aG sudo alice
```

### **Security Note:**

Adding user to **sudo** or **docker** = giving **root power**.

---

## **20. NEW COMMAND — `gpasswd` (25:06)**

Group management:

```
sudo gpasswd -a alice devteam
sudo gpasswd -d bob devteam
sudo gpasswd -A admin devteam
```

Useful in access control scenarios.

---

# ✅ End of Notes — Professional README.md Ready

Let me know if you want:

* A **PDF / DOCX version**
* A **colored cheat sheet**
* More diagrams
* A **Linux Privilege Escalation companion guide**
