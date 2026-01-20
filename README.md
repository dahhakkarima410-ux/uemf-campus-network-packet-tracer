# UEMF Campus Network Simulation – Cisco Packet Tracer

## Project Overview
This project is a university-scale campus network simulation designed using Cisco Packet Tracer.  
It models the logical network infrastructure of a modern academic campus inspired by UEMF, focusing on scalability, security, and traffic isolation rather than physical building architecture.

The goal is to design a realistic campus network that reflects industry practices used in large educational institutions.

---

## Network Architecture

The network follows a hierarchical Cisco campus design:

### Access Layer
- End-user devices (Students, Staff)
- Wireless Access Points
- Port Security enforcement

### Distribution Layer
- One distribution switch per building
- VLAN aggregation
- Trunk links towards the core

### Core Layer
- Two multilayer switches forming a redundant backbone
- Centralized inter-VLAN routing
- High availability and scalability

### Edge / WAN
- Router providing external connectivity
- Dynamic routing using OSPF

---

## Campus Structure

The simulated campus includes:

- Multiple academic buildings  
  - Buildings with 4 and 5 floors  
  - Each floor contains:
    - 1 Staff (Administration/Professors) PC
    - 1 Student PC

- Central academic building  
  - 7 floors  
  - Staff and Student devices on each floor

- Sports Complex  
  - 3 floors  
  - Mixed Staff and Student access on the first floor  
  - Student-only access on upper floors

- Restaurant / Visitor Area  
  - Guest-only access  
  - Isolated network segment

This structure enables realistic testing of traffic isolation, routing behavior, and access control policies.

---

## VLAN Design and Segmentation

The network is logically segmented using VLANs based on user roles:

| VLAN ID | Name     | Description |
|-------|----------|-------------|
| 10    | STUDENTS | Students, classrooms, labs, libraries |
| 20    | STAFF    | Professors and administration |
| 30    | GUEST    | Visitors and restaurant users |

This segmentation ensures:
- Separation of sensitive administrative data
- Controlled access between user groups
- Easier network management and scalability

---

## IP Addressing and Routing

### Addressing Strategy
- VLSM (Variable Length Subnet Masking) is used for efficient IP allocation
- Larger address spaces are allocated for Students, smaller subnets for Guests

### Routing
- Inter-VLAN routing is performed on Layer 3 Core Switches
- OSPF is used as the dynamic routing protocol between core devices and the edge router

---

## Network Services

- DHCP  
  - Automatic IP address assignment per VLAN

- Wireless Networking  
  - Separate SSIDs mapped to VLANs:
    - Students
    - Staff
    - Guests

- Extensibility  
  - The design allows easy integration of DNS, IoT, or monitoring services

---

## Security Design

Security is integrated into the architecture from the beginning:

- Access Control Lists (ACLs)  
  - Restrict communication between VLANs  
  - Guest network fully isolated from internal resources

- Port Security  
  - Enabled on access switches  
  - Prevents unauthorized devices from connecting

- VLAN Isolation  
  - Ensures sensitive data remains protected

---

## Testing and Validation

The network was validated using:
- ICMP (Ping) tests between different VLANs
- Cisco Packet Tracer Simulation Mode (PDU Simple)
- Verification of routing tables and VLAN propagation

All tests confirm correct connectivity, routing behavior, and security enforcement.

---

## Tools and Technologies

- Cisco Packet Tracer
- VLANs and Trunking
- Layer 3 Switching
- OSPF Routing Protocol
- VLSM Subnetting
- ACLs and Port Security
- DHCP Services

---

## Skills Demonstrated

- Campus Network Architecture
- Logical Network Design
- Subnetting and IP Planning
- Routing and Switching
- Network Security Implementation
- Troubleshooting and Validation

---

## Files

- `EcoCampus_UEMF.pkt` – Complete Packet Tracer simulation file

---

## Notes

This project emphasizes real-world network design principles rather than simplified lab scenarios.  
It is intended as a learning and portfolio project demonstrating applied networking knowledge.
