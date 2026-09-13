# CCNA 200-301 | Lab 11 (Part 1): Virtual Local Area Networks (VLANs)

## Overview
This repository contains the Packet Tracer topology and configuration documentation for **Lab 11 Part 1** from Jeremy's IT Lab CCNA course. This lab focuses on creating and configuring VLANs, assigning access ports to specific VLANs, isolating broadcast domains across layer 2 switches, and verifying VLAN operational status.

---

## Lab Objectives
- [x] Create VLANs in the switch VLAN database (`vlan <id>`).
- [x] Assign descriptive names to created VLANs (`name <name>`).
- [x] Configure switch access ports (`switchport mode access`).
- [x] Assign switch interfaces to specific access VLANs (`switchport access vlan <id>`).
- [x] Verify broadcast domain isolation between hosts on different VLANs without Layer 3 routing.

---

## Network Topology & VLAN Assignment Table

| Device | Interface | VLAN ID | VLAN Name | IP Address | Subnet Mask |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **PC1** | Fa0/1 | VLAN 10 | Engineering | `192.168.10.10` | `255.255.255.0` |
| **PC2** | Fa0/2 | VLAN 20 | HR | `192.168.20.10` | `255.255.255.0` |
| **PC3** | Fa0/3 | VLAN 10 | Engineering | `192.168.10.11` | `255.255.255.0` |
| **PC4** | Fa0/4 | VLAN 20 | HR | `192.168.20.11` | `255.255.255.0` |
| **SW1** | VLAN 10 | VLAN 10 | Engineering | `192.168.10.2` | `255.255.255.0` |

---

## Key Configurations Summary

### 1. VLAN Creation & Naming
```cisconetwork
SW1> enable
SW1# configure terminal

! Create and name VLAN 10
SW1(config)# vlan 10
SW1(config-vlan)# name Engineering
SW1(config-vlan)# exit

! Create and name VLAN 20
SW1(config)# vlan 20
SW1(config-vlan)# name HR
SW1(config-vlan)# exit