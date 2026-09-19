# CCNA 200-301 - Day 12 Lab: The Life of a Packet

## Overview
This repository contains my completion documentation and configuration analysis for **Day 12 Lab: The Life of a Packet** from **Jeremy's IT Lab CCNA 200-301 Complete Course**.

The purpose of this lab is to use Cisco Packet Tracer's **Simulation Mode** to trace and analyze how data flows across local and remote network segments, observing encapsulation/de-encapsulation, ARP table resolution, and routing table lookups at each hop.

---

## Lab Objectives
* Observe the step-by-step process of a host encapsulating data into IP packets and Ethernet frames.
* Analyze how **ARP (Address Resolution Protocol)** resolves unknown next-hop MAC addresses.
* Verify default gateway operations when traffic is destined for an outside/remote IP network.
* Track how source and destination **MAC addresses change at every layer-3 hop**, while source and destination **IP addresses remain constant**.
* Inspect switch MAC address tables and router routing tables during frame processing.

---

## Topology & Environment
* **Simulator:** Cisco Packet Tracer
* **Key Components:**
* Local Hosts / PCs (End Devices)
* Layer 2 Switches (Access Layer)
* Cisco IOS Routers (Default Gateways & Inter-network Routing)

---

## Execution & Analysis

### 1. Initial State & ARP Request
* **Trigger:** Initiated a `ping` from host PC1 to a remote host across a router hop.
* **Observation:** Because PC1 lacked the destination layer-2 MAC address for its default gateway, an ARP request was generated first.
* **Result:** ARP broadcast requested the MAC address associated with the default gateway IP. The router responded with its inbound interface MAC address.

### 2. Encapsulation & Hop-by-Hop Behavior
* **Layer 3:** Source IP (`PC1`) and Destination IP (`Remote Host`) remained intact across the entire path.
* **Layer 2 (Local Segment):** Source MAC was set to `PC1`, and Destination MAC was set to `Router Gateway Interface`.
* **At the Router:**
1. Router de-encapsulated the Layer 2 Ethernet frame.
2. Inspected the Layer 3 IP header and queried its routing table.
3. Re-encapsulated the packet into a new Layer 2 frame with:
* **New Source MAC:** Outbound interface of the Router.
* **New Destination MAC:** Interface of the next-hop router or destination end-device.

---

## Key Takeaways
1. **IP vs. MAC Scope:** IP addresses specify the ultimate end-to-end source and destination, whereas MAC addresses only specify the next hop on a local link.
2. **Encapsulation Cycle:** Routers strip the incoming Layer 2 header and apply a new Layer 2 header for each egress interface/network segment.
3. **Simulation Mode Value:** Using Packet Tracer's PDU inspector provided clear visibility into L2/L3 headers at each stage of transmission.

---

## How to Use
1. Download the `.pkt` file from this repository.
2. Open the file in **Cisco Packet Tracer**.
3. Switch to **Simulation Mode** and click **Capture / Forward** to inspect the Packet Data Units (PDUs) frame-by-frame.
