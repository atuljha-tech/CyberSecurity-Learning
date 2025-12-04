# 🐧 Linux File System & Essential Commands — Complete Notes

A clean, structured README-style document based on your timestamps.

---

## 📌 1. `whoami` (1:39)

**Purpose:** Shows which user is currently logged in.

```
whoami
```

Useful for checking if you're root or a normal user.

---

## 📌 2. 10‑Second Review (2:02)

* Linux is a **multi-user**, **multi-tasking OS**.
* Everything is structured inside the **Linux File System hierarchy**.
* Commands interact with files/directories.

---

## 📌 3. Root of the File System `/` (2:28)

* `/` is the **topmost directory**.
* Everything begins from here.
* All other directories are inside `/`.

```
/
├── bin
├── etc
├── home
├── lib
├── usr
└── ...
```

---

## 📌 4. `clear` (2:45)

Clears the terminal screen.

```
clear
```

Shortcut: `Ctrl + L`

---

## 📌 5. Everything is a File!! (3:03)

* In Linux, **files, folders, devices, processes → all treated as files**.
* Even hardware like disks, keyboard, etc.

Examples:

* `/dev/sda` → hard disk
* `/dev/null` → black hole file

---

## 📌 6. `/bin` (3:40)

Contains **essential commands** needed for basic system usage.
Examples:

* `ls`
* `cp`
* `mv`
* `cat`
* `rm`

These commands load before the OS fully boots.

---

## 📌 7. `cat` (4:49)

Reads and displays file content.

```
cat filename.txt
```

---

## 📌 8. `cp` (5:43)

Copies files and directories.

```
cp file1 file2
cp -r dir1 dir2
```

---

## 📌 9. `rm` (7:12)

Deletes files or directories.

```
rm file.txt
rm -r folder
```

⚠️ Permanent deletion — no recycle bin.

---

## ⚠️ 10. "I deleted a command!" (7:25)

* If you delete something from `/bin` or `/usr/bin`, system commands can stop working.
* Never remove system binaries.

---

## 📌 11. `/sbin` (8:48)

Contains **system administration binaries**.
Only root can run most of these.
Examples:

* `adduser`
* `mount`
* `shutdown`

---

## 📌 12. `adduser` (9:27)

Creates a new user.

```
sudo adduser atul
```

---

## 📌 13. `/usr` (10:11)

The largest directory.
Contains:

* `/usr/bin` → Most user commands
* `/usr/lib` → Libraries
* `/usr/share` → Shared data

---

## 📌 14. `which` (11:32)

Shows the path of a command.

```
which ls
```

Output example:

```
/bin/ls
```

---

## 📌 15. `/boot` (12:47)

Contains bootloader files:

* Kernel
* GRUB config

---

## 📌 16. `/var` (12:52)

Stores **variable data** like logs.
Examples:

* `/var/log`
* `/var/cache`

---

## 📌 17. `/tmp` (12:58)

Temporary files.
Automatically deleted.

---

## 📌 18. `/lib` (13:04)

Shared libraries needed by binaries.
Equivalent to Windows `.dll` files.

---

## 📌 19. `/home` (13:12)

Contains personal user directories.

```
/home/atul
/home/rahul
```

User files, downloads, configs stay here.

---

## 📌 20. `/root` (13:40)

Home directory of the **root user**.
Not the same as `/`.

---

## 📌 21. `/dev` (14:10)

Device files.
Examples:

* `/dev/sda` → disk
* `/dev/tty` → terminal

---

## 📌 22. `/etc` (15:33)

**Configuration files**.
Examples:

* `/etc/passwd`
* `/etc/hosts`
* `/etc/ssh/ssh_config`

---

## 📌 23. `/mnt` and `/media` (17:11)

Used for mounting.

* `/mnt` → manual mounts by admin
* `/media` → auto-mounted devices like USB

---

## 🏁 Final Challenge Summary (19:24)

This README gives you:

* Full directory-by-directory explanation
* Command references
* Clean, structured Linux filesystem understanding

If you'd like, I can also:

* Add diagrams
* Add advanced notes
* Create a printable PDF
* Create flashcards

Just tell me! 🚀
