# 👤 Kali Linux User Management

This guide walks through **basic user management** tasks in Kali Linux, including creating a new user, giving them sudo privileges, changing file ownership, and setting file permissions.  
These are foundational Linux admin skills you’ll use constantly in real-world environments.

---

## 📜 Table of Contents

- [👤 Add a New User](#-add-a-new-user)  
- [🔑 Grant Sudo Privileges](#-grant-sudo-privileges)  
- [📂 File Ownership](#-file-ownership)  
- [🔒 File Permissions](#-file-permissions)  
- [🔄 Switching Users](#-switching-users)  
- [📦 Wrapping Up](#-wrapping-up)  

---

## 👤 Add a New User

Create a new user with `adduser`. You’ll be asked to set a password and fill out optional info (full name, phone, etc.). Press **Enter** to skip fields and confirm with **Y**.

```bash
sudo adduser student
```

![Add User](/images/User-Management/001.png)

---

## 🔑 Grant Sudo Privileges

Add the new user to the **sudo group** so they can run admin commands.  
Check groups to confirm.

```bash
sudo usermod -aG sudo student
groups student
```

![Grant Sudo](/images/User-Management/002.png)

---

## 📂 File Ownership

Only the file’s owner (or root) can modify it. Use `ls -l` to check ownership.  
Example: root owns `example.txt`.

```bash
ls -l
```

![Check Owner](/images/User-Management/003.png)

Change ownership to `student`:

```bash
sudo chown student:student example.txt
ls -l
```

![Change Owner](/images/User-Management/004.png)

---

## 🔒 File Permissions

Use `chmod` to change access.  
Example: `600` means **owner has read/write, others have no access**.

```bash
sudo chmod 600 example.txt
ls -l
```

![Permissions](/images/User-Management/005.png)

### 🔑 Understanding Linux Permissions  

When you run `ls -l`, you’ll see file permissions represented like this:  

```
-rwxr-x---
```

This breaks down into **three groups of three characters**:  

- **Owner (user)** → `rwx`  
- **Group** → `r-x`  
- **Others (world)** → `---`  

Each letter stands for:  
- `r` = read  
- `w` = write  
- `x` = execute  

So:  
- `rwx` = full control (read, write, execute)  
- `r-x` = can read and execute, but not modify  
- `---` = no access  

When you use `chmod`:  
- `chmod 600 file.txt` → `rw- --- ---` (owner can read/write, group and others have no permissions)  
- `chmod 755 script.sh` → `rwx r-x r-x` (owner full access, group/others can read/execute)  

---

## 🔄 Switching Users

Switch to the new user with `su - student`.  
Check who you are with `whoami`.  
Exit to return to your main account.

```bash
su - student
whoami
exit
```

![Switch User](/images/User-Management/006.png)

---

## 📦 Wrapping Up

You now know how to:

- Create and manage users  
- Grant sudo rights  
- Change file ownership  
- Set file permissions (and understand rwx basics)  
- Switch between users  

These basics are critical for both **system administration** and **security hardening** in Linux. 🐉
