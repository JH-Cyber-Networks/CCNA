# CCNA Day 16 Lab: VLANs (Part 1) - Access Ports & VLAN Configuration

## Overview
This repository contains the Packet Tracer lab topology (`Day 16 Lab - VLANs Part 1.pkt`) and Cisco IOS configuration files for **Day 16** of *Jeremy's IT Lab CCNA 200-301 Course*.

The objective of this lab is to create and name Virtual Local Area Networks (VLANs) on Cisco Catalyst switches, configure access ports to assign end devices to specific broadcast domains, and verify proper frame isolation across switch ports.

---

## Lab Objectives
- Create database VLANs (`VLAN 10`, `VLAN 20`, etc.) and assign descriptive names.
- Configure interface ranges as `switchport mode access`.
- Assign switch access interfaces to their respective VLANs using `switchport access vlan <vlan-id>`.
- Verify VLAN database registration and access port assignments using Cisco IOS `show` commands.
- Test traffic separation between hosts across different VLANs without a Layer 3 routing device.

---

## Configuration Highlights

### 1. VLAN Creation & Naming
```cisco
Switch# configure terminal
Switch(config)# vlan 10
Switch(config-vlan)# name Engineering
Switch(config-vlan)# vlan 20
Switch(config-vlan)# name HR
Switch(config-vlan)# exit