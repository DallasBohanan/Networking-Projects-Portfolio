
Simulated Enterprise WAN Network Mock/Outline 





[ISP Router]
     |  (eBGP)
  [R1-Edge] --- [R2-Edge]   ← Dual-router redundancy at HQ
     |                |
  [DS1-Core] --- [DS2-Core]  ← L3 switches, EtherChannel uplink
   /    \         /    \
[AS1]  [AS2]  [AS3]  [AS4]  ← Access switches (per dept/floor)

[HQ Server Farm] on DS1/DS2 SVI
[DMZ Segment] off R1-Edge (simulated firewall via ACLs)

         WAN (GRE Tunnels)
         /              \
   [Branch-A-R]     [Branch-B-R]
       |                  |
  [Branch-A-SW]      [Branch-B-SW]

[DC-Core-SW] ← Data center, connected to HQ via OSPF Area 10
  |       |
[DC-AS1] [DC-AS2]




Network Segmentation 

IP Addressing Scheme

Segment
Subnet
Notes
HQ – Management
10.1.0.0/24
VLAN 10

HQ – IT
10.1.1.0/24
VLAN 20

HQ – Finance
10.1.2.0/24
VLAN 30

HQ – HR
10.1.3.0/24
VLAN 40

HQ – Sales
10.1.4.0/24
VLAN 50

HQ – VoIP
10.1.5.0/24
VLAN 60

HQ – Servers
10.1.10.0/24
VLAN 100

DMZ
10.1.20.0/24
VLAN 200

Branch A – Staff
10.2.1.0/24
VLAN 20
Branch A – Guest
10.2.2.0/24
VLAN 30

Branch B – Staff
10.3.1.0/24
VLAN 20
Branch B – Guest
10.3.2.0/24
VLAN 30

Data Center – App
10.10.1.0/24
VLAN 110
Data Center – DB
10.10.2.0/24
VLAN 120

WAN point-to-points
10.99.x.x/30
GRE tunnel endpoints
Public/ISP-facing
203.0.113.0/24
Documentation range


