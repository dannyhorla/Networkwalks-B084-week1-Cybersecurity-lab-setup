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

![](

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

## 🔎 System and Network Verification

The following commands can be used to verify the Kali Linux environment.

### 1. Verify the Operating System

```bash
cat /etc/os-release

Purpose: Displays operating system information and the installed Kali Linux release.

### 2. Check Network Interface
