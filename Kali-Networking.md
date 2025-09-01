# 🌐 Kali Linux Networking Basics

This guide covers the essential networking steps for your Kali Linux VM.  
You’ll learn how to check your interfaces, verify connectivity, connect a USB WiFi adapter, and understand NAT vs Bridged networking in VirtualBox.

---

## 📜 Table of Contents
- [🔎 Step 1: Check Network Interfaces](#-step-1-check-network-interfaces)
- [📶 Step 2: Verify Internet Connectivity](#-step-2-verify-internet-connectivity)
- [🔌 Step 3: Attach USB WiFi Adapter](#-step-3-attach-usb-wifi-adapter)
- [📡 Step 4: Confirm Adapter is Recognized](#-step-4-confirm-adapter-is-recognized)
- [⚡ Step 5: NAT vs Bridged Networking](#-step-5-nat-vs-bridged-networking)
- [📌 Wrapping Up](#-wrapping-up)

---

## 🔎 Step 1: Check Network Interfaces

Kali provides two ways to view your network interfaces.

```bash
ifconfig
```

![ifconfig](/images/Network-Basics/001.png)

```bash
ip a
```

![ip a](/images/Network-Basics/002.png)

- `lo` → loopback interface (internal only)  
- `eth0` → your primary wired adapter (NAT/Bridged)  
- `wlan0` → will appear once a USB WiFi adapter is attached  

---

## 📶 Step 2: Verify Internet Connectivity

Test connectivity with both an IP and a domain name.

```bash
ping -c 4 8.8.8.8
```
![ping 8.8.8.8](/images/Network-Basics/003.png)

```bash
ping -c 4 google.com
```
![ping google.com](/images/Network-Basics/004.png)

- If the IP ping works but DNS fails → check your DNS resolver (`/etc/resolv.conf`).  

---

## 🔌 Step 3: Attach USB WiFi Adapter

To use WiFi in Kali, attach a USB WiFi adapter through VirtualBox.  
Make sure the VM is **powered off** before editing USB settings.

1. In **VirtualBox Manager**, right-click your Kali VM → **Settings** → **USB**.  
2. Enable USB 2.0 or 3.0 controller (depending on your adapter).  
3. Add your adapter to the list.  

![USB Settings](/images/Network-Basics/005.png)

When the VM is running, also ensure the adapter is checked from the **bottom USB menu**:

![USB Menu](/images/Network-Basics/006.png)

---

## 📡 Step 4: Confirm Adapter is Recognized

Once attached and firmware is installed, verify the adapter is working:

```bash
lsusb
```
![lsusb](/images/Network-Basics/007.png)

```bash
ifconfig
```
![ifconfig wlan0](/images/Network-Basics/008.png)

```bash
iwconfig
```
![iwconfig](/images/Network-Basics/009.png)

Now `wlan0` should be listed and available for wireless operations.  

Tips if you don’t see `wlan0`:  
- Unplug/replug the adapter  
- Switch VirtualBox USB mode (2.0 ↔ 3.0)  
- Ensure the correct firmware is installed (`firmware-misc-nonfree`)  
- Run `dmesg | grep mt76` to check for driver errors  

---

## ⚡ Step 5: NAT vs Bridged Networking

By default, VirtualBox uses **NAT (Network Address Translation)**.  
This shares your host’s connection and works for most cases.  

Some lab scenarios may require **Bridged**, which gives Kali its own IP on your LAN.  

1. Power off your VM.  
2. In **VirtualBox Manager** → **Settings → Network**, open the dropdown.  

![Network Dropdown](/images/Network-Basics/010.png)

- **NAT** → VM hides behind host IP. Easy and safe for internet.  
- **Bridged Adapter** → VM gets its own LAN IP (e.g. 192.168.x.x). Useful for acting as a separate machine on the network.  
- **Host-only** → VM can only talk to the host. Useful for isolated testing.  

In most cases, leave it on **NAT** unless you specifically need Bridged.

---

## 📌 Wrapping Up

In this section, you learned how to:
- Check interfaces with `ifconfig` / `ip a`  
- Verify connectivity with `ping`  
- Attach and confirm a USB WiFi adapter  
- Understand NAT vs Bridged in VirtualBox  

Your Kali VM is now network-ready and prepared for the next step: installing and using tools. 🐉 
