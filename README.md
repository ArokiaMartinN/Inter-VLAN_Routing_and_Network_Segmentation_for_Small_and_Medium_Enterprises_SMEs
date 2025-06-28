# Inter-VLAN Routing and Network Segmentation for Small and Medium Enterprises (SMEs)

> **Duration:** June 2025  
> **Company:** Symbiotic Infotech Pvt. Ltd.  
> **Tools Used:** Cisco Packet Tracer, Cisco 2960 Series SI Switch, Fortinet FortiGate 100D, Console Cable, Cat 6 RJ45 Ethernet Cables

## Project Summary

This project focuses on designing and implementing a scalable, secure, and efficient SME-level network architecture using VLAN segmentation and Inter-VLAN Routing. The network is built to support both wired and wireless clients with proper DHCP configuration and trunk port setups. The entire setup was first simulated using **Cisco Packet Tracer** and then partially tested on **real enterprise-grade hardware** for validation.

## Key Features

- **Multi-VLAN Architecture**  
  Created VLAN 10 and VLAN 20, assigned ports Fa0/1–12 and Fa0/13–23 respectively for wired and wireless clients.

- **Router-on-a-Stick Inter-VLAN Routing**  
  Configured subinterfaces on the router (`G0/0.10`, `G0/0.20`) to enable communication between VLANs via trunk port.

- **Dynamic IP Assignment**  
  Implemented separate DHCP pools for each VLAN to allow automatic IP configuration per subnet:
  - VLAN 10 → `192.168.1.0/24`
  - VLAN 20 → `192.168.2.0/24`

- **Trunk Port Setup**  
  Set up Fa0/24 on the Main Switch as a trunk to handle tagged VLAN traffic.

- **Wireless AP Integration**  
  Connected access points to both VLANs, allowing wireless clients to receive proper VLAN-tagged IPs.

- **Hardware Testing**  
  Verified portions of the simulated network on real Cisco and Fortinet devices:
  - Cisco 2960 Series SI - L2 Managed Switch
  - Fortinet FortiGate 100D - Router (Firewall)
