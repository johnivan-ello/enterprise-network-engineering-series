\# Day 8 - IPv6 Routing Protocols Baseline



\## 📌 Project Overview

This project transitions the enterprise routing infrastructure into next-generation networking by configuring, validating, and comparing fundamental IPv6 dynamic and static routing protocols. Operating across isolated GNS3 environments, this lab explores the unique behavior of IPv6 link-local addresses, global unicast configurations, and protocol state machine transitions across four discrete architectures: Static/Default, RIPng, OSPFv3, and EIGRP for IPv6.



\## 🗺️ Network Topology

The lab topology maps out an identical dual-stack-ready physical layout used to systematically analyze the control planes of each next-generation routing engine.



!\[IPv6 Routing Topology](IPv6%20Topology.jpg)



\---



\## 🛠️ Technical Stack \& Implementation Details



\### 1. Global Multicast \& Unicast Routing

\* \*\*Engine Initialization:\*\* Activated native IPv6 packet processing and interface forwarding globally across all nodes using the critical `ipv6 unicast-routing` command.



\### 2. IPv6 Static \& Default Routing Engine

\* \*\*Next-Hop Steering:\*\* Configured point-to-point static routes using explicit IPv6 next-hop global unicast addresses.

\* \*\*Gateway of Last Resort:\*\* Implemented the IPv6 equivalent of a quad-zero default route (`ipv6 route ::/0 \[Next-Hop-Address]`) at the perimeter boundary to handle anonymous upstream transit.



\### 3. RIP Next Generation (RIPng)

\* \*\*Distance-Vector Evolutions:\*\* Instantiated classless RIPng, manually configuring the dynamic process directly under interface sub-menus via `ipv6 rip \[process-name] enable` rather than using standard global network statements.



\### 4. OSPFv3 (Open Shortest Path First v3)

\* \*\*Link-State Next-Gen Integration:\*\* Deployed OSPFv3 natively on interfaces (`ipv6 ospf 1 area 0`) to establish adjacencies over IPv6 link-local addresses (`FE80::/10`), separating the protocol from dependency on specific global IPv6 subnets.

\* \*\*Process Stability ID:\*\* Hardcoded an explicit 32-bit IPv4-formatted Router ID (`8.8.8.8`) to allow the OSPFv3 database engine to initialize safely.



\### 5. EIGRP for IPv6

\* \*\*Advanced Vector Routing plane:\*\* Configured EIGRP for IPv6 using an autonomous system structure (`ipv6 router eigrp 100`).

\* \*\*DUAL Engine Activation:\*\* Hardcoded a 32-bit Router ID and executed the `no shutdown` command inside the global protocol configuration menu to activate the loop-free Diffusing Update Algorithm (DUAL) topology matrix.



\---



\## 📊 Verification \& Control Plane Captures



The following terminal outputs have been captured and verified across each standalone environment to validate successful next-hop convergence:



\### 🔹 IPv6 Static \& Default Route Validation

Confirming static entries and default exit gateways inside the IPv6 routing table.

!\[IPv6 Static Output](IPv6%20Static%20and%20Default%20Routing.jpg)



\### 🔹 RIPng Process Verification

Reviewing active interface participation and dynamic prefix learning over the RIPng routing process.

!\[IPv6 RIP Output](IPv6%20RIP.jpg)



\### 🔹 OSPFv3 Neighbor Adjacency Validation

Verifying Link-Local neighbor handshakes, area designations, and successful `FULL` state synchronization.

!\[IPv6 OSPF Output](IPv6%20OSPF.jpg)



\### 🔹 EIGRP for IPv6 Operational Status

Analyzing successor routes, interface bindings, and loop-free metric convergence inside the EIGRPv6 topology table.

!\[IPv6 EIGRP Output](IPv6%20EIGRP.jpg)



\---

\## 👥 Author: John Ivan P. Ello | CCNA Certified

