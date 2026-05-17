\# Day 9 - Floating Static Routes (IPv4 + IPv6 Path Redundancy)



\## 📌 Project Overview

This project focuses on architecting deterministic path redundancy and high-availability (HA) routing fabrics at the enterprise edge. By deploying dual-stack (\*\*IPv4 and IPv6\*\*) Floating Static Routes, this lab establishes an automated failover mechanism. It trains the routing engine to utilize a high-speed primary transit link under standard conditions and immediately swing data payloads over to a backup path if a primary link failure is experienced.



\## 🗺️ Network Topology

The lab environment features a redundant diamond topology mapping out dual physical transit corridors (Primary vs. Backup/Backup Link) running between edge gateways.



!\[Floating Static Route Topology](Floating%20Static%20Route%20Topology.jpg)



\---



\## 🛠️ Technical Stack \& Implementation Details



\### 1. Administrative Distance (AD) Manipulation

\* \*\*Primary Path Anchoring:\*\* Configured standard static and default routes across both protocol suites, leaving them at their default Administrative Distance value of `1` so they are installed as the preferred routing choice inside the Forwarding Information Base (FIB).

\* \*\*Floating Backup Configuration:\*\* Deployed secondary static routes targeting the alternate transit link, manually inflating their Administrative Distance to `50` (e.g., `ip route 0.0.0.0 0.0.0.0 \[Backup-Next-Hop] 50`). This keeps the backup path hidden ("floating") outside the routing table as long as the primary path remains active.



\### 2. Dual-Stack Convergence Controls

\* \*\*IPv4 Fabric Redundancy:\*\* Managed routing parameters to govern legacy IP failover structures cleanly.

\* \*\*IPv6 Fabric Redundancy:\*\* Configured parallel next-generation static entries (`ipv6 route ::/0 \[Backup-IPv6-Next-Hop] 50`), ensuring complete parity across the enterprise dual-stack network perimeter.



\---



\## 📊 Verification \& Automated Failover Diagnostics



The following control plane tables and data plane tracing maps have been captured from the environment to validate resilient failover engineering:



\### 🔹 IPv4 Route Injection \& Path Validation

Analyzing the standard state routing table and testing data paths to confirm traffic tracks over the primary low-AD link corridor.

\* \*\*Routing Table Status:\*\*

&#x20; !\[IPv4 Show IP Route Output](IPv4%20Show%20IP%20Route.jpg)

\* \*\*Active Data Path Tracking:\*\*

&#x20; !\[IPv4 Trace Route Output](IPv4%20Trace%20Route.jpg)



\### 🔹 IPv6 Next-Gen Route Injection \& Path Validation

Validating native next-generation prefix convergence and tracking the operational active hop mapping across the IPv6 control plane.

\* \*\*Routing Table Status:\*\*

&#x20; !\[IPv6 Show IP Route Output](IPv6%20Show%20IP%20Route.jpg)

\* \*\*Active Data Path Tracking:\*\*

&#x20; !\[IPv6 Trace Route Output](IPv6%20Trace%20Route.jpg)



\---

\## 👥 Author: John Ivan P. Ello | CCNA Certified

