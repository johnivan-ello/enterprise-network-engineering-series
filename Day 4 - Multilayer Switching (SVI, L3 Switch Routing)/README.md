\# Day 4 - Multilayer Switching Architecture (SVI \& L3 Switch Routing)



\## 📌 Project Overview

To offload high-latency routing overhead from traditional edge perimeters, this project transitions the network core into high-performance Multilayer Switches (MLS). This architecture achieves line-rate Inter-VLAN forwarding by utilizing Switched Virtual Interfaces (SVIs) and configuring dedicated routed ports to handle internal corporate traffic distribution natively within the hardware ASIC fabric.



\## 🗺️ Network Topology

The lab topology simulates a collapsed core model featuring a distribution-layer multilayer switch running down to access switches and endpoint nodes.



!\[Multilayer Switching Topology](Multilayer%20Switching%20Topology.jpg)



\---



\## 🛠️ Technical Stack \& Implementation Details



\### 1. Hardware Routing Initialization

\* \*\*ASIC Forwarding Core:\*\* Enabled the switch's global Cisco Express Forwarding (CEF) hardware engine using the `ip routing` command, converting the Layer 2 platform into an active Layer 3 routing plane.

\* \*\*Routed Ports:\*\* Converted standard access ports into point-to-point Layer 3 interfaces via the `no switchport` command to establish dedicated, non-broadcast transit links toward core perimeters.



\### 2. Switched Virtual Interfaces (SVIs)

\* \*\*Virtual Gateways:\*\* Instantiated logical Layer 3 Switched Virtual Interfaces (`interface vlan 10`) to serve as local high-speed default gateways for corresponding corporate access subnets.

\* \*\*Bottleneck Elimination:\*\* Offloaded traffic distribution onto the switch backplane, eliminating the single physical trunk link congestion common in Router-on-a-Stick designs.



\---



\## 📊 Verification \& Data Plane Diagnostics



The following configuration tables and verification captures have been extracted from the environment to validate optimal Layer 3 switching fabrics:



\### 🔹 SVI Operational Status

Verifying the instantiation, line protocol state, and IP mapping of the localized Switched Virtual Interfaces.

!\[Interface Vlans Status](Interface%20Vlans.jpg)



\### 🔹 Path Traversal Analysis (Ping \& Traceroute)

Executing end-to-end ICMP tracking and hop-by-hop traceroutes to visually confirm path steering across the internal hardware switching boundaries.

!\[Ping and Traceroute Verification](Ping%20and%20Traceroute.jpg)



\---

\## 👥 Author: John Ivan P. Ello | CCNA Certified

