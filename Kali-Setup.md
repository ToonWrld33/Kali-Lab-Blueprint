# 🐉 Kali Linux VM Setup Guide

This guide walks you through setting up a Kali Linux Virtual Machine on Windows 11 using VirtualBox.  
It is beginner-friendly, screenshot-heavy, and step-by-step — designed to ensure you can follow along with no prior experience.

---

## 📜 Table of Contents

- [⚙️ Step 1: Verify Virtualization Support](#️-step-1-verify-virtualization-support)
- [💻 Step 2: Verify Minimum Requirements](#-step-2-verify-minimum-requirements)
- [📦 Step 3: Download Required Software](#-step-3-download-required-software)
- [🗂️ Step 4: Organize Your Files](#️-step-4-organize-your-files)
- [🖥️ Step 5: Install VirtualBox](#-step-5-install-virtualbox)
- [🖥️ Step 6: Install Extension Pack & 7-Zip](#-step-6-install-extension-pack--7-zip)
- [🗂️ Step 7: Extract Kali VM Files](#-step-7-extract-kali-vm-files)
- [🖥️ Step 8: Import Kali VM into VirtualBox](#-step-8-import-kali-vm-into-virtualbox)
- [🔧 Step 9: Configure VM Settings](#-step-9-configure-vm-settings)
- [▶️ Step 10: Start Kali VM & Log In](#-step-10-start-kali-vm--log-in)

---

## ⚙️ Step 1: Verify Virtualization Support

Before we begin, make sure your system supports virtualization.  

Open **Task Manager** → **Performance** tab → **CPU**.  
Look for **Virtualization: Enabled**.  

![Step 1](/images/Kali-VM-Setup/001.png)

- ✅ If enabled, continue.  
- ❌ If disabled, restart and enable it in your BIOS/UEFI.  

---

## 💻 Step 2: Verify Minimum Requirements

Minimum specs for Kali VM:  

- 🧠 **RAM**: 2 GB (4 GB+ recommended)  
- 💾 **Disk**: 20 GB (40–60 GB recommended)  
- ⚙️ **CPU**: 1 core minimum (2+ recommended)  
- 🌐 **Network**: Wired or USB WiFi adapter  

---

## 📦 Step 3: Download Required Software

1. **VirtualBox**  
   Download the latest Windows version.  
   ![Step 2](/images/Kali-VM-Setup/002.png)

2. **VirtualBox Extension Pack**  
   Download the matching Extension Pack.  
   ![Step 3](/images/Kali-VM-Setup/003.png)

3. **7-Zip** (64-bit)  
   Download 7-Zip (64-bit).  
   ![Step 4](/images/Kali-VM-Setup/004.png)

4. **Kali Linux VM Image**  
   Make sure to choose **Virtual Machines**, not the installer ISO.  
   ![Step 5](/images/Kali-VM-Setup/005.png)

5. **Choose VirtualBox Image**  
   Select the **VirtualBox** VM download. Avoid torrents/docs.  
   ![Step 6](/images/Kali-VM-Setup/006.png)

---

## 🗂️ Step 4: Organize Your Files

Create a folder on your **Desktop** called `Kali-VM-Setup`.  
Move all downloads (VirtualBox, Extension Pack, 7-Zip, Kali VM) into it.  

![Step 7](/images/Kali-VM-Setup/007.png)

---

## 🖥️ Step 5: Install VirtualBox

1. Double-click installer → allow changes.  
   ![Step 8](/images/Kali-VM-Setup/008.png)

2. Click **Next** through setup.  
   ![Step 9](/images/Kali-VM-Setup/009.png)

3. Accept license → **Next**.  
   ![Step 10](/images/Kali-VM-Setup/010.png)

4. Leave default setup → **Next**.  
   ![Step 11](/images/Kali-VM-Setup/011.png)

5. Warning: Network disconnect is normal → click Yes.  
   ![Step 12](/images/Kali-VM-Setup/012.png)

6. Missing dependencies → click Yes.  
   ![Step 13](/images/Kali-VM-Setup/013.png)

7. Setup options (Start menu, shortcut, start VM) → Next.  
   ![Step 14](/images/Kali-VM-Setup/014.png)

8. Ready to install → click Install.  
   ![Step 15](/images/Kali-VM-Setup/015.png)

9. Install complete → click Finish.  
   ![Step 16](/images/Kali-VM-Setup/016.png)

---

## 🖥️ Step 6: Install Extension Pack & 7-Zip

1. Double-click Extension Pack.  
   ![Step 17](/images/Kali-VM-Setup/017.png)

2. Click Upgrade to install pack.  
   ![Step 18](/images/Kali-VM-Setup/018.png)

3. Accept license → I Agree.  
   ![Step 19](/images/Kali-VM-Setup/019.png)

4. Install 7-Zip (allow changes).  
   ![Step 20](/images/Kali-VM-Setup/020.png)

5. Click Install.  
   ![Step 21](/images/Kali-VM-Setup/021.png)

6. Installation successful → Close.  
   ![Step 22](/images/Kali-VM-Setup/022.png)

---

## 🗂️ Step 7: Extract Kali VM Files

1. Right-click Kali VM download → Show more options.  
   ![Step 23](/images/Kali-VM-Setup/023.png)

2. 7-Zip → Extract to "Kali\".  
   ![Step 24](/images/Kali-VM-Setup/024.png)

3. Folder now contains extracted VM.  
   ![Step 25](/images/Kali-VM-Setup/025.png)

---

## 🖥️ Step 8: Import Kali VM into VirtualBox

1. VirtualBox → Machine → Open/New.  
   ![Step 26](/images/Kali-VM-Setup/026.png)

2. Navigate to extracted folder → select `Kali-amd64`.  
   ![Step 27](/images/Kali-VM-Setup/027.png)

3. Kali VM now appears in VirtualBox.  
   ![Step 28](/images/Kali-VM-Setup/028.png)

---

## 🔧 Step 9: Configure VM Settings

1. Increase RAM to ~4048 MB.  
   ![Step 29](/images/Kali-VM-Setup/029.png)

2. Leave processors at 2 CPUs.  
   ![Step 30](/images/Kali-VM-Setup/030.png)

---

## ▶️ Step 10: Start Kali VM & Log In

1. Start VM → Login (username: kali / password: kali).  
   ![Step 31](/images/Kali-VM-Setup/031.png)

2. Kali desktop successfully loaded.  
   ![Step 32](/images/Kali-VM-Setup/032.png)

---

🎉 Congratulations! You’ve successfully set up Kali Linux in VirtualBox.  
From here, you can move on to updates, customizing your VM, and installing pentesting tools.
