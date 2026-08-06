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
