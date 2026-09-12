# 🖥️ Cybersecurity Lab Setup

**Networkwalks Academy | Week 1 Project | Tools: VirtualBox + Kali Linux**

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

*(Insert your VirtualBox NAT Networks screenshot here once uploaded)*

The lab currently consists of one Kali Linux VM connected to a private NAT Network. Additional target machines can be added to the same network for future exercises.

---

## ⚙️ Lab Configuration

| Component           | Configuration                     |
|----------------------|------------------------------------|
| Host OS              | Windows 10                         |
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
