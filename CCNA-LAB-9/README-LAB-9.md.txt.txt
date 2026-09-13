# CCNA 200-301 | Lab 09: Switch Interface Configuration & Troubleshooting

## Overview
This repository contains the Packet Tracer topology and configuration documentation for **Lab 09** from Jeremy's IT Lab CCNA course. The focus of this lab is managing Cisco switch interfaces, manually configuring speed and duplex settings, resolving interface duplex mismatches, and configuring interface descriptions and range settings.

---

## Lab Objectives
- [x] Configure interface descriptions for network documentation and identification.
- [x] Hardcode interface speed and duplex parameters (`speed`, `duplex`).
- [x] Identify and resolve duplex mismatch conditions.
- [x] Utilize Cisco IOS interface range commands (`interface range`) for bulk configuration.
- [x] Verify interface status, error counters, and speed/duplex operational state.

---

## Network Topology & Addressing Table

| Device | Interface | Connected To | Speed / Duplex | Status |
| :--- | :--- | :--- | :--- | :--- |
| **SW1** | FastEthernet0/1 | SW2 Fa0/1 | Auto / Auto (or 100 / Full) | Connected |
| **SW1** | FastEthernet0/2 | PC1 NIC | 100 / Full | Connected |
| **SW2** | FastEthernet0/1 | SW1 Fa0/1 | Auto / Auto (or 100 / Full) | Connected |
| **SW2** | FastEthernet0/2 | PC2 NIC | 100 / Full | Connected |

---

## Key Configurations Summary

### 1. Bulk Interface Descriptions & Hardcoding Speed/Duplex
```cisconetwork
SW1> enable
SW1# configure terminal

! Configure connection to PC1
SW1(config)# interface FastEthernet0/2
SW1(config-if)# description Link to PC1
SW1(config-if)# speed 100
SW1(config-if)# duplex full
SW1(config-if)# no shutdown
SW1(config-if)# exit

! Configure trunk link interface to SW2
SW1(config)# interface FastEthernet0/1
SW1(config-if)# description Trunk Link to SW2
SW1(config-if)# speed auto
SW1(config-if)# duplex auto
SW1(config-if)# exit