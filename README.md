# 🎓 HU University Network

A Cisco Packet Tracer-based university network design and simulation project developed as part of a Computer Science networking project at **Hawassa University, Ethiopia**.

## 📌 Project Overview

The **HU University Network** is designed to support approximately **180 hosts** distributed across two university buildings.

The network follows a **three-layer hierarchical architecture**:

- Core Layer
- Distribution Layer
- Access Layer

The design uses VLAN segmentation, IPv4 addressing, subnetting, routing, redundancy, security mechanisms, network services, and wireless connectivity.

## 🎯 Project Objectives

- Design a scalable university network.
- Connect two university buildings.
- Support approximately 180 hosts.
- Divide the network into multiple VLANs.
- Apply IPv4 addressing and subnetting.
- Implement inter-VLAN communication.
- Provide dynamic routing.
- Improve network availability through redundancy.
- Apply basic network security mechanisms.
- Provide wired and wireless connectivity.
- Support essential network services.
- Develop practical network design, testing, and troubleshooting skills.

# 🏢 University Buildings

## Building A

- 2 floors
- Approximately 80 hosts
- 4 VLANs
- Wired and wireless connectivity

## Building B

- 3 floors
- Approximately 100 hosts
- 6 VLANs
- Wired and wireless connectivity

## Overall Network

| Component | Quantity |
|---|---:|
| Buildings | 2 |
| Floors | 5 |
| Approximate Hosts | 180 |
| VLANs | 10 |
| Core Switches | 2 |
| Distribution Switches | 2 |
| Access Switches | 10 |
| Routers | 1 |
| Firewalls | 1 |
| Servers | Included |
| Wireless Access Points | Included |

# 🌐 Network Architecture

The project follows a **three-tier hierarchical network architecture**.

``
                         INTERNET / CLOUD
                                |
                              Router
                                |
                             Firewall
                                |
                 +--------------+--------------+
                 |                             |
             CORE-SW1                       CORE-SW2
                 |                             |
          +------+-------+              +------+-------+
          |              |              |              |
       DISW1           DISW2        Distribution    Distribution
          |              |              |              |
      Access          Access        Access          Access
      Switches        Switches      Switches        Switches
          |              |              |              |
       PCs/APs        PCs/APs      PCs/APs        PCs/APs


## Core Layer

The Core Layer forms the backbone of the university network and provides high-speed connectivity, Layer 3 communication, and redundancy.

## Distribution Layer

The Distribution Layer aggregates access switches and provides network segmentation, routing, policy control, and redundancy.

## Access Layer

The Access Layer connects end-user devices such as PCs and Wireless Access Points. The project uses 10 Access Switches.

# 🔀 VLAN Design

The network is divided into **10 VLANs**.

| VLAN | Network | Default Gateway | Prefix | Usable Hosts |
|---:|---|---|---|---:|
| 10 | 192.168.16.0 | 192.168.16.1 | /27 | 30 |
| 20 | 192.168.16.32 | 192.168.16.33 | /27 | 30 |
| 30 | 192.168.16.64 | 192.168.16.65 | /27 | 30 |
| 40 | 192.168.16.96 | 192.168.16.97 | /27 | 30 |
| 50 | 192.168.16.128 | 192.168.16.129 | /27 | 30 |
| 60 | 192.168.16.160 | 192.168.16.161 | /27 | 30 |
| 70 | 192.168.16.192 | 192.168.16.193 | /27 | 30 |
| 80 | 192.168.16.224 | 192.168.16.225 | /27 | 30 |
| 90 | 192.168.17.0 | 192.168.17.1 | /27 | 30 |
| 100 | 192.168.17.32 | 192.168.17.33 | /27 | 30 |

# 🧮 IP Addressing and Subnetting

The internal IPv4 address space is:

```text
192.168.16.0/23
```

Subnet mask:

```text
255.255.254.0
```

| Property | Value |
|---|---:|
| Network Prefix | /23 |
| Total Addresses | 512 |
| Usable Addresses | 510 |
| Address Range | 192.168.16.0 – 192.168.17.255 |

Each VLAN uses a `/27` subnet.

| Property | Value |
|---|---:|
| Subnet Mask | 255.255.255.224 |
| Total Addresses | 32 |
| Usable Host Addresses | 30 |
| Network Bits | 27 |
| Host Bits | 5 |

# 📐 VLSM

The project applies subnetting principles to divide the larger `/23` address space into smaller networks for the VLANs.

This provides:

- Logical network separation
- Easier network management
- Reduced broadcast domains
- Better address organization
- Improved scalability
- Easier troubleshooting

# 🔄 Routing

The project incorporates:

- Inter-VLAN Routing
- Dynamic Routing
- OSPF
- HSRP
- Default/WAN routing where required

## OSPF

**OSPF (Open Shortest Path First)** provides dynamic route discovery, best-path selection, adaptation to topology changes, and scalability.

## HSRP

**HSRP (Hot Standby Router Protocol)** provides gateway redundancy and improves network availability by providing a backup gateway.

# 🔗 Switching

The network uses:

- Layer 2 switching
- Layer 3 switching
- VLANs
- Access ports
- Trunk links
- 802.1Q VLAN tagging
- Inter-switch connectivity
- Redundant switching paths

## Access Ports

Access ports connect end devices to their appropriate VLAN.

## Trunk Links

Trunk links carry multiple VLANs between compatible network devices and maintain VLAN segmentation across the topology.

# 📡 Wireless Network

The university network includes **Wireless Access Points** to provide wireless connectivity.

The design considers wireless user connectivity, Access Point placement, network integration, redundant connectivity where applicable, and VLAN-based traffic separation.

# 🔐 Network Security

The project incorporates several security concepts.

## VLAN Segmentation

VLANs logically separate network traffic and help limit unnecessary communication between network segments.

## Firewall

The firewall provides a security boundary between external networks and the internal university network.

## Access Control Lists

ACLs can control which traffic is permitted or denied between network segments.

## Port Security

Port security helps restrict unauthorized devices from connecting to designated switch ports.

## NAT

Network Address Translation allows private internal addresses to communicate with external networks through address translation.

## Secure Management

SSH can be used to protect administrative access to network devices.

# 🖥️ Network Services

The topology includes infrastructure for:

- DHCP
- DNS
- Web services
- Authentication
- Network management

## DHCP

DHCP automatically provides IP configuration information such as IP address, subnet mask, default gateway, and DNS server.

## DNS

DNS translates domain names into IP addresses.

## Server

The topology includes a dedicated server for required network services.

# 🛡️ Network Redundancy

The design uses redundancy concepts such as:

- Two Core Switches
- Two Distribution Switches
- Multiple network paths
- HSRP
- Redundant infrastructure connections
- Wireless connectivity redundancy where applicable

The purpose is to reduce single points of failure and improve network availability.

# 🏗️ Physical and Logical Design

## Physical Design

The physical design considers:

- Buildings
- Floors
- Network devices
- Switch locations
- End-user connections
- Wireless Access Points
- Server connectivity

## Logical Design

The logical design considers:

- VLANs
- IP addressing
- Subnetting
- Routing
- Security
- Network services
- Redundancy

# 🧪 Network Testing and Verification

The completed network can be tested for:

- Device connectivity
- VLAN operation
- Trunk connectivity
- Inter-VLAN communication
- Routing
- OSPF neighbors
- Gateway redundancy
- DHCP operation
- DNS operation
- Security policies
- Wireless connectivity

# 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Cisco Packet Tracer | Network simulation |
| IPv4 | Network addressing |
| Subnetting | Network segmentation |
| VLSM | Address planning |
| VLAN | Logical network separation |
| 802.1Q | VLAN trunking |
| Layer 2 Switching | Local network connectivity |
| Layer 3 Switching | Routing between networks |
| Inter-VLAN Routing | Communication between VLANs |
| OSPF | Dynamic routing |
| HSRP | Gateway redundancy |
| ACL | Traffic control |
| NAT | Address translation |
| DHCP | Automatic IP configuration |
| DNS | Name resolution |
| SSH | Secure device management |
| Port Security | Switch-port protection |
| Wireless Networking | Wireless user access |

# 🖥️ Network Devices

## Routing and Security

- 1 Router
- 1 Firewall

## Switching

- 2 Core Switches
- 2 Distribution Switches
- 10 Access Switches

## Network Services

- Server(s)

## End Devices

- PCs
- Wireless Access Points
- Wireless clients where applicable

# 📁 Project Structure

```text
cisco-packet-tracer-university-network/
│
├── README.md
│
└── HU-University-Network.pkt.pkt
```

# 📄 Packet Tracer Project

The main project file is:

```text
HU-University-Network.pkt.pkt
```

Open it using **Cisco Packet Tracer** to view and interact with the simulated university network.

# 🎓 Academic Context

This project was developed as an academic and practical networking project for **Computer Science studies at Hawassa University**.

It demonstrates practical understanding of computer networking, network architecture, Cisco networking, IP addressing, VLANs, routing, network security, wireless networking, and troubleshooting.

# 📚 Learning Outcomes

This project provides practical experience in:

- Designing enterprise-style networks
- Creating hierarchical network architectures
- Planning IPv4 address spaces
- Calculating subnets
- Creating VLAN-based network segmentation
- Understanding Layer 2 and Layer 3 networking
- Implementing routing concepts
- Understanding network redundancy
- Applying network security concepts
- Designing wireless connectivity
- Working with Cisco IOS
- Using Cisco Packet Tracer
- Testing network connectivity
- Troubleshooting network problems
- Documenting network infrastructure

# 🌍 Real-World Application

The concepts demonstrated in this project can be applied to:

- Universities
- Colleges
- Schools
- Offices
- Government organizations
- Hospitals
- Enterprise networks

A hierarchical network design makes it easier to expand the network as the number of users, buildings, departments, and services increases.

# 🚀 Future Improvements

Possible future improvements include:

- Adding additional university buildings
- Increasing VLAN segmentation where required
- Implementing IPv6
- Improving wireless coverage
- Adding wireless controller redundancy
- Expanding network monitoring
- Adding centralized authentication
- Implementing more advanced security policies
- Adding additional servers and services
- Implementing network logging and monitoring
- Improving high-availability mechanisms
- Integrating additional WAN connections

# 📊 Project Summary

| Category | Details |
|---|---|
| Project | HU University Network |
| Institution | Hawassa University |
| Country | Ethiopia |
| Simulation Platform | Cisco Packet Tracer |
| Buildings | 2 |
| Floors | 5 |
| Approximate Hosts | 180 |
| VLANs | 10 |
| Address Block | 192.168.16.0/23 |
| VLAN Subnets | /27 |
| Core Switches | 2 |
| Distribution Switches | 2 |
| Access Switches | 10 |
| Router | 1 |
| Firewall | 1 |
| Wireless | Supported |
| Routing | OSPF |
| Gateway Redundancy | HSRP |
| Security | ACL, Port Security, Firewall, NAT |
| Services | DHCP, DNS, Web/Server Services |

# 👨‍💻 Author

## Eshetu Alemu

**Computer Science Student**  
**Hawassa University**  
**Ethiopia 🇪🇹**

# 📌 Repository

**Cisco Packet Tracer University Network**

Repository:

`eshetualemu4020-dev/cisco-packet-tracer-university-network`

# ⭐ Acknowledgment

This project was developed for educational purposes to strengthen practical knowledge and experience in computer networking, Cisco technologies, network design, and network troubleshooting.

---

## 🎓 Final Project Statement

The **HU University Network** demonstrates how a university can be organized into a structured, scalable, secure, and redundant network using modern networking concepts.

The project combines **hierarchical network design, VLAN segmentation, IPv4 addressing, subnetting, routing, redundancy, security, wireless networking, and network services** in a simulated Cisco environment.

**Built with Cisco Packet Tracer | Hawassa University | Ethiopia 🇪🇹**
