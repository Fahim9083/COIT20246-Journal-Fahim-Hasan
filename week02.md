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

VirtualBox is virtualization software that allows a computer to run virtual machines. A virtual machine works like a separate computer and can have its own operating system. VirtualBox is useful for learning, testing and running different operating systems without installing them directly on the physical computer.

---

## My Description of OpenWRT

OpenWRT is a Linux-based operating system designed mainly for networking devices such as routers. It provides tools and features for managing network connections and network settings. OpenWRT can also be run as a virtual machine, which makes it useful for learning about networking and network administration.

---

## AI Generated Description

### AI Prompt

Write a short description of VirtualBox and OpenWRT for a first-year IT student. Use simple language and explain what each one is used for.

### AI Description of VirtualBox

VirtualBox is virtualization software that allows users to create and run virtual machines on a computer. Each virtual machine can run its own operating system, making VirtualBox useful for learning, testing and using different operating systems.

### AI Description of OpenWRT

OpenWRT is an open-source Linux operating system designed mainly for routers and other networking devices. It provides advanced networking features and allows users to configure and manage network connections.

---

## Comparison Between My Description and AI Description

My descriptions and the AI-generated descriptions are similar because they both explain the main purpose of VirtualBox and OpenWRT. My VirtualBox description focuses on virtual machines and explains that they can run different operating systems. My OpenWRT description focuses on its use as a Linux-based operating system for networking.

The AI descriptions provide similar information but use slightly different wording and provide a little more detail. Overall, both descriptions explain the main purpose of VirtualBox and OpenWRT clearly.
