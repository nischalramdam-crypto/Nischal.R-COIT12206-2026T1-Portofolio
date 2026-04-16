# VLAN Configuration and Inter-VLAN Routing using GNS3

## Course

COIT12206 – TCP/IP Principles and Protocols

---

# Project Overview

This project explores how Virtual Local Area Networks (VLANs) can be used to segment a network and control communication between devices. The work is divided into two parts:

* **Task 1:** Configuring VLANs and verifying network isolation
* **Task 2:** Enabling communication between VLANs using a router

---

# Task 1: VLAN Configuration and Network Isolation

![Task1 Network](projectcreate.png)

---

## Network Topology

![Task1 Network](topology.png)

The setup includes four hosts connected to a single Open vSwitch. At this stage, no router is present, meaning all communication depends entirely on VLAN configuration.

---

## Host Addressing

Each host was manually assigned an IP address within the same subnet:

* Host1 → 10.10.1.101
* Host2 → 10.10.1.102
* Host3 → 10.10.1.103
* Host4 → 10.10.1.104

![Configuration](h1.png)
![Configuration](h2.png)
![Configuration](h3.png)
![Configuration](h4.png)

---

## VLAN Configuration

To logically divide the network, VLAN tagging was applied on the switch ports using Open vSwitch commands:

```
ovs-vsctl set port eth1 tag=10
ovs-vsctl set port eth2 tag=10
ovs-vsctl set port eth3 tag=20
ovs-vsctl set port eth4 tag=20
```

* VLAN 10 includes Host1 and Host2
* VLAN 20 includes Host3 and Host4

This configuration ensures that devices are grouped logically rather than physically.

![VLAN Setup](Setport.png)

---

## Switch Verification

![Task1 Ports](tag.png)
![Task1 Ports](tag2nd.png)

The screenshots confirm that VLAN tags have been successfully applied to the respective ports on the switch.

---

## Connectivity Testing

![Task1 Ping](h1pingtoall.png)
![Task1 ping](h4.png)

Testing was performed using the `ping` command to verify communication:

* Devices within the **same VLAN** were able to communicate successfully
* Devices in **different VLANs** could not communicate

This confirms that VLAN segmentation is functioning as expected.

---

## ARP Behaviour Analysis

![Task1 Ports](DifferentVLAN.png)
![Task1 Ports](arp-a.png)

ARP (Address Resolution Protocol) results further validated the isolation:

* Within the same VLAN, MAC addresses were resolved correctly
* Across VLANs, ARP requests failed, resulting in incomplete entries

This behaviour occurs because VLANs create separate broadcast domains, preventing ARP messages from crossing between them.

---

## Challenges Faced

During the implementation, several issues were encountered:

* Incorrect VLAN tagging initially caused unexpected connectivity
* Some ports were not properly assigned, leading to communication errors
* ARP results were confusing at first but became clear after understanding broadcast domain separation

These issues were resolved by carefully verifying switch configuration and rechecking port assignments.

---

## Explanation

VLANs work by dividing a single physical network into multiple logical networks. Each VLAN acts as an independent broadcast domain, meaning devices in one VLAN cannot directly communicate with devices in another VLAN without routing.

In this task, even though all hosts shared the same IP range, VLAN tagging ensured that traffic remained isolated. This demonstrates how VLANs enhance network security and organization without requiring additional hardware.

---

## Conclusion (Task 1)

The experiment successfully demonstrated VLAN-based network segmentation. Devices were grouped into separate logical networks, and communication was restricted accordingly.

This confirms that VLANs are an effective method for controlling traffic flow and improving network structure.

