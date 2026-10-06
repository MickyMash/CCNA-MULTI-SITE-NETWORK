# Enterprise Network Infrastructure - The Macharia Hospital


A high-availability, multi-site enterprise network infrastructure designed and simulated in Cisco Packet Tracer for a healthcare organization (**The Macharia Hospital**). This project demonstrates multi-tier switching, core-distribution redundancy, dynamic WAN routing, dual-ISP failover, and dedicated server-farm segmentation.

---

## 📌 Project Overview

Modern healthcare operations depend on continuous connectivity across hospital branches, departments, and critical server infrastructure. This project models a full-scale corporate network connecting a **Headquarters (HQ)** and a **Branch Site** through a redundant WAN core, ensuring zero single points of failure for clinical, administrative, and data services.

---

## 🛠️ Key Architectural Features

### 1. High Availability & Gateway Redundancy
* **HSRP (Hot Standby Router Protocol):** Configured across dual Cisco 3650 Multilayer Switches at both HQ and Branch sites to provide instant default gateway failover for departmental VLANs.

### 2. Link Aggregation & Performance
* **LACP (Link Aggregation Control Protocol):** Configured EtherChannels between core and distribution switches to increase backbone bandwidth and provide link redundancy.

### 3. Redundant Dual-ISP WAN Core
* Connected **HQ-Router**, **BRANCH-Router**, **ISP1**, and **ISP2** using a full mesh/partial mesh WAN architecture.
* Addressed via dedicated point-to-point `/30` subnets (`10.10.10.0/30` through `60.60.60.0/30`) to ensure reliable multi-path data transmission and ISP redundancy.

### 4. Departmental Inter-VLAN Routing & Segmentation
* **HQ Subnetting (`192.168.x.x/24`):** Segmented into MLOCS, MER, MRM, IT, CS, GWA, and Management VLANs.
* **Branch Subnetting (`172.31.x.x/24`):** Segmented into NSO, HL, Marketing, Finance, HR, and GWA VLANs.
* Dedicated access controls for network printers and end-user PCs within each department.

### 5. Centralized Server Site Infrastructure
* Connected via routed subnet (`172.16.50.0/24`) off the HQ Router.
* Hosts enterprise-wide network services:
  * **DNS Server** (Domain Name Resolution)
  * **DHCP Server** (Dynamic IP Assignment)
  * **WEB Server** (Internal Portals / Intranet)
  * **EMAIL Server** (Hospital Communication)

---

## 📐 Network Addressing & VLAN Summary

### Subnet Scheme Overview

| Region / Link | Subnet Block | Subnet Mask | Description |
| :--- | :--- | :--- | :--- |
| **WAN Core Links** | `10.10.10.0/30` – `60.60.60.0/30` | `255.255.255.252` | Inter-router WAN links (HQ, Branch, ISP1, ISP2) |
| **HQ LAN VLANs** | `192.168.10.0/24` – `192.168.99.0/24` | `255.255.255.0` | HQ Departmental Endpoints & Printers |
| **Branch LAN VLANs**| `172.31.10.0/24` – `172.31.99.0/24` | `255.255.255.0` | Branch Departmental Endpoints & Printers |
| **Server Farm** | `172.16.50.0/24` | `255.255.255.0` | Centralized DNS, DHCP, Web, Email Servers |

---

## 📁 Repository Structure

```text
.
├── README.md                          # Project Documentation
├── pkt/
│   └── Macharia_Hospital_Network.pkt  # Cisco Packet Tracer Topology File
├── docs/
│   ├── Topology_Diagram.png           # Full Topology Screenshot
│   └── IP_Addressing_Table.xlsx       # Complete IP & Interface Addressing Master Sheet
└── configs/
    ├── HQ-Router.txt                  # Running config for HQ-Router
    ├── BRANCH-Router.txt              # Running config for BRANCH-Router
    ├── HQ-Multilayer-Switch1.txt      # Running config for HQ Core Switch 1
    └── BRANCH-Multilayer-Switch1.txt  # Running config for Branch Core Switch 1
