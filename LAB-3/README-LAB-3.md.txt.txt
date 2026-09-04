# CCNA 200-301 — Lab 3: Basic Router Configuration

This repository contains my completion documentation and configuration scripts for **Lab 3** of Jeremy's IT Lab CCNA 200-301 course.

---

## Lab Overview

The focus of this lab is initial Cisco IOS router configuration, basic network connectivity setup, and securing device access via CLI.

* **Course:** Jeremy's IT Lab — Cisco CCNA 200-301
* **Lab:** Lab 3 (Basic Router Configuration)
* **Simulator:** Cisco Packet Tracer

---

## Objectives

1. Access the router command-line interface (CLI) via console session.
2. Configure basic device settings (Hostname, Banner, Passwords).
3. Secure User EXEC and Privileged EXEC modes.
4. Configure IP addresses on router GigabitEthernet interfaces.
5. Enable interfaces and verify operational status using IOS display commands.
6. Test end-to-end connectivity using `ping`.

---

## Configuration Commands Summary

```text
! Enter privileged mode and global configuration mode
enable
configure terminal

! Set Hostname
hostname R1

! Secure Privileged EXEC Mode
enable secret Cisco123

! Configure Console Access
line console 0
password ConsolePass
login
exit

! Set Message of the Day (MOTD) Banner
banner motd # Authorized Access Only! #

! Configure Interface IP Addresses
interface GigabitEthernet0/0/0
ip address 192.168.1.1 255.255.255.0
no shutdown
exit

interface GigabitEthernet0/0/1
ip address 10.0.0.1 255.255.255.0
no shutdown
exit

! Save Configuration
end
copy running-config startup-config