# 🌐 The Enterprise Network Engineering Series

Welcome to the central repository for **The Enterprise Network Engineering Series**. This portfolio documents a structured, 10-day hands-on engineering progression designed to simulate, architect, and optimize complex multi-vendor enterprise campus and WAN infrastructures using **GNS3** and **Cisco Packet Tracer**.

Each day tackles a distinct routing, switching, scaling, or edge security requirement—moving from fundamental interior gateway protocol baseline deployments up to multi-AS border gateway routing and high-availability dual-stack path redundancy.

---

## 🗺️ 10-Day Lab Roadmap & Directory Index

Click on any day below to view the dedicated implementation steps, configuration strategies, protocol constraints, and network topology diagrams:

| Day | Lab Focus | Core Technologies Deployed | Topology Preview |
| :---: | :--- | :--- | :---: |
| **01** | [IPv4 Routing Protocols](./Day%201%20-%20IPv4%20Routing%20Protocols/) | Static, Default, RIPv2, OSPFv2, EIGRP Baseline | <img src="./Day 1 - IPv4 Routing Protocols/Topology.jpg" width="220"> |
| **02** | [OSPF Broadcast Multi-Access](./Day%202%20-%20OSPF%20Broadcast%20Multi-Access%20(DR%20BDR)/) | DR/BDR Elections, Priority Manipulation, LSAs | <img src="./Day 2 - OSPF Broadcast Multi-Access (DR BDR)/Topology.jpg" width="220"> |
| **03** | [Inter-VLAN Routing](./Day%203%20-%20Inter-VLAN%20Routing%20(Router-on-a-Stick)/) | Router-on-a-Stick, IEEE 802.1Q Subinterfaces | <img src="./Day 3 - Inter-VLAN Routing (Router-on-a-Stick)/ROAS Topology.jpg" width="220"> |
| **04** | [Multilayer Switching](./Day%204%20-%20Multilayer%20Switching%20(SVI,%20L3%20Switch)/) | SVI Interfaces, Layer 3 EtherChannel, Routed Ports | <img src="./Day 4 - Multilayer Switching (SVI, L3 Switch Routing)/Multilayer Switching Topology.jpg" width="220"> |
| **05** | [EtherChannel Aggregation](./Day%205%20-%20EtherChannel%20(LACP,%20PAgP,%20Static)/) | LACP, PAgP, Static Port-Channel Bundling | <img src="./Day 5 - EtherChannel (LACP, PAgP, Static)/EtherChannel Topology.jpg" width="220"> |
| **06** | [Centralized DHCP Services](./Day%206%20-%20DHCP%20(IPv4%20+%20Relay%20Concept)/) | IPv4 Addressing Pools, Layer 3 DHCP Relay Agents | <img src="./Day 6 - DHCP (IPv4 + Relay Concept)/DHCP Topology.jpg" width="220"> |
| **07** | [Network Address Translation](./Day%207%20-%20Network%20Address%20Translation%20(NAT)/) | Static, Dynamic, NAT Overload (PAT), IP Inside/Outside | <img src="./Day 7 - Network Address Translation (NAT)/NAT Topology.jpg" width="220"> |
| **08** | [IPv6 Routing Protocols](./Day%208%20-%20IPv6%20Routing%20Protocols/) | OSPFv3, EIGRP for IPv6, Link-Local Adjacencies | <img src="./Day 8 - IPv6 Routing Protocols/IPv6 Topology.jpg" width="220"> |
| **09** | [Floating Static Routes](./Day%209%20-%20Floating%20Static%20Routes%20(IPv4%20+%20IPv6)/) | Dual-Stack (IPv4/IPv6) Path Redundancy, AD Tuning | <img src="./Day 9 - Floating Static Routes (IPv4 + IPv6)/Floating Static Route Topology.jpg" width="220"> |
| **10** | [Border Gateway Protocol](./Day%2010%20-%20Border%20Gateway%20Protocol%20(eBGP%20%26%20iBGP)/) | Multi-AS eBGP, iBGP Split-Horizon, `next-hop-self` | <img src="./Day 10 - Border Gateway Protocol (eBGP & iBGP)/BGP Topology.jpg" width="220"> |

---

## 🛠️ Engineering Tooling & Emulation Specs
- **Network Emulation fabrics:** GNS3 (Cisco IOSv 15.x Virtual Images), Cisco Packet Tracer v8.x
- **Analysis & Testing:** Wireshark Packet Capture & Frame Inspection, ICMP Diagnostics
- **Host Emulation:** Virtual PC Simulator (VPCS nodes)

---
## 👥 Author Profile

* **Developer:** John Ivan P. Ello
* **Professional Credentials:** Summa Cum Laude Graduate, BS in Information Systems | CCNA Certified
* **Email:** [1ello.johnivan03@gmail.com](mailto:1ello.johnivan03@gmail.com)
* **LinkedIn:** [linkedin.com/in/johnivanello](https://www.linkedin.com/in/johnivanello/)
* **GitHub Portfolio:** [github.com/JohnIvan-Ello](https://github.com/JohnIvan-Ello)
