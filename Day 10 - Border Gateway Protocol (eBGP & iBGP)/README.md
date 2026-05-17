\# Day 10 - Border Gateway Protocol (eBGP \& iBGP)



\## 📌 Project Overview

This project serves as the capstone of the Enterprise Network Engineering Series, focusing on the implementation, path propagation, and control-plane troubleshooting of the Border Gateway Protocol (BGP). The lab simulates a multi-provider WAN ecosystem, demonstrating how discrete Autonomous Systems (AS) interconnect and exchange routing prefixes across internet-scale boundaries while exploring the critical behavioral rules governing internal and external BGP peers.



\## 🗺️ Network Topology

The architecture features multiple routing nodes divided into distinct, isolated Autonomous Systems (AS 50000 and AS 50500) to trace multi-hop exterior path steering.



!\[BGP Topology](BGP%20Topology.jpg)



\---



\## 🛠️ Technical Stack \& Implementation Details



\### 1. External BGP (eBGP) Border Peering

\* \*\*AS Boundary Interconnection:\*\* Established external BGP adjacencies across autonomous boundaries over standard TCP port 179, facilitating inter-AS path vectors exchange.

\* \*\*Loop Prevention Mechanics:\*\* Leveraged native AS-Path attribute tracking to seamlessly detect and drop routing updates containing the local AS number, preventing routing loops across external transits.



\### 2. Internal BGP (iBGP) Core Distribution

\* \*\*Intra-AS Routing Fabrics:\*\* Configured internal BGP peer relationships within the core network to cleanly pass externally learned prefixes deep inside the local corporate backbone.

\* \*\*Next-Hop Attribute Remediation:\*\* Overcame default BGP next-hop behaviors—where an edge node leaves the external next-hop IP address unmodified when advertising to internal peers—by applying a strict `neighbor \[IP] next-hop-self` routing policy. This marks the local edge router as the reachable gateway, successfully validating prefixes on internal nodes.



\---



\## 📊 Verification \& Control Plane Diagnostics



The following routing tables and validation traces have been extracted from the environment to prove end-to-end multi-AS path convergence:



\### 🔹 Core Routing Table Injection (Show IP Route)

Analyzing the active routing matrix to verify successful network injection of prefixes learned via BGP, marked cleanly with the capital \*\*B\*\* indicator flag.

!\[Show IP Route Output](Show%20IP%20Route.jpg)



\### 🔹 End-to-End Inter-AS Verification (Ping \& Trace Route)

Executing comprehensive data plane ICMP tracking and hop-by-hop traceroutes to confirm seamless packet transit across autonomous network boundaries.

!\[IP ping and Trace Route Verification](IP%20ping%20and%20Trace%20Route.jpg)



\---

\## 👥 Author: John Ivan P. Ello | CCNA Certified

