# 📦 Kali Linux Package Management

This guide covers the essentials of managing software packages in Kali Linux using **apt**.  
You’ll learn how to update, search, install, verify, remove, purge, and clean up packages.

---

## 📜 Table of Contents
- [🔄 Step 1: Update & Upgrade](#-step-1-update--upgrade)
- [🔎 Step 2: Search for a Package](#-step-2-search-for-a-package)
- [📥 Step 3: Install a Package](#-step-3-install-a-package)
- [🛠 Step 4: Verify Installed Package](#-step-4-verify-installed-package)
- [❌ Step 5: Remove a Package](#-step-5-remove-a-package)
- [🧹 Step 6: Purge Config Files](#-step-6-purge-config-files)
- [🧽 Step 7: Autoremove Dependencies](#-step-7-autoremove-dependencies)
- [📌 Wrapping Up](#-wrapping-up)

---

## 🔄 Step 1: Update & Upgrade

Always update your system before working with packages.

```bash
sudo apt update
sudo apt full-upgrade -y
```

![apt update](/images/Package-Management/001.png)

---

## 🔎 Step 2: Search for a Package

Use `apt search` to find packages in the Kali repositories.

```bash
sudo apt search geoip-bin
```

![apt search](/images/Package-Management/002.png)

---

## 📥 Step 3: Install a Package

Install a package by name. In this example we install `geoip-bin`.

```bash
sudo apt install geoip-bin -y
```

![apt install](/images/Package-Management/003.png)

---

## 🛠 Step 4: Verify Installed Package

Check if the package works or view its version.

```bash
wireshark --version
```

![verify package](/images/Package-Management/004.png)

---

## ❌ Step 5: Remove a Package

Remove a package but leave its configuration files behind.

```bash
sudo apt remove geoip-bin -y
```

![apt remove](/images/Package-Management/005.png)

---

## 🧹 Step 6: Purge Config Files

Remove both the package and its configuration files.

```bash
sudo apt purge geoip-bin -y
```

![apt purge](/images/Package-Management/006.png)

---

## 🧽 Step 7: Autoremove Dependencies

Clean up unused libraries and dependencies left behind.

```bash
sudo apt autoremove -y
```

![apt autoremove](/images/Package-Management/007.png)

---

## 📌 Wrapping Up

In this section, you learned how to:
- Update and upgrade your system  
- Search for packages  
- Install and verify software  
- Remove and purge unwanted packages  
- Clean up dependencies  

🐉 Your Kali environment is now clean, organized, and ready for more tools.
