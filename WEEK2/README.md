# TCP/IP Configuration - Week 1

## Student Details
- Name: Nischal Ramdam
- Student ID: 12316714
- Course: COIT12206
- Date: 11/03/2026

---

## Project Overview
This project demonstrates a basic TCP/IP configuration using GNS3. A single Linux host was added to the topology and configured with a static IP address. The configuration was verified through the console.

---

## Task Summary
- Created a new GNS3 project
- Added one Linux host
- Configured a static IP address for Host1
- Verified the configuration through the console
- Captured screenshots as evidence of completion

---

## Network Topology
- 1 Linux Host: Host1
- Standalone host topology for basic IP configuration practice

---

## IP Configuration
- IP Address: 10.10.1.1
- Subnet Mask: 255.255.255.0
- Gateway: 192.168.0.1
- DNS: 192.168.0.1

---

## Configuration Code

```bash
auto eth0
iface eth0 inet static
    address 10.10.1.1
    netmask 255.255.255.0
    gateway 192.168.0.1
    up echo nameserver 192.168.0.1 > /etc/resolv.conf
```

---

## Screenshots

### Project Creation
![Project](1.png)
![Project](step1.png)

### Host Configuration
![Config](Config-host1.png)
![Config](Config-host2.png)
![Config](console-host3png)
![Config](console-host4.png)

### Console Output
![Console](ip-host1.png)
![Console](ip-host2.png)
![Console](ip-host3.png)
![Console](ip-host4.png)


### Ping View
![Ping](Ping-success-1to2.png)
![Ping](ping-failure.png)
![Ping](ping-success.png)
![Ping](ping-sucess-4to2.png)

---

## Learning Outcome
This task helped me understand how to create a simple GNS3 project, assign a static IP address to a Linux host, and verify the network configuration using terminal commands.

---

## Author
**Nischal Ramdam**
