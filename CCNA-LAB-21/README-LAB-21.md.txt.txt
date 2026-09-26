# CCNA Day 21 Lab: Rapid Spanning Tree Protocol (RSTP - 802.1w)

## Overview
This repository contains the Packet Tracer topology (`Day 21 Lab - RSTP.pkt`) and Cisco IOS switch configurations for **Day 21** of *Jeremy's IT Lab CCNA 200-301 Course*.

The primary objective of this lab is to configure, verify, and analyze **Rapid Spanning Tree Protocol (Rapid PVST+)** across Cisco switches, observe fast topology convergence using proposal/agreement handshakes, and configure RSTP-specific port types and protection features.

---

## Lab Objectives
- Global transition from classic PVST+ (802.1D) to **Rapid PVST+ (802.1w)** using `spanning-tree mode rapid-pvst`.
- Identify and verify RSTP port roles (**Root Port**, **Designated Port**, **Alternate Port**, **Backup Port**).
- Identify and verify RSTP port states (**Discarding**, **Learning**, **Forwarding**).
- Configure RSTP **Edge Ports** using PortFast (`spanning-tree portfast`).
- Analyze RSTP link types (**Point-to-Point** vs. **Shared**).
- Verify RSTP operation and rapid convergence mechanisms using Cisco IOS `show` commands.

---

## Configuration Highlights

### 1. Enabling Rapid PVST+ Globally
```cisco
Switch1# configure terminal
Switch1(config)# spanning-tree mode rapid-pvst
