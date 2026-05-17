\# Day 6 - Centralized DHCP Services \& Layer 3 Relay Concept



\## 📌 Project Overview

This project addresses the operational challenge of centralizing IP address management within the corporate core. By decoupling address assignment servers from access-layer host segments, this design implements automated, dynamic IPv4 allocation across multiple remote subnets using \*\*Layer 3 DHCP Relay Agents (IP Helper)\*\* without requiring an independent DHCP server in every local broadcast domain.



\## 🗺️ Network Topology

The lab infrastructure partitions corporate endpoints into remote subnets running back to a core routing node acting as the centralized pool repository.



!\[DHCP Topology](DHCP%20Topology.jpg)



\---



\## 🛠️ Technical Stack \& Implementation Details



\### 1. Centralized DHCP Scopes \& Parameter Tuning

\* \*\*Dynamic Scopes:\*\* Programmed distinct, isolated dynamic address scopes (`ip dhcp pool`) on the central router, explicitly binding critical lease options like the default gateway (`default-router`) and server hierarchies.

\* \*\*Subnet Safeguarding:\*\* Implemented precise IP exclusion parameters (`ip dhcp excluded-address`) to permanently protect high-value static infrastructure assets—such as switch SVIs and perimeter links—from dynamic deployment overlaps.



\### 2. Layer 3 DHCP Relay (IP-Helper Architecture)

\* \*\*Broadcast Boundary Mitigation:\*\* Because client DHCP Discover messages are broadcast packets (limited to their local Layer 2 broadcast domain), remote routers will natively drop them.

\* \*\*Unicast Relay Conversion:\*\* Applied the `ip helper-address \[Central-DHCP-IP]` parameter directly onto all localized interface subinterfaces/gateways. This instructs the intermediate interface to capture client broadcasts, encapsulate them as targeted unicast streams, and relay them cleanly across routing boundaries to the central server.



\---



\## 📊 Verification \& Allocation Diagnostics



The following system captures and configuration segments have been verified within the environment to confirm successful dynamic addressing:



\### 🔹 DHCP Pool \& Scope Allocation

Verifying the configuration of centralized network pools and address tracking parameters.

!\[DHCP Pool Configuration](DHCP%20Pool.jpg)



\### 🔹 Layer 3 Relay Configuration (IP-Helper)

Validating the active insertion of the unicast helper address parameters under the local gateway interfaces.

!\[IP-Helper Interface Binding](IP-Helper.jpg)



\### 🔹 Endpoint Address Binding Proof

Reviewing the client terminal output to confirm successful lease negotiations and correct default gateway configuration.

!\[IP Config Validation](IP%20Config.jpg)



\---

\## 👥 Author: John Ivan P. Ello | CCNA Certified

