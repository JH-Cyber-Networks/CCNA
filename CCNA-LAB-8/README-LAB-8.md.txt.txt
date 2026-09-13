# CCNA 200-301 | Lab 08: Basic Switch Configuration & Security

## Overview
This repository contains the Packet Tracer topology and configuration documentation for **Lab 08** from Jeremy's IT Lab CCNA course. The objective of this lab is to configure initial switch settings, establish basic network connectivity, secure management access, and implement baseline switch hardening on Cisco IOS switches.

---

## Lab Objectives
- [x] Configure basic device parameters (Hostname, Banner MOTD).
- [x] Secure administrative access (Console password, Enable secret).
- [x] Configure management interface (SVI - VLAN 1) with an IP address and default gateway.
- [x] Configure SSH for secure remote access (Domain name, RSA keys, VTY lines).
- [x] Disable unused services and shutdown inactive interfaces.
- [x] Save active configurations to NVRAM (`startup-config`).

---

## Network Topology & Addressing Table

| Device | Interface | IP Address | Subnet Mask | Default Gateway |
| :--- | :--- | :--- | :--- | :--- |
| **PC1** | NIC | `192.168.1.10` | `255.255.255.0` | `192.168.1.1` |
| **PC2** | NIC | `192.168.1.11` | `255.255.255.0` | `192.168.1.1` |
| **SW1** | VLAN 1 | `192.168.1.2` | `255.255.255.0` | `192.168.1.1` |
| **SW2** | VLAN 1 | `192.168.1.3` | `255.255.255.0` | `192.168.1.1` |

---

## Key Configurations Summary

### 1. Basic Switch Hardening (SW1 Example)
```cisconetwork
SW1> enable
SW1# configure terminal
SW1(config)# hostname SW1
SW1(config)# enable secret Cisco123!
SW1(config)# banner motd # Authorized Access Only! #