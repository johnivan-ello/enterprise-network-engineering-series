\# Day 7 - Network Address Translation (NAT \& PAT Overload)



\## 📌 Project Overview

This project focuses on securing the corporate enterprise edge boundary where the private RFC 1918 internal addressing structures transition to the public internet space. The lab implements Network Address Translation (NAT) and Port Address Translation (PAT) to conserve routable public IP space while masking internal logical network layouts from external discovery.



\## 🗺️ Network Topology

The lab topology simulates an enterprise edge gateway router connected to a private localized internal LAN on one side, and an upstream service provider (ISP) network on the other.



!\[NAT Topology](NAT%20Topology.jpg)



\---



\## 🛠️ Technical Stack \& Implementation Details



\### 1. Port Address Translation (PAT / NAT Overload)

\* \*\*Dynamic Translation Engine:\*\* Configured dynamic NAT with overload mapping parameters (`ip nat inside source list 1 interface gig0/0 overload`). This allows hundreds of local devices sharing a single private prefix to multiplex across a single public interface securely.

\* \*\*Layer 4 Tracking:\*\* Monitored how the edge router assigns unique source TCP/UDP port identifiers to track independent conversational streams flowing through the translated interface.



\### 2. Domain Perimeter Boundaries

\* \*\*Interface Designation:\*\* Carefully configured strict traffic processing perimeters across hardware boundary segments by manually injecting `ip nat inside` rules on local LAN-facing links and `ip nat outside` parameters on WAN-facing public links.



\---



\## 📊 Verification \& Translation Table Diagnostics



The following translation tables and end-to-end connectivity proofs have been captured and verified within the lab environment:



\### 🔹 Active NAT Translation Table

Analyzing the state machine matrix of the edge router to confirm how private inside local IP addresses and source ports map natively to public inside global addresses.

!\[IP Nat Translation Output](IP%20Nat%20Translation.jpg)



\### 🔹 Public Reachability Verification (PC Ping to Public IP)

Executing data plane ICMP tracking from an inside host node to a simulated public server interface, confirming successful state translation and flawless round-trip return routing.

!\[PC Ping Verification](PC%20Ping%20to%20Public%20IP.jpg)



\---

\## 👥 Author: John Ivan P. Ello | CCNA Certified

