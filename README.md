# 🌐 Networking Lab Repository

[![Cisco Packet Tracer](https://img.shields.io/badge/Cisco-Packet%20Tracer-1BA0D7?style=flat&logo=cisco&logoColor=white)](https://www.netacad.com/courses/packet-tracer)
[![Networking](https://img.shields.io/badge/Topic-Networking-blue?style=flat)](https://github.com/sharansidh-0301/Networking)
[![CCNA](https://img.shields.io/badge/Certification-CCNA-00A3E0?style=flat&logo=cisco)](https://www.cisco.com/c/en/us/training-events/training-certifications/certifications/associate/ccna.html)

A comprehensive collection of Cisco networking configurations, simulations, and documentation for learning and practicing core networking concepts. This repository includes Packet Tracer topology files, configuration scripts, and visual documentation for various networking protocols and technologies.

## 📋 Table of Contents

- [Overview](#overview)
- [Repository Structure](#repository-structure)
- [Topics Covered](#topics-covered)
- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
- [Configuration Examples](#configuration-examples)
- [Resources](#resources)
- [Contributing](#contributing)
- [License](#license)

## 🎯 Overview

This repository serves as a practical learning resource for networking students and professionals preparing for Cisco certifications (CCNA, CCNP) or anyone interested in understanding network configuration and management. Each topic includes:

- 📦 **Packet Tracer Files (.pkt)**: Ready-to-use network topologies
- 📝 **Configuration Scripts (.txt)**: Step-by-step CLI commands
- 📸 **Screenshots**: Visual documentation of configurations
- 📚 **Documentation**: Detailed explanations and notes

## 📂 Repository Structure

```
Networking/
├── Access Control List/        # ACL configurations and examples
│   ├── Access Control List.pkt
│   ├── Access control list.txt
│   └── Screenshots/
├── DHCP-AutoIP-Config/        # DHCP and Auto-IP setup
│   ├── DHCP-AutoIP-Config.pkt
│   ├── DHCP-AutoIP-Config.txt
│   └── Screenshots/
├── Etherchannel/              # Link aggregation configurations
│   ├── Etherchannel.pkt
│   ├── Etherchanne.txt
│   ├── etherchannel2.pkt
│   └── etherchannel 2.txt
├── DNS-Config.pkt             # DNS server configuration
├── Telnet-Config.pkt          # Remote access via Telnet
├── WAP.pkt                    # Wireless Access Point setup
├── spannind-tree-protocol.pkt # STP configuration
├── tcp_udp_ports.jpg          # Port reference diagram
├── ccnaa.pdf                  # CCNA study materials
└── ccnaa.docx                 # Additional documentation
```

## 🔧 Topics Covered

### 1. Access Control Lists (ACL)
Learn how to implement standard and extended ACLs to control network traffic based on IP addresses, protocols, and ports.

**Key Concepts:**
- Standard ACLs (numbered and named)
- Extended ACLs
- ACL placement and best practices
- Wildcard mask configuration

### 2. DHCP & Auto-IP Configuration
Understand dynamic IP address assignment and automatic IP configuration for network devices.

**Key Concepts:**
- DHCP server configuration
- DHCP pool setup
- Default gateway assignment
- IP address exclusion ranges
- APIPA (Automatic Private IP Addressing)

### 3. DNS Configuration
Configure DNS services for hostname-to-IP address resolution in network environments.

**Key Concepts:**
- DNS server setup
- Forward and reverse lookup zones
- DNS client configuration
- Name resolution testing

### 4. Etherchannel (Link Aggregation)
Implement link aggregation to increase bandwidth and provide redundancy between switches.

**Key Concepts:**
- LACP (Link Aggregation Control Protocol)
- PAgP (Port Aggregation Protocol)
- Static Etherchannel configuration
- Load balancing methods

### 5. Spanning Tree Protocol (STP)
Configure STP to prevent network loops and ensure redundant paths in switched networks.

**Key Concepts:**
- STP operation and states
- Root bridge election
- Port roles (Root, Designated, Blocked)
- RSTP (Rapid Spanning Tree Protocol)
- Per-VLAN Spanning Tree (PVST+)

### 6. Telnet Configuration
Set up remote access to network devices using Telnet protocol.

**Key Concepts:**
- VTY line configuration
- Password authentication
- Enable secret configuration
- Access restrictions

### 7. Wireless Access Point (WAP)
Configure wireless networking with security and access control.

**Key Concepts:**
- SSID configuration
- WPA2/WPA3 security
- Wireless authentication
- Channel selection

### 8. TCP/UDP Ports Reference
Visual reference guide for commonly used TCP and UDP port numbers.

## 🛠️ Prerequisites

To work with the files in this repository, you'll need:

1. **Cisco Packet Tracer** (Version 7.3 or higher)
   - [Download from Cisco NetAcad](https://www.netacad.com/courses/packet-tracer)
   - Free with NetAcad account

2. **Basic Networking Knowledge**
   - Understanding of OSI model
   - IP addressing and subnetting
   - Basic routing and switching concepts

3. **Optional Tools**
   - Text editor for viewing configuration files
   - PDF reader for documentation

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/sharansidh-0301/Networking.git
cd Networking
```

### 2. Open Packet Tracer Files

1. Launch Cisco Packet Tracer
2. Navigate to `File` → `Open`
3. Select any `.pkt` file from the repository
4. Explore the topology and device configurations

### 3. Review Configuration Files

Each directory contains `.txt` files with CLI commands. You can:
- Copy and paste commands into Packet Tracer devices
- Use as reference for similar configurations
- Study the command syntax and parameters

### 4. Practice and Experiment

- Modify existing topologies
- Test different configurations
- Break and fix scenarios
- Document your own variations

## 💻 Configuration Examples

### Access Control List (Standard ACL)

```cisco
Router> enable
Router# configure terminal
Router(config)# ip access-list standard 10
Router(config-std-nacl)# permit 192.168.1.0 0.0.0.255
Router(config-std-nacl)# deny 192.168.2.0 0.0.0.255
Router(config-std-nacl)# exit
Router(config)# interface serial 0/1/0
Router(config-if)# ip access-group 10 out
```

### DHCP Configuration

```cisco
Router> enable
Router# configure terminal
Router(config)# ip dhcp pool LAN_POOL
Router(dhcp-config)# network 192.168.1.0 255.255.255.0
Router(dhcp-config)# default-router 192.168.1.1
Router(dhcp-config)# dns-server 8.8.8.8
Router(dhcp-config)# exit
Router(config)# ip dhcp excluded-address 192.168.1.1 192.168.1.10
```

### Etherchannel Configuration

```cisco
Switch> enable
Switch# configure terminal
Switch(config)# interface range fastEthernet 0/1-2
Switch(config-if-range)# channel-group 1 mode active
Switch(config-if-range)# exit
Switch(config)# interface port-channel 1
Switch(config-if)# switchport mode trunk
```

## 📚 Resources

### Official Documentation
- [Cisco IOS Command Reference](https://www.cisco.com/c/en/us/support/ios-nx-os-software/ios-15-4m-t/products-command-reference-list.html)
- [Cisco CCNA Study Materials](https://www.cisco.com/c/en/us/training-events/training-certifications/certifications/associate/ccna.html)

### Learning Resources
- [Cisco NetAcad](https://www.netacad.com/)
- [Packet Tracer Labs](https://www.packettracernetwork.com/)
- [Subnet Calculator](https://www.subnet-calculator.com/)

### Additional Materials
- `ccnaa.pdf` - CCNA study guide included in this repository
- `tcp_udp_ports.jpg` - Port number reference chart

## 🤝 Contributing

Contributions are welcome! If you'd like to add new network configurations or improve existing ones:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-config`)
3. Add your configurations with documentation
4. Commit your changes (`git commit -m 'Add new network configuration'`)
5. Push to the branch (`git push origin feature/new-config`)
6. Open a Pull Request

**Guidelines:**
- Include both `.pkt` files and `.txt` configuration files
- Add screenshots showing the working configuration
- Provide clear documentation
- Test configurations before submitting

## 📄 License

This repository is intended for educational purposes. All configurations and materials are provided as-is for learning and practice.

## 🙏 Acknowledgments

- Cisco Systems for Packet Tracer software
- Cisco NetAcad for training resources
- The networking community for continuous learning and sharing

## 📧 Contact

For questions or suggestions, please open an issue in this repository.

---

**⭐ If you find this repository helpful, please consider giving it a star!**

*Happy Networking! 🚀*
