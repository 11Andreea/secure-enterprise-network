# IP Addressing



After configuring the VLANs, the next step is to configure the IP addressing scheme. Each VLAN is assigned its own IP subnet, allowing devices from different network segments to be managed and controlled separately.



The internal network uses the private `10.0.0.0/8` address space.



## IP Addressing Scheme



Each VLAN is assigned a `/24` subnet. The first usable address in each subnet is reserved for the VLAN gateway.



| VLAN | Name | Subnet | Gateway | Usable Address Range | Broadcast |
|------|------|--------|---------|----------------------|-----------|
| 10 | ADMIN | `10.10.10.0/24` | `10.10.10.1` | `10.10.10.2 – 10.10.10.254` | `10.10.10.255` |
| 20 | IT | `10.10.20.0/24` | `10.10.20.1` | `10.10.20.2 – 10.10.20.254` | `10.10.20.255` |
| 30 | USERS | `10.10.30.0/24` | `10.10.30.1` | `10.10.30.2 – 10.10.30.254` | `10.10.30.255` |
| 40 | SERVERS | `10.10.40.0/24` | `10.10.40.1` | `10.10.40.2 – 10.10.40.254` | `10.10.40.255` |
| 50 | GUEST | `10.10.50.0/24` | `10.10.50.1` | `10.10.50.2 – 10.10.50.254` | `10.10.50.255` |
| 60 | DMZ | `10.10.60.0/24` | `10.10.60.1` | `10.10.60.2 – 10.10.60.254` | `10.10.60.255` |
| 99 | MANAGEMENT | `10.10.99.0/24` | `10.10.99.1` | `10.10.99.2 – 10.10.99.254` | `10.10.99.255` |
| 999 | UNUSED | N/A | N/A | N/A | N/A |



The subnet mask used for all internal networks is:



```text

255.255.255.0

````



or, in CIDR notation:



```text

/24

```



## Addressing Structure



The IP addressing scheme was designed so that the VLAN can be easily identified from the IP address.



The general structure is:



```text

10.<VLAN-ID>.0.0/24

```



For example:



```text

VLAN 10 → 10.10.0.0/24

VLAN 20 → 10.20.0.0/24

VLAN 30 → 10.30.0.0/24

VLAN 40 → 10.40.0.0/24

VLAN 50 → 10.50.0.0/24

VLAN 60 → 10.60.0.0/24

VLAN 99 → 10.99.0.0/24

```



This structure makes the network easier to manage and allows administrators to quickly identify the segment to which an IP address belongs.



## Gateway Addresses



The first usable address of each subnet is reserved for the default gateway.



```text

VLAN 10 → 10.10.0.1

VLAN 20 → 10.20.0.1

VLAN 30 → 10.30.0.1

VLAN 40 → 10.40.0.1

VLAN 50 → 10.50.0.1

VLAN 60 → 10.60.0.1

VLAN 99 → 10.99.0.1

```



Devices belonging to each VLAN will use the corresponding gateway address when communicating with devices located outside their local subnet.



## Reserved Address Ranges



To keep the addressing scheme organized, part of each subnet is reserved for infrastructure and devices that require static IP addresses.



The proposed structure is:



```text

10.X.0.1        → Default gateway

10.X.0.2–99     → Infrastructure and static devices

10.X.0.100–254   → DHCP clients

```



This separation prevents conflicts between statically configured devices and dynamically assigned addresses.


## Network Device Addressing



The Layer 3 interfaces responsible for routing between VLANs will use the gateway addresses defined for each subnet.



The addressing plan is:



```text

VLAN 10 → 10.10.0.1/24

VLAN 20 → 10.20.0.1/24

VLAN 30 → 10.30.0.1/24

VLAN 40 → 10.40.0.1/24

VLAN 50 → 10.50.0.1/24

VLAN 60 → 10.60.0.1/24

VLAN 99 → 10.99.0.1/24

```



These addresses act as the default gateways for the corresponding VLANs.



## End Device Addressing



End devices in the user-oriented VLANs can receive their IP addresses automatically through DHCP.



For a workstation in VLAN 20, the addressing parameters will follow this structure:



```text

IP Address:      10.20.0.x

Subnet Mask:     255.255.255.0

Default Gateway: 10.20.0.1

```



For a workstation in VLAN 40:



```text

IP Address:      10.40.0.x

Subnet Mask:     255.255.255.0

Default Gateway: 10.40.0.1

```



Devices that require stable and predictable addresses, such as servers and network infrastructure devices, should use static IP addresses.



## Addressing Verification



After configuring the IP addresses, the configuration can be verified using:



```text

show ip interface brief

```



This command displays:



* Interface name

* IP address

* Interface status

* Protocol status



The output should show the configured interfaces with their corresponding IP addresses and an operational status of `up/up` where applicable.



## Connectivity Testing



Basic IP connectivity can be tested using the `ping` command:



```text

ping <IP-address>

```



For example:



```text

ping 10.20.0.1

```



A successful response confirms that the source device can reach the specified destination.



The gateway of each VLAN should be tested individually:



```text

ping 10.10.0.1

ping 10.20.0.1

ping 10.30.0.1

ping 10.40.0.1

ping 10.50.0.1

ping 10.60.0.1

ping 10.99.0.1

```



## Addressing Validation



The IP addressing configuration is considered correct when:



* Each VLAN has its own dedicated subnet.

* Each subnet uses the correct `/24` mask.

* Each VLAN has a unique default gateway.

* End devices have addresses belonging to their assigned VLAN subnet.

* Static addresses do not overlap with the DHCP address range.

* Devices can reach their local gateway.

* The network interfaces show the expected operational status.



The resulting addressing scheme provides a structured foundation for the rest of the network configuration, including routing, DHCP, access control, and security policies.




