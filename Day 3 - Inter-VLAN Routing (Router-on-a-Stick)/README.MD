\# Day 3 - Inter-VLAN Routing (Router-on-a-Stick)



\## 📌 Project Overview

This project focuses on bridging isolated Layer 2 broadcast domains by implementing controlled Layer 3 forwarding pathways. The design utilizes the standard \*\*Router-on-a-Stick (RoaS)\*\* architectural pattern, leveraging a single physical link partitioned into multiple logical subinterfaces to route traffic between distinct departmental VLANs securely and efficiently.



\## 🗺️ Network Topology

The lab environment features multiple access segments trunked up to a single core router.



!\[ROAS Topology](ROAS%20Topology.jpg)



\---



\## 🛠️ Technical Stack \& Implementation Details



\### 1. Logical Subinterface Provisioning

\* \*\*802.1Q Termination:\*\* Carved the router's physical interface into distinct logical subinterfaces corresponding to each host VLAN (e.g., `interface gig0/0.10`).

\* \*\*Tag Matching:\*\* Deployed explicit encapsulation parameters (`encapsulation dot1Q 10`) to ensure the router correctly interprets, strips, and adds VLAN tags for incoming and outgoing data frames.



\### 2. Trunking \& Path Isolation

\* \*\*Core-to-Edge Trunk:\*\* Configured the uplink switchport as an IEEE 802.1Q trunk, allowing multi-VLAN payloads to traverse the single physical medium toward the router.

\* \*\*Deterministic Gateways:\*\* Assigned unique IP addresses to each subinterface, acting as the local default gateway for their respective corporate segments.



\---



\## 📊 Verification \& Data Plane Deep-Dive



The following configurations and packet-level analyses have been verified within the lab environment to confirm seamless inter-subnet transit:



\### 🔹 Subinterface Mapping

Validating the creation of logical Layer 3 subinterfaces and their corresponding 802.1Q tag bindings.

!\[Sub-Interfaces Output](Sub-Interfaces.jpg)



\### 🔹 Packet-Level Inspection (Wireshark Capture)

Analyzing the frame structures to visually confirm the presence of the 4-byte 802.1Q header injected into transit traffic as it hits the backbone trunk link.

!\[Wireshark Capture](Wireshark.jpg)



\### 🔹 End-to-End Data Plane Proof

Executing cross-VLAN ICMP tracking from a host computer node to verify successful inter-subnet routing and network reachability.

!\[PC Ping Verification](PC-Ping.jpg)



\---

\## 👥 Author: John Ivan P. Ello | CCNA Certified

