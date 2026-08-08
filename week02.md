# Week 2 - Computer Systems and Applications

## Task 2 - Computer Information

### CPU

- CPU: 11th Gen Intel(R) Core(TM) i5-1135G7 @ 2.40GHz
- Maximum Clock Speed: 2419 MHz

![CPU Information](images/week2-task2-cpu.png)

### RAM

- Total RAM: 8,317,952,000 Bytes
- Total RAM: 7.93 GB

![RAM Information](images/week2-task2-ram.png)

### Disk

- Total Disk Size: 858.85 GB

![Disk Information](images/week2-task2-disk.png)

### Operating System

- OS Name: Microsoft Windows 11 Home Single Language
- OS Version: 10.0.26200 (Build 26200)

![Operating System Information](images/week2-task2-os.png)


## Task 3 - Deploy Linux Web Server in VirtualBox

### Boot Manager

- **Name:** GRUB 2
- **Version:** 2.06-3

I found the boot manager information by checking the installed GRUB packages in OpenWRT. I used the following command:

```bash
opkg list-installed | grep -i grub
```

The command showed the following installed GRUB packages:

- grub2 - 2.06-3
- grub2-bios-setup - 2.06-3
- grub2-efi - 2.06-3

This shows that GRUB 2 version 2.06-3 is installed.

![Boot Manager](images/week2-task3-boot.png)

---

### Linux Kernel

- **Name:** Linux Kernel
- **Version:** 5.10.161

I found the Linux kernel version by using the following command in the OpenWRT terminal:

```bash
uname -r
```

The command returned:

```text
5.10.161
```

Therefore, the Linux kernel version running on my OpenWRT system is 5.10.161.

![Kernel Version](images/week2-task3-kernel.png)

---

## My Description of VirtualBox

A computer can run virtual machines thanks to virtualization software called VirtualBox. A virtual machine can have its own operating system and functions similarly to a standalone computer. You may learn, test, and run various operating systems without physically installing them on your computer by using VirtualBox.

---

## My Description of OpenWRT

A Linux-based operating system called OpenWRT was created primarily for networking equipment like routers. It offers capabilities and tools for controlling network configurations and connections. OpenWRT is helpful for learning about networking and network administration because it can also be used as a virtual computer.

---

## AI Generated Description

### AI Prompt

Write a brief explanation of OpenWRT and VirtualBox for a first-year IT student. Explain each one's purpose using straightforward language.

### AI Description of VirtualBox

VirtualBox is a virtualization program that enables users to build and operate virtual machines on a computer. VirtualBox is helpful for studying, testing, and utilizing several operating systems because each virtual machine can run its own operating system.

### AI Description of OpenWRT

An open-source Linux operating system called OpenWRT was created primarily for routers and other networking equipment. Users may configure and manage network connections using its sophisticated networking features.

---

## Comparison Between My Description and AI Description

The primary goal of VirtualBox and OpenWRT is explained in both my and the AI-generated descriptions, which is why they are identical. Virtual machines are the main topic of my VirtualBox description, which also shows that they can run several operating systems. The use of OpenWRT as a Linux-based networking operating system is the main subject of my description.

While the AI descriptions offer similar information, they are slightly more detailed and have slightly different wording. In general, both explanations provide a clear explanation of the primary function of OpenWRT and VirtualBox.


## Task 4 - Browse to OpenWRT Websites

### Example Web Site

I accessed the example web site using the web browser on my Windows host operating system. The example web page loaded successfully.

![Example Web Site](images/week2-task4-openwrt.png)

---

### OpenWRT Management Interface

I accessed the OpenWRT management interface from my Windows web browser using the OpenWRT guest's management IP address.

The management interface was accessed using:

`http://192.168.56.2:81/cgi-bin/luci`

After logging in with the OpenWRT root account, I was able to view the OpenWRT status and system information.

![OpenWRT System Information](images/week2-task4-system.png)

---

### OpenWRT System Information

The following information was recorded from the OpenWRT management interface:

- **CPU:** 11th Gen Intel(R) Core(TM) i5-1135G7 @ 2.40GHz
- **Architecture:** x86/64
- **RAM:** 106.46 MiB (approximately 111,631,401 Bytes)
- **Disk Size:** 102.33 MiB (approximately 107,300,782 Bytes)
- **Operating System:** OpenWrt 22.03.3
- **Kernel Version:** 5.10.161

The OpenWRT management interface showed 106.46 MiB as the total available memory. The storage section showed a total disk space of 102.33 MiB.

---

### OpenWRT Network Information

The network information was obtained from the Network section at the bottom of the OpenWRT management interface.

- **Protocol:** DHCP client
- **Address:** 10.0.3.15/24
- **Gateway:** 10.0.3.2
- **DNS 1:** 172.20.10.1
- **DNS 2:** Not displayed
- **Device:** Ethernet Adapter: eth1
- **MAC Address:** 08:00:27:28:1B:C4

![OpenWRT Network Information](images/week2-task4-network.png)


## Task 5 - Complete Week 1 Tutorial

I went over my Week 1 journal to make sure I had finished all of the assignments. Additionally, I verified that my Knowledge Test screenshot and Week 1 journal entry were part of my GitHub repository.

I have now completed the Week 1 and Week 2 tutorial activities.
