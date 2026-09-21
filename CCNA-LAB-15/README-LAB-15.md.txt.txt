# CCNA Day 15 Lab: VLSM (Variable Length Subnet Masking) & Static Routing

## Overview
This repository contains the Packet Tracer topology (`Day 15 Lab - VLSM.pkt`), addressing breakdown, and device configurations for **Day 15 Lab** from *Jeremy's IT Lab CCNA 200-301 Course*.

The primary objective of this lab is to subnet the base network **`192.168.5.0/24`** using **Variable Length Subnet Masking (VLSM)** to efficiently satisfy the host requirements for four distinct LANs and one point-to-point WAN link, followed by configuring static routes to achieve full end-to-end reachability.

---

## Lab Requirements & Addressing Plan

### Base Network
`192.168.5.0/24`

### Subnet Allocation (Largest to Smallest Requirement)

1. **LAN2 (64 Hosts required)**
- **Subnet ID:** `192.168.5.0/25`
- **Subnet Mask:** `255.255.255.128`
- **Usable IP Range:** `192.168.5.1` - `192.168.5.126`
- **Broadcast Address:** `192.168.5.127`
- **PC2 IP:** `192.168.5.1`
- **R1 G0/1 IP:** `192.168.5.126`

2. **LAN1 (45 Hosts required)**
- **Subnet ID:** `192.168.5.128/26`
- **Subnet Mask:** `255.255.255.192`
- **Usable IP Range:** `192.168.5.129` - `192.168.5.190`
- **Broadcast Address:** `192.168.5.191`
- **PC1 IP:** `192.168.5.129`
- **R1 G0/0 IP:** `192.168.5.190`

3. **LAN3 (14 Hosts required)**
- **Subnet ID:** `192.168.5.192/28`
- **Subnet Mask:** `255.255.255.240`
- **Usable IP Range:** `192.168.5.193` - `192.168.5.206`
- **Broadcast Address:** `192.168.5.207`
- **PC3 IP:** `192.168.5.193`
- **R2 G0/0 IP:** `192.168.5.206`

4. **LAN4 (9 Hosts required)**
- **Subnet ID:** `192.168.5.208/28`
- **Subnet Mask:** `255.255.255.240`
- **Usable IP Range:** `192.168.5.209` - `192.168.5.222`
- **Broadcast Address:** `192.168.5.223`
- **PC4 IP:** `192.168.5.209`
- **R2 G0/1 IP:** `192.168.5.222`

5. **Point-to-Point WAN (2 Hosts required)**
- **Subnet ID:** `192.168.5.224/30`
- **Subnet Mask:** `255.255.255.252`
- **Usable IP Range:** `192.168.5.225` - `192.168.5.226`
- **Broadcast Address:** `192.168.5.227`
- **R1 G0/0/0 IP:** `192.168.5.225`
- **R2 G0/0/0 IP:** `192.168.5.226`

---

## Configuration Summary

### R1 Static Route
Configured static route pointing to R2's LAN subnets (or a single summary route):
```cisco
R1(config)# ip route 192.168.5.192 255.255.255.192 192.168.5.226
