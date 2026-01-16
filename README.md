# Small-network-enviroment-Packet-tracer
This project simulates a small enterprise network environment using Cisco Packet Tracer. The network is designed to demonstrate VLAN segmentation, inter-VLAN routing, DHCP services, and dynamic routing using OSPF across both LAN and WAN segments.

The goal of this project is to practice designing, configuring, and verifying connectivity in a multi-VLAN, multi-router environment.

# Network Design Summary
The network consists of:
- Multiple switches supporting VLANs and trunking
- Three routers connected via serial links to simulate a WAN
- Multiple LAN segments with dynamic IP addressing
- OSPF implemented for routing between all network segments
- Loopback interfaces used for router identification and management

# VLAN and LAN Configuration (Initial LAN)
Two VLANs were initially created:
VLAN 2
VLAN 4
These VLANs were subnetted using VLSM to support a specific number of hosts per VLAN.
Both VLANs are connected to Switch 1, which is trunked to Switch 2. Trunking allows VLAN traffic to be forwarded to Router 1, where inter-VLAN routing is performed.

# Inter-VLAN Routing and DHCP
Router 1 is configured to:
- Perform inter-VLAN routing
- Provide DHCP services to each VLAN
Each VLAN receives dynamic IP addressing from the router, allowing hosts in different VLANs to communicate while remaining logically separated.
This portion of the network represents a local area network (LAN).

# WAN Simulation and OSPF Configuration
To simulate a wide area network (WAN):
- Router 1 is connected to Router 2 via a serial link
- Router 2 is connected to Router 3 via another serial link
Each serial connection is assigned its own IP address.
OSPF is configured on all routers to allow dynamic routing between LAN and WAN segments.

# Loopback Interfaces and Router IDs
Each router includes a loopback interface used as its OSPF Router ID:
- Router 1: 1.1.1.1/32
- Router 2: 2.2.2.2/32
- Router 3: 3.3.3.3/32
Loopback interfaces provide stable router identification and simulate remote management access.

# External Network Simulation
Router 3 connects directly to a server configured with the IP address 8.8.8.8, simulating an external resource such as Google DNS.
This allows verification of end-to-end connectivity across the entire network.

# Network Expansion (Additional LAN)
An additional LAN was created by connecting Switch 2 to Switch 3.
Two additional VLANs were configured:
- VLAN 10 – 172.16.10.0
- VLAN 20 – 172.16.20.0
These VLANs use standard subnetting (not VLSM).
Router 1 was updated to:
- Support inter-VLAN routing for the new VLANs
- Provide DHCP services
- Advertise the new networks through OSPF

# Verification and Connectivity
Connectivity was verified by:
- Confirming DHCP address assignment
- Testing inter-VLAN communication
- Verifying OSPF neighbor relationships
- Pinging the simulated external server (8.8.8.8)
All VLANs and network segments successfully communicate with each other.

# What This Project Demonstrates
- VLAN creation and trunking
- VLSM-based subnetting
- Inter-VLAN routing
- DHCP configuration
- OSPF dynamic routing
- WAN simulation using serial links
- Network scalability and expansion
- Troubleshooting and verification skills
