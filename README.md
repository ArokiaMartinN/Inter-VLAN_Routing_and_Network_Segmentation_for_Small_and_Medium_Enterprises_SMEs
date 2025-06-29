# Inter-VLAN Routing and Network Segmentation for Small and Medium Enterprises (SMEs)

> **Duration:** June 2025  
> **Company:** Symbiotic Infotech Pvt. Ltd.   

### Project Summary

• Designed and implemented a SME level multi-VLAN network and Inter-VLAN Routing via Router-on-a-Stick and separate DHCP configuration, IP Address Pools for Each VLAN and Trunk port setup, Integration of Access Points for wireless clients using Cisco Packet Tracer.  
• Verified Parts of the Network through hands-on testing with Enterprise-Grade Cisco and Fortinet Hardware.

### Tools & Networking Devices

• Cisco Packet Tracer  
• Cisco Catalyst 2960 Series SI - Switch (L2 Managed)  
• Fortinet Fortigate 100D - Router (Firewall)  
• Console Cable & Cat 6 RJ45 Ethernet Cables

### Network Architecture

### Core Components
- **Router:** 
  - Handles inter-VLAN routing
  - Configured with **Subinterfaces**:
    - `G0/0.10` → `192.168.1.0/24` (VLAN 10) [Dept 1]
    - `G0/0.20` → `192.168.2.0/24` (VLAN 20) [Dept 2]
   - **Reserved IPs** (For Future need of Static IPs)
     - VLAN10_POOL: `192.168.1.2` – `192.168.1.10`
     - VLAN20_POOL: `192.168.2.2` – `192.168.2.10`
  - Acts as centralized **DHCP Server**
    - VLAN10_POOL: `192.168.1.11` – `192.168.1.254`
    - VLAN20_POOL: `192.168.2.11` – `192.168.2.254`

- **Main Switch (Core Layer):** 
  - Ports Fa0/1–12 → VLAN 10 [Dept 1]
  - Ports Fa0/13–23 → VLAN 20 [Dept 2]
  - Port Fa0/24 → **Trunk** to Router
  - Connects to all departmental (access-layer) switches

## Department-Level Structure

### Department 1 – VLAN 10 [Dept 1] (`192.168.1.0/24`)
- Default Gateway - `192.168.1.1`
- **Sub 1 [Switch 1]**
  - Devices:
    - PC 1.1 (DG 1.1)
    - PC 1.2, PC 1.3
    - Printer 1.1
    - Wireless Access Point (Wi-Fi 1.1)
      - Connected Laptop 1.1
- **Sub 1 [Switch 2]**
  - Devices:
    - PC 1.4, PC 1.5
    - Server 1.1

### Department 2 – VLAN 20 [dept 2] (`192.168.2.0/24`)
- Default Gateway - `192.168.2.1`
- **Sub 2 [Switch 1]**
  - Devices:
    - PC 2.1, PC 2.2, PC 2.3
    - Server 2.1
    - Wireless Access Point (Wi-Fi 2.1)
      - Connected Laptop 2.1
- **Sub 2 [Switch 2]**
  - Devices:
    - PC 2.4, PC 2.5
    - Printer 2.1

## Key Features Implemented

### VLAN-Based Segmentation
- Created **VLAN 10** and **VLAN 20** to separate departments.
- Logical segmentation reduces broadcast domains and improves security.

### Inter-VLAN Routing via Router-on-a-Stick
- Enabled communication between VLANs using **subinterfaces** on router with `dot1Q` encapsulation.

### Centralized DHCP
- The router allocates IP addresses dynamically using **DHCP pools**, with proper exclusion of router and reserved IPs.

### Trunk Port Setup
- Trunk configured on **Fa0/24** of the Main Switch to carry tagged traffic to router.

### Wireless Integration
- Wireless routers/access points connected per department.
- Wireless devices receive VLAN-specific IPs via DHCP.

### Hardware Validation
- Confirmed VLAN trunking and DHCP functionality using:
  - Cisco 2960 Series SI Switch
  - Fortinet FortiGate 100D (as alternate L3 test device)


