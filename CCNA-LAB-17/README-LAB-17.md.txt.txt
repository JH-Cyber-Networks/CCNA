# CCNA Day 17 Lab: VLANs (Part 2) - Trunk Ports & 802.1Q Encapsulation

## Overview
This repository contains the Packet Tracer lab topology (`Day 17 Lab - VLANs Part 2.pkt`) and Cisco IOS device configurations for **Day 17** of *Jeremy's IT Lab CCNA 200-301 Course*.

The primary objective of this lab is to configure and verify **802.1Q Trunk Links** between switches to allow traffic from multiple VLANs to travel across a single physical link while maintaining VLAN tagging and broadcast isolation.

---

## Lab Objectives
- Configure switch-to-switch interfaces as dynamic or static **Trunk Ports** (`switchport mode trunk`).
- Set explicit **802.1Q Encapsulation** on switches supporting multiple trunking protocols (`switchport trunk encapsulation dot1q`).
- Modify the **Native VLAN** on trunk interfaces (`switchport trunk native vlan <vlan-id>`) to ensure non-tagged traffic is processed correctly.
- Prune unneeded VLANs from trunk links using the **Allowed VLAN list** (`switchport trunk allowed vlan`).
- Verify trunking status and detect Native VLAN mismatch errors using Cisco IOS verification commands.

---

## Configuration Highlights

### 1. Static Trunk & Native VLAN Configuration
```cisco
Switch1# configure terminal
Switch1(config)# interface GigabitEthernet0/1
Switch1(config-if)# switchport mode trunk
Switch1(config-if)# switchport trunk native vlan 99