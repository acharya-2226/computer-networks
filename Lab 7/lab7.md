# Lab 7: Configuration of Switch, VLAN Configuration and Inter-VLAN Routing

## Objectives
- To create and configure multiple VLANs on a network switch.
- To configure trunking and assign switch ports to appropriate VLANs.
- To implement and verify Inter-VLAN Routing using a router.

## Theory

### 1) Switch Configuration
A switch is a Layer 2 network device used to connect multiple devices within a local area network. It forwards data frames based on MAC addresses, ensuring efficient communication between connected devices. Switch configuration involves setting up interfaces, enabling or disabling ports, and assigning ports to VLANs. Proper switch configuration helps in reducing collisions, improving network performance, and organizing network traffic effectively.

### 2) Virtual Local Area Network (VLAN)
A VLAN (Virtual Local Area Network) is a logical segmentation of a network within a switch. VLANs allow devices to be grouped together even if they are physically connected to different switch ports. This logical separation reduces broadcast traffic, improves security, and simplifies network management. Each VLAN acts as an independent broadcast domain.

### 3) VLAN Configuration
VLAN configuration involves creating VLANs on the switch and assigning them unique VLAN IDs and names. After creating VLANs, switch ports are configured in access mode and assigned to specific VLANs. Devices connected to these ports can communicate only with devices in the same VLAN unless routing is enabled. VLAN configuration is essential for controlling network traffic and improving scalability.

### 4) Inter-VLAN Routing
Inter-VLAN routing is the process of forwarding network traffic between different VLANs. Since VLANs are separate broadcast domains, a Layer 3 device such as a router is required for communication between them. In this method, a single physical router interface is divided into multiple sub-interfaces, each configured for a specific VLAN. This approach is commonly known as Router-on-a-Stick.

## Network Topology
- 1 Switch
- 1 Router
- 4 PCs
- VLAN 10 and VLAN 20 configured on the switch
- Trunk link between switch and router

## Observation
- Ping in same VLAN: Successful
- Ping between different VLANs: Successful after inter-VLAN routing configuration

## Configuration

### VLAN and IP Addressing Scheme

| VLAN | Name | Network | Gateway |
|------|------|---------|---------|
| 10 | Computer | 192.168.10.0/24 | 192.168.10.1 |
| 20 | Electronics | 192.168.20.0/24 | 192.168.20.1 |

| Device | IPv4 Address | Subnet Mask | Default Gateway |
|--------|--------------|-------------|-----------------|
| PC0 | 192.168.10.2 | 255.255.255.0 | 192.168.10.1 |
| PC1 | 192.168.10.3 | 255.255.255.0 | 192.168.10.1 |
| PC2 | 192.168.20.2 | 255.255.255.0 | 192.168.20.1 |
| PC3 | 192.168.20.3 | 255.255.255.0 | 192.168.20.1 |

## Commands

### Switch Configuration

#### 1) Create VLANs
```bash
Switch(config)# vlan 10
Switch(config-vlan)# name Computer
Switch(config-vlan)# exit
Switch(config)# vlan 20
Switch(config-vlan)# name Electronics
Switch(config-vlan)# exit
```

#### 2) Assign Ports to VLANs
```bash
Switch(config)# interface range fa0/1-2
Switch(config-if-range)# switchport mode access
Switch(config-if-range)# switchport access vlan 10
Switch(config-if-range)# exit
Switch(config)# interface range fa0/3-4
Switch(config-if-range)# switchport mode access
Switch(config-if-range)# switchport access vlan 20
Switch(config-if-range)# exit
```

#### 3) Configure Trunk Port (Switch-Router)
```bash
Switch(config)# interface fa0/5
Switch(config-if)# switchport mode trunk
Switch(config-if)# exit
```

#### Verification on Switch
```bash
Switch# show vlan brief
```

### Router Configuration (Inter-VLAN Routing)
```bash
Router(config)# interface GigabitEthernet 0/0.10
Router(config-subif)# encapsulation dot1Q 10
Router(config-subif)# ip address 192.168.10.1 255.255.255.0
Router(config-subif)# exit
Router(config)# interface GigabitEthernet 0/0.20
Router(config-subif)# encapsulation dot1Q 20
Router(config-subif)# ip address 192.168.20.1 255.255.255.0
Router(config-subif)# exit
```

## Result
In this experiment, the switch was successfully configured with multiple VLANs, and ports were correctly assigned to their respective VLANs. A trunk link was established between the switch and the router. Inter-VLAN routing was implemented using router sub-interfaces. Devices within the same VLAN were able to communicate with each other, and communication between different VLANs was successfully achieved through the router.

## Discussion
The configuration of VLANs logically separated the network into different broadcast domains, which reduced unnecessary broadcast traffic and improved network efficiency. Assigning switch ports to specific VLANs ensured that devices were grouped according to their function. The trunk port allowed multiple VLAN traffic to pass between the switch and the router using VLAN tagging. Inter-VLAN routing enabled controlled communication between VLANs while maintaining network segmentation. Verification commands confirmed that the VLANs, trunk links, and routing were correctly configured.

## Conclusion
The objectives of configuring VLANs on a switch and enabling inter-VLAN routing using a router were successfully implemented and verified.