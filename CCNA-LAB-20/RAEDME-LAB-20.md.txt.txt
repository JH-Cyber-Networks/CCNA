# CCNA Day 19 Lab: Spanning Tree Protocol (STP) - Part 1

## Overview
This repository contains the Packet Tracer topology (`Day 19 Lab - STP Part 1.pkt`) and Cisco IOS switch configurations for **Day 19** of *Jeremy's IT Lab CCNA 200-301 Course*.

The primary objective of this lab is to observe classic IEEE 802.1D Spanning Tree Protocol operations, analyze the election process for the **Root Bridge**, **Root Ports**, **Designated Ports**, and **Non-Designated (Blocking) Ports**, and manually influence STP topology elections by modifying bridge priorities and port costs.

---

## Lab Objectives
- Understand the 802.1D STP Bridge Protocol Data Unit (BPDU) exchange.
- Identify the election parameters: **Bridge ID (Priority + MAC Address)** and **Path Cost**.
- Manually configure the Root Bridge primary and secondary priorities (`spanning-tree vlan <id> root primary` / `priority <value>`).
- Modify interface STP costs (`spanning-tree vlan <id> cost <value>`) to alter designated root paths.
- Verify STP states (**Blocking**, **Listening**, **Learning**, **Forwarding**) using standard Cisco IOS verification commands.

---

## Configuration Highlights

### 1. Manual Root Bridge Assignment
```cisco
! Setting SW1 as Primary Root Bridge for VLAN 1
SW1# configure terminal
SW1(config)# spanning-tree vlan 1 root primary
! Alternative explicit priority configuration (must be multiples of 4096):
SW1(config)# spanning-tree vlan 1 priority 4096