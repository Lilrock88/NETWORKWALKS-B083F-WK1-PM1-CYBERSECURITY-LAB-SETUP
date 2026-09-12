# 🔐 Cybersecurity Lab Environment Setup

**Setting up a personal virtual lab for cybersecurity practice and hands-on learning**

![Skill](https://img.shields.io/badge/Skill-Cybersecurity-808080)
![Ver](https://img.shields.io/badge/Ver-Virtualbox%20v7.2-blue)
![Kali Linux](https://img.shields.io/badge/Kali%20Linux-v2026.1-orange)
![Skill](https://img.shields.io/badge/Skill-Linux-808080)
![Network](https://img.shields.io/badge/Network-10.0.0.0%2F24-4CAF50)
![Skill](https://img.shields.io/badge/Skill-Virtualization-808080)
![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github&logoColor=white)
![NetworkWalks](https://img.shields.io/badge/NetworkWalks-e74c3c)
![Author](https://img.shields.io/badge/Arilewola%20Abdulrokeeb-e74c3c)

---

## 📌 Project Overview

For this project, I built my own virtual cybersecurity lab using VirtualBox and Kali Linux. The goal was to create an isolated environment on my personal laptop where I can safely practice cybersecurity tools, scanning, and hands-on exercises without putting my real machine or my home network at risk.

---

## 🎯 Objectives

The main objectives of this project were to:

- Install VirtualBox and configure it as my hypervisor
- Import Kali Linux as a virtual machine
- Create a dedicated NAT Network for the lab
- Configure network connectivity for Kali Linux
- Assign a static IP address to the Kali VM
- Verify internet connectivity and DNS resolution
- Take a clean VM snapshot for recovery
- Document the whole process, including issues I ran into

---

## 🛡️ Purpose of the Lab

This lab gives me an isolated, controlled environment to practice cybersecurity skills without any risk to my actual laptop or home network. It can be used for things like network reconnaissance, scanning, vulnerability assessment, and general tool practice as I continue through the Networkwalks program.

⚠️ **Important:** This lab is strictly for practicing on systems I own or have explicit permission to test — not for use against any unauthorized system.

---

## 🏗️ Lab Architecture
<img width="1932" height="814" alt="Lab Architecture" src="https://github.com/user-attachments/assets/9f57689c-7426-4b87-aab0-ac400f62cba9" />


The lab currently consists of one Kali Linux VM connected to a private NAT Network. Additional target machines can be added to the same network for future exercises.

---

## ⚙️ Lab Configuration

| Component           | Configuration                     |
|----------------------|------------------------------------|
| Host OS              | Windows 11                         |
| Host RAM             | 8 GB                                |
| Processor            | Intel Core i5-6300U @ 2.40GHz       |
| Hypervisor           | VirtualBox 7.2.6                    |
| Security OS          | Kali Linux 2026.1                   |
| Kali RAM             | 2048 MB                             |
| Virtual Network      | NAT Network                         |
| Network Address      | 10.0.0.0/24                         |
| Kali IP Address      | 10.0.0.2/24                         |
| Default Gateway      | 10.0.0.1                            |
| DNS Server           | 8.8.8.8                             |
| Future VM Range      | 10.0.0.3 – 10.0.0.99                |

---

## 🪜 Lab Setup Procedure

### Step 1: Installed 7-Zip
I downloaded and installed 7-Zip so I could extract the Kali Linux VM files.

### Step 2: Installed VirtualBox
I installed VirtualBox 7.2.6 to use as my hypervisor on Windows 10.

### Step 3: Created a NAT Network
I created a dedicated NAT Network instead of using the default NAT setting, so that future VMs on this same network can communicate with each other while still reaching the internet. I initially couldn't find the Network tool in the VirtualBox menu, so I created it using the command line instead:
<img width="1918" height="1078" alt="nat-network-config" src="https://github.com/user-attachments/assets/7723f076-fbe4-4595-bc49-b755b3584dd2" />
## Step 4: Imported Kali Linux
I imported Kali Linux into VirtualBox and set the VM's Network Adapter 1 to attach to my newly created NAT Network, with the name set to NatNetwork.
<img width="1912" height="1076" alt="kali-linux" src="https://github.com/user-attachments/assets/d1cce8b6-0eb4-43b3-afd7-1256ce27c8fc" />

## Step 5: Configured Kali's Network
Inside Kali, I went to Edit Connections → Wired connection 1 → IPv4 Settings, and set it to Manual with:
- Address: 10.0.0.2
- Netmask: 24
- Gateway: 10.0.0.1
- DNS: 8.8.8.8
 <img width="1918" height="1077" alt="kali-network-configuration" src="https://github.com/user-attachments/assets/77d342f2-0e58-431f-ab87-fc850f4de275" />
 ## Step 6: Took a Clean Snapshot
After everything was working, I took a VirtualBox snapshot named **"Network walks"** to preserve this clean baseline so I can restore back to it if a future exercise breaks the configuration.
