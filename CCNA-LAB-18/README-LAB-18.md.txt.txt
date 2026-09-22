# CCNA Day 18 Lab: Dynamic Trunking Protocol (DTP) & VLAN Trunking Protocol (VTP)

## Overview
This repository contains the Packet Tracer lab topology (`Day 18 Lab - DTP and VTP.pkt`) and Cisco IOS device configurations for **Day 18** of *Jeremy's IT Lab CCNA 200-301 Course*.

The primary objective of this lab is to configure, control, and analyze Cisco's proprietary **Dynamic Trunking Protocol (DTP)** modes to manage automatic trunk negotiation, disable unwanted DTP frames, and configure **VLAN Trunking Protocol (VTP)** in Server, Client, and Transparent modes.

---

## Lab Objectives
- Understand and configure DTP interface modes: `dynamic auto`, `dynamic desirable`, `trunk`, and `access`.
- Disable DTP negotiation on administrative trunk links using `switchport nonegotiate`.
- Configure VTP modes (Server, Client, Transparent), VTP domain names, and VTP passwords.
- Observe VTP Revision Number behavior and practice best practices for VTP security and deployment.
- Verify operational trunking states and VLAN database synchronization across switches.

---

## Configuration Highlights

### 1. DTP Negotiation & Disabling DTP
```cisco
Switch1# configure terminal
Switch1(config)# interface GigabitEthernet0/1
Switch1(config-if)# switchport mode dynamic desirable
! To disable DTP on an administrative trunk:
Switch1(config-if)# switchport mode trunk
Switch1(config-if)# switchport nonegotiate
