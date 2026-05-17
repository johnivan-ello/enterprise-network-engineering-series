\# Day 1 - IPv4 Routing Protocols Baseline



\## 📌 Project Overview

This project establishes the baseline routing fabric for the enterprise infrastructure series. It involves configuring, analyzing, and comparing fundamental IPv4 routing methods across isolated GNS3 environments. By deploying Static/Default routing alongside three interior gateway protocols (RIPv2, OSPFv2, and EIGRP), this lab evaluates convergence speed, administrative distance behaviors, and routing table metrics.



\## 🛠️ Technical Stack \& Implementation Details

\- \*\*Static \& Default Routing:\*\* Configured explicitly scoped static paths alongside quad-zero default routes (`ip route 0.0.0.0 0.0.0.0`) to engineer clean exit points toward provider perimeters.

\- \*\*RIPv2 Routing:\*\* Deployed classless distance-vector RIPv2, disabling auto-summarization (`no auto-summary`) to preserve VLSM prefix boundaries.

\- \*\*OSPFv2 Single-Area:\*\* Instantiated OSPF link-state tracking inside a foundational Area 0 backbone, forcing explicit Loopback 0 interface bindings for deterministic Router ID (RID) stability.

\- \*\*EIGRP Autonomous System:\*\* Configured EIGRP advanced distance-vector metrics, utilizing the Diffusing Update Algorithm (DUAL) for fast loop-free backup path tracking.

\- \*\*Control Plane Analysis:\*\* Evaluated how Administrative Distance (AD) determines path placement when multiple protocols compete for the same prefix (Static: 1, EIGRP: 90, OSPF: 110, RIP: 120) via `show ip route`.



\---

\## 👥 Author: John Ivan P. Ello | CCNA Certified

