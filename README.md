# 🔐 Secure Enterprise Network

> A work-in-progress enterprise network designed and simulated in Cisco Packet Tracer, with a focus on network segmentation, services, security, and infrastructure management.

## 🚧 Project Status

**Work in Progress**

This project is currently under development. The network topology and core configuration are being built incrementally, with additional security features, services, testing, and documentation planned.

Some configurations may be incomplete or subject to change.

---

## 📌 Overview

The goal of this project is to design and simulate a small enterprise network that includes:

- VLAN-based network segmentation
- Inter-VLAN routing
- DHCP and DNS services
- Internal servers
- DMZ infrastructure
- Firewall configuration
- Internet/ISP connectivity
- Network security controls
- Infrastructure management and monitoring
- Documentation and troubleshooting

The project is being developed in **Cisco Packet Tracer** as a practical networking and cybersecurity project.

---

## 🗺️ Network Architecture

The network is divided into several logical segments:

| VLAN | Name | Network | Purpose |
|------|------|---------|---------|
| 10 | ADMIN | `10.10.10.0/24` | Administration |
| 20 | IT | `10.10.20.0/24` | IT department |
| 30 | USERS | `10.10.30.0/24` | General users |
| 40 | SERVERS | `10.10.40.0/24` | Internal servers |
| 50 | GUEST | `10.10.50.0/24` | Guest devices |
| 60 | DMZ | `10.10.60.0/24` | Public-facing services |

> The topology and addressing scheme may change during development.

---

## 🛠️ Technologies & Tools

- **Cisco Packet Tracer**
- Cisco IOS
- VLANs
- 802.1Q Trunking
- Inter-VLAN Routing
- DHCP
- DNS
- NAT
- ACLs
- DMZ
- Firewall
- SNMP
- Syslog
- Network troubleshooting
- TCP/IP

---

## 🎯 Current Progress

### Completed

- [x] Initial network topology
- [x] VLAN structure
- [x] IP addressing plan
- [x] DHCP configuration
- [x] Basic DNS configuration
- [x] Basic connectivity testing
- [x] Initial server infrastructure
- [x] DMZ network planning
- [x] ACL implementation
- [x] Harden network devices
- [x] Syslog
- [x] NAT configuration
- [x] DMZ services
- [x] Firewall configuration

### In Progress


- [ ] Internet / ISP connectivity
- [ ] Security testing
- [ ] Full connectivity testing
- [ ] Network documentation

### Planned

- [ ] Improve access control
- [ ] Test VLAN isolation
- [ ] Test DMZ security
- [ ] Document troubleshooting procedures
- [ ] Finalize configuration
- [ ] Final project review

---

## 🧪 Testing

Testing is performed throughout the development process rather than only after the network is completed.

Examples include:

- VLAN connectivity
- Inter-VLAN communication
- DHCP address assignment
- DNS resolution
- Server accessibility
- DMZ accessibility
- NAT translation
- Internet connectivity
- ACL behavior
- Management access
- Network isolation

Issues discovered during development are documented separately.

---

## 🐛 Known Issues

This project is still under development, so some features may not work as expected.

Current issues and troubleshooting notes are tracked through the repository's **GitHub Issues**.

---

## ⚠️ Disclaimer

This is an educational project created for learning and experimentation.

The network is simulated in Cisco Packet Tracer and is not intended to represent a production-ready enterprise infrastructure.

---

## 👩‍💻 Author

### Andreea
> Student interested in networking, cybersecurity, software development, and infrastructure.
