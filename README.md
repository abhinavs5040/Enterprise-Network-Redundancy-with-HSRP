# Enterprise-Network-Redundancy-with-HSRP
Enterprise network simulation with VLAN segmentation, inter-VLAN routing, and HSRP for gateway redundancy. Designed in Cisco Packet Tracer with failover testing to ensure high availability and minimal downtime.
🚀 Project Summary
Designed and implemented an enterprise-like network topology with:

VLAN segmentation (HR, Finance, IT)
Inter-VLAN routing using Layer-3 switches (SVIs)
HSRP for redundant default gateways (active/standby)
Centralized DHCP on L3 core with DHCP relay (ip helper-address) at branches
OSPF (Area 0) for dynamic routing across HQ and branch WAN links
ACLs to enforce role-based traffic policies (example: block HR → IT)
Config exports & failover testing for demonstration
Configs, Packet Tracer file, topology image and verification steps are included.

🗺 Topology (summary)
HQ
L3SW-1 (Primary L3 switch) — HSRP Active, DHCP server, OSPF
L3SW-2 (Standby L3 switch) — HSRP Standby, OSPF
SW-ACC (Access) — trunks to L3 core, ports for PCs
R-HQ (Router) — WAN head/router, serial to branches
Branches
R-BR1, SW-BR1, PCs (branch 1)
R-BR2, SW-BR2, PCs (branch 2)
(See images/topology.png in this repo for the workspace screenshot.)

⚙️ Addressing & VLANs (used in this lab)
VLAN 10 (HR) → 10.0.10.0/24 (HSRP VIP: 10.0.10.1)
VLAN 20 (Finance) → 10.0.20.0/24 (HSRP VIP: 10.0.20.1)
VLAN 30 (IT) → 10.0.30.0/24 (HSRP VIP: 10.0.30.1)
Branch 1 LAN → 10.1.10.0/24 (default-gw 10.1.10.1)
Branch 2 LAN → 10.2.10.0/24 (default-gw 10.2.10.1)
Core ↔ R-HQ links + serial WANs use /30 networks as shown in configs.
