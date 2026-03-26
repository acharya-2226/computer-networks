# Final Project Report

## 1. Question (Task)
Design and implement a small enterprise network in Cisco Packet Tracer with the following requirements:
- 3 routers using RIP version 2 for dynamic routing.
- VLANs and trunking for LAN segmentation.
- DHCP for all VLAN user networks.
- DNS server with multiple host records.
- Default routes where required.
- Network summarization concept at the core router.

## 2. Problem Statement
A multi-router, multi-VLAN network must provide end-to-end connectivity and name resolution across departments. The network should automatically assign IP addresses to clients, route traffic between VLANs and remote LANs, and resolve hostnames through a central DNS service. The implementation must be stable, scalable, and testable using standard verification commands.

## 3. Components Required
- 3 x Cisco 2811 Routers
  - Router0 (Core)
  - Router1 (Left branch, VLAN 10/20 gateway)
  - Router2 (Right branch, VLAN 30 gateway)
- 2 x Cisco 2960 Switches
  - Switch0 (Left access switch)
  - Switch1 (Right access switch)
- 4 x PCs
  - PC1, PC2, PC3, PC4
- 1 x Server-PT
  - DNS Server
- Cables
  - Serial DCE/DTE links between routers
  - Copper straight-through for router-switch, switch-PC, switch-server links

## 4. Theory (Basic)
### RIP v2
RIP v2 is a distance-vector routing protocol that exchanges routes using hop count as the metric. It supports classless routing (CIDR/VLSM) and sends periodic route updates.

### VLAN and Trunking
VLANs split a switch into multiple logical broadcast domains. Trunk links carry traffic for multiple VLANs using 802.1Q tagging.

### Inter-VLAN Routing (Router-on-a-Stick)
Router subinterfaces (for example, Fa0/0.10, Fa0/0.20, Fa0/0.30) are used as default gateways for VLANs.

### DHCP
DHCP dynamically assigns IP settings (IP, mask, gateway, DNS) to clients from defined address pools.

### DNS
DNS maps hostnames (for example, pc3.local) to IP addresses for easier access and management.

## 5. Procedure

### 5.1 Basic Initial Configuration (All Routers and Switches)
Apply on each router/switch (change hostname as needed):

```text
enable
configure terminal
hostname <DeviceName>
no ip domain-lookup
line con 0
logging synchronous
exit
line vty 0 4
login
exit
end
write memory
```

### 5.2 Router0 (Core) Configuration

```text
enable
configure terminal
hostname Router0

interface serial0/2/0
ip address 10.0.0.1 255.255.255.252
clock rate 64000
no shutdown
exit

interface serial0/3/0
ip address 10.0.1.1 255.255.255.252
clock rate 64000
no shutdown
exit

router rip
version 2
network 10.0.0.0
no auto-summary
default-information originate
exit

ip route 0.0.0.0 0.0.0.0 serial0/2/0
end
write memory
```

Note:
- FastEthernet0/0 on Router0 was removed from VLAN 10 ownership to avoid duplicate gateway/network conflict.
- Router0 learns 192.168.10.0, 192.168.20.0, and 192.168.30.0 via RIP.

### 5.3 Router1 Configuration (VLAN 10 and VLAN 20 Gateway + DHCP)

```text
enable
configure terminal
hostname Router1

interface serial0/3/0
ip address 10.0.0.2 255.255.255.252
no shutdown
exit

interface fastethernet0/0
no shutdown
exit

interface fastethernet0/0.10
encapsulation dot1Q 10
ip address 192.168.10.1 255.255.255.0
exit

interface fastethernet0/0.20
encapsulation dot1Q 20
ip address 192.168.20.1 255.255.255.0
exit

router rip
version 2
network 10.0.0.0
network 192.168.10.0
network 192.168.20.0
no auto-summary
exit

ip dhcp excluded-address 192.168.10.1 192.168.10.20
ip dhcp excluded-address 192.168.20.1 192.168.20.20

ip dhcp pool VLAN10
network 192.168.10.0 255.255.255.0
default-router 192.168.10.1
dns-server 192.168.10.100
exit

ip dhcp pool VLAN20
network 192.168.20.0 255.255.255.0
default-router 192.168.20.1
dns-server 192.168.10.100
exit

ip route 0.0.0.0 0.0.0.0 10.0.0.1
end
write memory
```

### 5.4 Router2 Configuration (VLAN 30 Gateway + DHCP)

```text
enable
configure terminal
hostname Router2

interface serial0/3/0
ip address 10.0.1.2 255.255.255.252
no shutdown
exit

interface fastethernet0/0
no shutdown
exit

interface fastethernet0/0.30
encapsulation dot1Q 30
ip address 192.168.30.1 255.255.255.0
exit

router rip
version 2
network 10.0.0.0
network 192.168.30.0
no auto-summary
exit

ip dhcp excluded-address 192.168.30.1 192.168.30.20

ip dhcp pool VLAN30
network 192.168.30.0 255.255.255.0
default-router 192.168.30.1
dns-server 192.168.10.100
exit

ip route 0.0.0.0 0.0.0.0 10.0.1.1
end
write memory
```

### 5.5 Switch0 Configuration (VLAN 10, VLAN 20, Trunk, DNS Port)
Assumed port mapping:
- Fa0/1 trunk to Router1
- Fa0/2 PC1 (VLAN 10)
- Fa0/3 PC2 (VLAN 20)
- Fa0/5 DNS Server (VLAN 10)

```text
enable
configure terminal
hostname Switch0

vlan 10
name SALES
exit

vlan 20
name HR
exit

interface fa0/1
switchport mode trunk
no shutdown
exit

interface fa0/2
switchport mode access
switchport access vlan 10
no shutdown
exit

interface fa0/3
switchport mode access
switchport access vlan 20
no shutdown
exit

interface fa0/5
switchport mode access
switchport access vlan 10
no shutdown
exit

end
write memory
```

### 5.6 Switch1 Configuration (VLAN 30 + Trunk)
Assumed port mapping:
- Fa0/1 trunk to Router2
- Fa0/2 PC3 (VLAN 30)
- Fa0/3 PC4 (VLAN 30)

```text
enable
configure terminal
hostname Switch1

vlan 30
name IT
exit

interface fa0/1
switchport mode trunk
no shutdown
exit

interface fa0/2
switchport mode access
switchport access vlan 30
no shutdown
exit

interface fa0/3
switchport mode access
switchport access vlan 30
no shutdown
exit

end
write memory
```

### 5.7 DNS Server Visual Configuration
Desktop -> IP Configuration:
- IP Address: 192.168.10.100
- Subnet Mask: 255.255.255.0
- Default Gateway: 192.168.10.1
- DNS Server: 192.168.10.100

Services -> DNS -> ON
Add records:
- dns.local -> 192.168.10.100
- pc2.local -> 192.168.20.2
- pc3.local -> 192.168.30.2
- pc4.local -> 192.168.30.3

### 5.8 PC Visual Configuration
Desktop -> IP Configuration -> DHCP on all PCs.
Expected:
- PC1 in 192.168.10.0/24
- PC2 in 192.168.20.0/24
- PC3 and PC4 in 192.168.30.0/24
- DNS server received as 192.168.10.100

## 6. Outcome
The final network satisfies all requirements:
- Dynamic routing via RIP v2 across 3 routers.
- VLAN segmentation and trunking operational.
- DHCP successfully assigns addresses for all VLANs.
- DNS resolves local hostnames across VLANs.
- End-to-end connectivity validated with ping by IP and hostname.

Sample successful tests:
- ping 192.168.30.2 from PC1: Success
- ping pc3.local from PC1: Success
- ping dns.local from clients: Success

## 7. Use Case
This design models a small multi-department office network:
- SALES (VLAN 10), HR (VLAN 20), IT (VLAN 30)
- Central core and branch routers
- Automated client onboarding using DHCP
- Internal name resolution using DNS

It can be used as a baseline for academic labs, SMB branch design practice, or protocol verification exercises.
