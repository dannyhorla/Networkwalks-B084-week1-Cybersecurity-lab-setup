# 🔐 Cybersecurity Lab Setup Using Kali Linux and VirtualBox

![OS](https://img.shields.io/badge/Host%20OS-Windows%2011%20Pro-blue)
![Virtualization](https://img.shields.io/badge/Hypervisor-VirtualBox-orange)
![Linux](https://img.shields.io/badge/Guest%20OS-Kali%20Linux-557C94)
![Networking](https://img.shields.io/badge/Network-NAT%20Network-green)
![Focus](https://img.shields.io/badge/Focus-Cybersecurity-red)

## 📌 Project Overview

This project documents the deployment and configuration of a cybersecurity laboratory using Kali Linux running as a virtual machine inside Oracle VirtualBox on a Windows 11 Pro host.

The laboratory was established using a prebuilt Kali Linux VirtualBox image, providing a practical environment for learning Linux administration, network configuration, cybersecurity tools, and authorized security testing.

The virtual machine uses NAT Network mode to support outbound network connectivity and communication between virtual machines connected to the same NAT Network.

This project represents a foundational step toward developing practical skills in Security Operations Center (SOC) analysis, vulnerability assessment, penetration testing, and ethical hacking.

The lab will serve as a foundation for future hands-on cybersecurity exercises and technical projects.

---

## 🎯 Project Objectives

The primary objectives of this project are to:

- Set up a cybersecurity lab using Oracle VirtualBox.
- Deploy Kali Linux using a prebuilt VirtualBox image.
- Configure virtual machine resources and settings.
- Configure a NAT Network virtual network adapter.
- Verify the Kali Linux operating system and network configuration.
- Practise Linux command-line operations and network troubleshooting.
- Establish a controlled environment for authorized security testing.
- Prepare the environment for future penetration-testing and SOC analysis exercises.
- Document the setup process and technical findings.

---

## 🖥️ Lab Environment

The laboratory consists of a Windows host computer running Oracle VirtualBox, with Kali Linux operating inside a virtual machine.

### Hardware and Software Configuration

| Component | Configuration |
|---|---|
| Physical Computer | Dell Latitude E7470 |
| Host Operating System | Windows 11 Pro |
| Virtualization Platform | Oracle VirtualBox |
| Guest Operating System | Kali Linux |
| Installation Method | Prebuilt VirtualBox Image |
| Network Mode | NAT Network |
| Virtual Machine RAM | 2gb |
| Virtual CPU Allocation | 2 |
| Virtual Disk Capacity | 20GB |
| Kali Linux Version | 2026.3 |
| Additional Virtual Machines | Kioptrix, Metasploit, Devguru |

---

## 🏗️ Lab Architecture

The lab follows a virtualized architecture in which mainly Kali Linux and some other os run as guest operating system on a Windows 11 Pro host.

![](https://github.com/dannyhorla/Networkwalks-B084-week1-Cybersecurity-lab-setup/blob/main/Screenshot%20(11).png)


### Architecture Diagram

    +---------------------------------------------+
    |            Physical Computer                |
    |                                             |
    |              Dell Latitude E7470            |
    |                                             |
    |         +-------------------------+         |
    |         |      Windows 11 Pro     |         |
    |         |       Host OS           |         |
    |         |                         |         |
    |         |  +-------------------+  |         |
    |         |  | Oracle VirtualBox |  |         |
    |         |  |                   |  |         |
    |         |  |   +-----------+   |  |         |
    |         |  |   | Kali Linux|   |  |         |
    |         |  |   |           |   |  |         |
    |         |  |   | Security  |   |  |         |
    |         |  |   | Tools     |   |  |         |
    |         |  |   +-----------+   |  |         |
    |         |  +-------------------+  |         |
    |         +-------------------------+         |
    |                                             |
    +---------------------------------------------+
                         |
                         |
                   NAT Network
                         |
             +-----------+-----------+
             |                       |
       Internet Access       Other Connected VMs
       (Outbound Traffic)    (When Configured)

### Network Architecture

The Kali Linux virtual machine is configured to use a NAT Network.

This configuration allows virtual machines attached to the same NAT Network to communicate with one another and supports outbound connectivity through the host's network connection.

Additional virtual machines can be connected to the same NAT Network for controlled cybersecurity exercises.

The actual subnet, gateway, and IP addresses depend on the NAT Network configuration.

![](https://github.com/dannyhorla/Networkwalks-B084-week1-Cybersecurity-lab-setup/blob/main/Screenshot%20(9).png)

---

## 🛠️ Tools and Technologies

The following technologies are used in this project:

| Tool | Purpose |
|---|---|
| Windows 11 Pro | Host operating system |
| Oracle VirtualBox | Virtualization and VM management |
| Kali Linux | Cybersecurity testing and analysis environment |
| NAT Network | Virtual networking and connectivity |
| Linux Terminal | System administration and diagnostics |
| Nmap | Network discovery and service enumeration |
| Wireshark | Network traffic analysis |
| Burp Suite | Web application security testing |

Nmap, Wireshark, and Burp Suite are included as tools relevant to the intended learning objectives. Their inclusion does not imply that every tool has already been used in this project.

---

## ⚙️ Implementation and Setup Process

### Step 1: Prepare the Host System

The host system is a Dell Latitude E7470 running Windows 11 Pro.

Before deploying the virtual machine, available memory, processor resources, and disk capacity should be checked to ensure the system can support the virtualized environment.

### Step 2: Install Oracle VirtualBox

Oracle VirtualBox provides the virtualization platform required to run Kali Linux on the Windows host.

Official download:

https://www.virtualbox.org/wiki/Downloads

### Step 3: Obtain the Prebuilt Kali Linux VirtualBox Image

A prebuilt Kali Linux VirtualBox image was used instead of installing the operating system manually from an ISO file.

Prebuilt images simplify deployment because the virtual machine is already configured for use with VirtualBox.

Official Kali Linux downloads:

https://www.kali.org/get-kali/

The image should be obtained from the official Kali Linux website, and its integrity should be verified where applicable.

### Step 4: Import the Virtual Machine

The downloaded image was extracted and imported into Oracle VirtualBox.

The virtual machine was then made available through the VirtualBox Manager.

Official installation documentation:

https://www.kali.org/docs/virtualization/import-premade-virtualbox/

### Step 5: Configure Virtual Machine Resources

The virtual machine configuration includes resources such as:

- Random Access Memory (RAM).
- Virtual processors.
- Virtual hard disk.
- Network adapter.

Resource allocation should be adjusted according to the host computer's capabilities.

The actual values should be recorded in the lab configuration table.

### Step 6: Configure the NAT Network

The Kali Linux network adapter was configured to use NAT Network mode.

The configuration can be reviewed in VirtualBox Manager under the virtual machine's network settings.

The NAT Network configuration should also be checked in VirtualBox's Network Manager.

Important considerations:

- Confirm that the NAT Network is enabled.
- Confirm that the Kali virtual machine is attached to the intended NAT Network.
- Check whether DHCP is enabled if automatic IP addressing is required.
- Verify the assigned IP address and default route from Kali Linux.
- Ensure any additional lab virtual machines use the intended network.

### Step 7: Start Kali Linux

After importing and configuring the virtual machine, Kali Linux was started from VirtualBox Manager.

The guest operating system can then be used to perform system checks and network diagnostics.

---


## Step 8. Create a Clean VM Snapshot

After completing the initial configuration, a VirtualBox snapshot was created.

Example snapshot name:

```text
Clean Kali - Network Setup
```

The snapshot represents the clean baseline of the laboratory.

If a future exercise changes or damages the VM configuration, the machine can be restored to this baseline.


---

# 🔎 Lab Verification

| ✅ Test                        | 🧾 Command                      | 🎯 Expected Result              |
| ----------------------------- | ------------------------------- | ------------------------------- |
| 🌐 Check IP address           | `ip a`                          | Correct Kali IP displayed       |
| 📡 Test gateway               | `ping 10.0.0.1`                 | Successful replies              |
| 🌍 Test Internet connectivity | `ping 8.8.8.8`                  | Successful replies              |
| 🔎 Test DNS resolution        | `nslookup networkwalks.com`     | Domain resolves                 |
| 🧰 Verify Nmap                | `nmap --version`                | Nmap version displayed          |
| 🔄 Verify snapshot            | Restore snapshot and run `ip a` | Baseline configuration restored |

### Example Results

```text
IP Address:
10.0.0.2/24

Gateway:
10.0.0.1

DNS:
8.8.8.8
```

---

# 🐞 Problems Encountered & Solutions

Documenting problems is an important part of the project.

## Problem 1. Internet Connectivity After Static IP Configuration

After manually configuring the IPv4 settings, Internet connectivity may fail depending on the Kali/NetworkManager configuration.

One workaround used during this lab was:

```bash
sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0
```

The network connection was then restarted/rebooted and connectivity was tested again.

> **Important:** Network interface and connection names may differ between systems. Students should first identify their actual connection name before running an `nmcli` command.

---

## Problem 2. VirtualBox VT-x / Virtualization Error

The VM initially failed to start because hardware virtualization was disabled in the system firmware/BIOS.

The issue was resolved by:

1. Restarting the computer.
2. Entering BIOS/UEFI settings.
3. Enabling Intel VT-x / hardware virtualization.
4. Saving the configuration.
5. Restarting the computer.
6. Starting the Kali VM again.

After enabling virtualization, the VM started successfully.


---

# 💡 What I Learned

Through this project, I learned how to create and configure a virtual environment for cybersecurity practice.

The most important concepts I learned include:

### 1. NAT vs NAT Network

A standard NAT configuration and a NAT Network serve different purposes.

A NAT Network allows multiple VMs connected to the same virtual network to communicate with one another while providing network address translation for external connectivity.

This makes it useful for building a multi-machine cybersecurity laboratory.

### 2. Virtual Machine Networking

I learned how VirtualBox virtual network adapters connect virtual machines to different types of networks and how network configuration affects communication between machines.

### 3. Static IP Configuration

I learned how to configure and verify IPv4 addressing, subnet masks, gateways, and DNS settings in Kali Linux.

### 4. VM Snapshots

I learned that a clean snapshot should be created **before performing risky or experimental activities**.

This provides a known-good recovery point for future cybersecurity exercises.

### 5. Documentation

I learned that documenting commands, configuration, screenshots, problems, and solutions is an important part of a professional cybersecurity project.

---

# 🔐 Security & Ethical Use

This laboratory is intended strictly for education purposes only.

---

# 🔗 Tools & Resources

- **7-Zip:** [https://7-zip.org/download.html](https://7-zip.org/download.html)
- **VirtualBox:** [https://virtualbox.org/wiki/Downloads](https://virtualbox.org/wiki/Downloads)
- **Kali Linux:** [https://kali.org/get-kali](https://kali.org/get-kali)

---

# 👤 Author

**Adebayo Olaoluwa**\
Cybersecurity Intern B084

LinkedIn: https://www.linkedin.com/in/adebayo-olaoluwa-4a08b6404?utm_source=share_via&utm_content=profile&utm_medium=member_ios

---

## 📌 Project Information

**Program Name:** Cybersecurity at Networkwalks | **Week:** 01 | **Project:** Cybersecurity & Pentesting Lab Setup | **Repository:** GitHub
