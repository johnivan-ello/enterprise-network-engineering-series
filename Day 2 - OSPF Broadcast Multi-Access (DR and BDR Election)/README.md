\# Day 2 - OSPF Broadcast Multi-Access Topology (DR/BDR)



\## 📌 Project Overview

This lab focuses on optimizing Link-State Advertisement (LSA) flooding and neighbor adjacency overhead within multi-access broadcast segments (such as common Ethernet transit networks). By implementing Designated Router (DR) and Backup Designated Router (BDR) selection rules, this project scales neighbor relationships from an inefficient $O(n^2)$ down to a highly streamlined $O(n)$ architecture.



\## 🗺️ Network Topology

The lab environment features a multi-node broadcast segment where all routers are tied to a single multi-access segment. 



!\[OSPF Multi-Access Topology](Topology.jpg)



\---



\## 🛠️ Technical Stack \& Implementation Details



\### 1. DR/BDR Election Engineering

\* \*\*Priority Manipulation:\*\* Manipulated interface OSPF priority values (`ip ospf priority`) to deterministically control elections, forcing the primary core node to assume the DR role and a secondary node to assume the BDR role.

\* \*\*Router ID Anchoring:\*\* Hardcoded unique IPv4 Loopbacks as RIDs to guarantee election stability across process restarts.



\### 2. Adjacency State Machines \& LSA Optimization

\* \*\*DROther Isolation:\*\* Verified traffic behaviors where DROther nodes form full adjacencies only with the DR and BDR (using multicast destination `224.0.0.6` to send Link-State Updates).

\* \*\*Two-Way Status:\*\* Engineered the network so that non-DR/non-BDR routers maintain a non-flooding, loop-free `2WAY/DROTHER` neighbor state with each other, saving significant router CPU and link bandwidth.



\---



\## 📊 Verification \& Control Plane Captures



The following output states have been captured and verified within the lab environment to confirm the deterministic election baseline:



\### 🔹 Designated Router (DR) State

The primary root forwarding node running the segment topology map.

!\[DR Output](DR.jpg)



\### 🔹 Backup Designated Router (BDR) State

The standby forwarding node ready to immediately absorb segment management in the event of a DR failure.

!\[BDR Output](BDR.jpg)



\### 🔹 DROther Adjacency Validation

The access-layer nodes maintaining an intentional `2WAY` state with other non-designated routing nodes.

!\[DROthers Output](Drothers.jpg)



\---

\## 👥 Author: John Ivan P. Ello | CCNA Certified

