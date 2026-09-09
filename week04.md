# Week 4 - Network Technologies

## Task 1 - Knowledge Test

I completed the Week 4 Knowledge Test as part of the tutorial activities.

---

## Task 2 - Project Initiation

I joined a project group through the Group Formation - Project section on Moodle.

The project group was formed according to the requirements provided for the COIT20246 Networking and Cyber Security course.

---

# Task 3 - Draw Network Diagrams

## Task 3(a) - Switched LAN with One Switch

For this task, I created a switched Local Area Network (LAN) using diagrams.net (draw.io).

The network contains one switch and four PCs. Each PC is connected directly to the switch.

### Network Diagram

![Switched LAN with One Switch and Four PCs](images/week4-task3-lana.png)

### Original Draw.io File

[Download the original draw.io file](images/week4-task3-lana.drawio)

---

## Task 3(b) - Switched LAN with Three Switches

For this task, I created a switched LAN containing eight PCs and three switches.

Four PCs are connected to the first switch, and another four PCs are connected to the second switch. The two switches are then connected to a third switch, forming the required star topology.

### Network Diagram

![Switched LAN with Three Switches and Eight PCs](images/week4-task3-lanb.png)

### Original Draw.io File

[Download the original draw.io file](images/week4-task3-lanb.drawio)

---

# Task 4 - Analyse Ping Packet Capture

For this task, I analysed a previously captured ping packet file using Wireshark.

The packet capture was used to understand how ping operates from a networking and protocol perspective. I focused on ARP and ICMP packets and examined how data is encapsulated through different network layers.

---

## Task 4(a) - Inspect Packets in Wireshark

I opened the ping packet capture file in Wireshark and inspected the packets.

The main packets of interest were ARP packets and ICMP packets. Since many packets in the capture were similar, I focused on the different packets and their purpose.

### Wireshark Packet Capture

![Wireshark Ping Packet Capture](images/week4-task4-wireshark.png)

---

## Task 4(b) - Network Diagram

The network diagram shows the devices involved in the ping communication.

The diagram includes the known IP addresses and MAC addresses of the devices involved in the communication.

### Network Diagram

![Ping Network Diagram](images/week4-task4-ping.png)

### Original Draw.io File

[Download the original draw.io file](images/week4-task4-ping.drawio)

---

## Task 4(c) - Purpose of ARP Packets

ARP stands for Address Resolution Protocol.

ARP is used to find the MAC address associated with an IP address on a local network.

When a device knows the destination IP address but does not know the destination MAC address, it sends an ARP Request to discover the MAC address.

The ARP Request is sent by the device that needs to communicate with another device on the local network. The request asks which device owns the required IP address.

The device that owns that IP address responds with an ARP Reply containing its MAC address.

### ARP Communication

The ARP communication observed in Wireshark was analysed to determine:

- Who sent the ARP Request
- Which IP address was being requested
- Who received the request
- Which device responded
- The MAC address provided in the ARP Reply

---

## Task 4(d) - First ARP Packet Diagram

I analysed the first ARP packet in Wireshark and created a packet diagram to show its encapsulation.

The diagram identifies the relevant Ethernet header, ARP information and the overall packet size in bytes.

### First ARP Packet Diagram

![First ARP Packet Diagram](images/week4-task4-arp-packet.png)

### Original Draw.io File

[Download the original draw.io file](images/week4-task4-arp-packet.drawio)

---

## Task 4(e) - First Two ICMP Packets

The first two ICMP packets were examined in Wireshark.

The first packet is an ICMP Echo Request. It is sent by the source device to test whether the destination device is reachable.

The second packet is an ICMP Echo Reply. It is sent by the destination device in response to the Echo Request.

The Echo Request and Echo Reply are used by the ping command to test connectivity between two devices.

### Packet Analysis

**First ICMP packet:**

- Protocol: ICMP
- Type: Echo Request
- Source: [Enter source IP from Wireshark]
- Destination: [Enter destination IP from Wireshark]

**Second ICMP packet:**

- Protocol: ICMP
- Type: Echo Reply
- Source: [Enter source IP from Wireshark]
- Destination: [Enter destination IP from Wireshark]

---

## Task 4(f) - First ICMP Packet Diagram

I created a packet diagram for the first ICMP packet.

The diagram shows the main parts of the packet and demonstrates how the ICMP message is encapsulated within the network communication.

### First ICMP Packet Diagram

![First ICMP Packet Diagram](images/week4-task4-icmp-packet.png)

### Original Draw.io File

[Download the original draw.io file](images/week4-task4-icmp-packet.drawio)

---

# Task 5 - View ARP Table (Optional)

This task is optional.

The ARP table can be viewed using PowerShell to identify devices that are reachable by the computer on the local network.

After communicating with other devices, such as by using ping or accessing websites, the ARP table can be checked to see whether new devices have been discovered.

### ARP Table Screenshot

![ARP Table](images/week4-task5-arp-table.png)

### Reachable Devices

| Device | MAC Address | Reason |
|---|---|---|
| Device 1 | [Enter MAC address] | Discovered in the ARP table after network communication |
| Device 2 | [Enter MAC address] | Discovered in the ARP table after network communication |
