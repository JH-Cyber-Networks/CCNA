# CCNA Day 22 Lab: Inter-VLAN Routing & Router-on-a-Stick (ROAS)

## Overview
This repository contains the Packet Tracer topology (`Day 22 Lab - Router-on-a-Stick.pkt`) and Cisco IOS device configurations for **Day 22** of *Jeremy's IT Lab CCNA 200-301 Course*.

The primary objective of this lab is to configure and verify **Inter-VLAN Routing** using the **Router-on-a-Stick (ROAS)** method. This involves creating subinterfaces on a single router physical interface, encapsulating traffic with IEEE 802.1Q tags, and setting up trunk links on connected switch interfaces.

---

## Lab Objectives
- Configure 802.1Q trunking on the switchport interface connected to the router (`switchport mode trunk`).
- Create and configure **Router Subinterfaces** on the router (`interface <type> <slot/port>.<subinterface-id>`).
- Configure IEEE 802.1Q encapsulation on each subinterface (`encapsulation dot1Q <vlan-id>`).
- Assign appropriate IP default gateway addresses and subnet masks to each subinterface.
- Configure native VLAN handling on subinterfaces (`encapsulation dot1Q <vlan-id> native`).
- Verify Inter-VLAN routing across separate VLANs using Cisco IOS `show` commands and host `ping` operations.

---

## Configuration Highlights

### 1. Switch Configuration (Trunk & Access Ports)
```cisco
Switch# configure terminal
! Configure interface facing the router as a trunk link
Switch(config)# interface GigabitEthernet0/1
Switch(config-if)# switchport mode trunk
Switch(config-if)# exit

! Assign host ports to respective VLANs
Switch(config)# interface FastEthernet0/1
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 10

Switch(config)# interface FastEthernet0/2
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 20
