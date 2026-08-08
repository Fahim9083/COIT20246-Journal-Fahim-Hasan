## Task 1 - complete the quize


![PowerShell Output](images/week3-task1.png)

## Task 2 - View Your Addresses

### Command

```powershell
ipconfig /all
```

### Screenshot

![PowerShell Output](images/week3-task2-powershell.png)

### Address Information

| Address | Value | Description |
|---------|-------|-------------|
| Host Name | DESKTOP-KTLTPI7 | The name of my computer on the network. |
| IPv4 Address | 172.20.10.9 | Identifies my computer on the local network. |
| Subnet Mask | 255.255.255.240 | Separates the network portion and host portion of the IP address. |
| Default Gateway | 172.20.10.1 | The router used to access other networks and the Internet. |
| Physical (MAC) Address | 70-CD-0D-43-2D-8F | A unique hardware address assigned to my Wi-Fi adapter. |
| DNS Server | 172.20.10.1 | Translates domain names into IP addresses. |

## Task 3 - Ping Your Local Router

### Command

```powershell
ping 172.20.10.1
```

### Screenshot

![Ping Local Router](images/week3-task3-ping-router.png)

### Ping Results

| Item | Value |
|------|-------|
| Default Gateway | 172.20.10.1 |
| Packets Sent | 4 |
| Packets Received | 4 |
| Packets Lost | 0 (0% loss) |
| Minimum Delay | 2 ms |
| Maximum Delay | 2 ms |
| Average Delay | 2 ms |

### How I Found the Delay

I used the ping 172.20.10.1 command in PowerShell. The minimum, maximum and average round-trip times were displayed in the "Approximate round trip times in milli-seconds" section of the output.

### Discussion

The ping results show a stable connection between my computer and the local router. The minimum, maximum and average delay were all 2 ms, indicating a fast and consistent local network connection.

Network delay can change over time because of:
- Wi-Fi signal strength
- Network congestion caused by multiple devices
- Background downloads or updates
- Router workload
- Temporary wireless interference

In this test, there was 0% packet loss, which indicates that the connection to the router was reliable.


## Task 4 - Ping Your OpenWRT Linux Server

### Commands Used

```bash
ip link
ip addr
tcpdump -i br-mng -w /tmp/week3-task4-ping.pcap
```

```powershell
ping 192.168.56.2
```

### OpenWRT Server Addresses

| Address | Value | Description |
|---------|-------|-------------|
| Interface | br-mng | Management network interface |
| IPv4 Address | 192.168.56.2 | The management IP address of the OpenWRT server |
| MAC Address | 08:00:27:51:DA:12 | The hardware (MAC) address of the br-mng interface |

### Packet Capture

I started packet capture on the OpenWRT server using `tcpdump` on the `br-mng` interface. Then I pinged the server from my Windows computer using `ping 192.168.56.2`. After the ping completed, I stopped the packet capture by pressing **Ctrl + C**.

The packet capture file was saved as:

`week3-task4-ping.pcap`

The `.pcap` file has been uploaded to my GitHub journal repository.


## Task 5 - Academic Integrity Policy

### Student Academic Integrity Policy and Procedure

I reviewed the CQUniversity Student Academic Integrity Policy and Procedure. The policy explains that academic integrity means acting with honesty, trust, fairness, respect and responsibility in learning, teaching and research.

### Five Levels of Academic Integrity Breaches

1. **Level 1 - Inappropriate Academic Conduct**
   - This is the lowest level of academic integrity breach.

2. **Level 2 - Minor Academic Misconduct**
   - This is a minor form of academic misconduct.

3. **Level 3 - Moderate Academic Misconduct**
   - This is a moderate level of academic misconduct.

4. **Level 4 - Substantial Academic Misconduct**
   - This is a substantial level of academic misconduct.
   - It can include plagiarism, self-plagiarism, collusion, cheating and contract cheating.

5. **Level 5 - Serious Academic Misconduct**
   - This is the most serious level of academic misconduct.
   - It can include plagiarism, self-plagiarism, collusion, cheating and contract cheating.

### Policy Document

The Student Academic Integrity Policy and Procedure PDF has been uploaded to my GitHub journal repository.
