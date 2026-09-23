## VLAN Configuration

| VLAN ID | Name | Network | Gateway | Purpose |
|--------:|------|---------|---------|---------|
| 10 | ADMIN | `10.10.10.0/24` | `10.10.10.1` | Administration department |
| 20 | IT | `10.10.20.0/24` | `10.10.20.1` | IT department and network administration |
| 30 | USERS | `10.10.30.0/24` | `10.10.30.1` | General employees and workstations |
| 40 | SERVERS | `10.10.40.0/24` | `10.10.40.1` | Internal enterprise servers |
| 50 | GUEST | `10.10.50.0/24` | `10.10.50.1` | Guest devices with restricted access |
| 60 | DMZ | `10.10.60.0/24` | `10.10.60.1` | Public-facing services |
| 99 | MANAGEMENT | `10.10.99.0/24` | `10.10.99.1` | Network device management |
| 999 | UNUSED | N/A | N/A | Unused switch ports |

## Network Segmentation

The network is divided into separate VLANs to provide logical segmentation between departments, servers, guest devices, management interfaces, and public-facing services.

- **VLAN 10 – ADMIN:** Administration workstations.
- **VLAN 20 – IT:** IT department and network administration systems.
- **VLAN 30 – USERS:** General employee workstations.
- **VLAN 40 – SERVERS:** Internal infrastructure and application servers.
- **VLAN 50 – GUEST:** Guest devices with restricted access to internal resources.
- **VLAN 60 – DMZ:** Public-facing services such as the web and mail servers.
- **VLAN 99 – MANAGEMENT:** Dedicated management network for switches and other network devices.
- **VLAN 999 – UNUSED:** Dedicated VLAN for unused switch ports.