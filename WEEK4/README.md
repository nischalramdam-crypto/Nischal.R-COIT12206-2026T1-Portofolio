# COIT12206 – Week 01 Portfolio

## 👤 Student Details

* Name: Nischal Ramdam
* Student ID: 12316714
* Date: 01/04/2026

---

## 🖥️ Network Setup

* Host1 & Host2 → Switch → Router → Host3

---

## 🌐 Configuration

```bash
# Host1
auto eth0
iface eth0 inet static
    address 10.1.1.11
    netmask 255.255.255.0
    gateway 10.1.1.1

# Host2
auto eth0
iface eth0 inet static
    address 10.1.1.12
    netmask 255.255.255.0
    gateway 10.1.1.1

# Host3
auto eth0
iface eth0 inet static
    address 10.1.2.11
    netmask 255.255.255.0
    gateway 10.1.2.1

# Router
auto eth0
iface eth0 inet static
    address 10.1.1.1
    netmask 255.255.255.0

auto eth1
iface eth1 inet static
    address 10.1.2.1
    netmask 255.255.255.0

# Enable routing
up sysctl net.ipv4.ip_forward=1
```

---

## 💻 Commands

```bash
ip address show
ping 10.1.1.11
ping 10.1.2.11
```

---

## 📸 Screenshots

![Network](images/network.png)
![Config](images/config.png)
![Ping](images/ping.png)

