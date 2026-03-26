# Lab 9: Wireless Network Setup and Packet Analysis using Cisco Packet Tracer

## Objectives
- To configure a wireless router and establish a wireless network using Cisco Packet Tracer.
- To connect wireless devices to the network and assign IP addresses using DHCP.
- To verify secure wireless communication using WPA2 security settings.

## Theory
A wireless network allows devices to communicate without physical connections by using radio waves. In this lab, a wireless router is configured to create a wireless local area network (WLAN) that provides connectivity, IP address assignment through DHCP, and secure access to wireless devices. The router assigns IP addresses automatically to connected clients, ensuring efficient network communication.

An SSID is used to identify the wireless network, while WPA2 security with AES encryption ensures secure communication by protecting the network from unauthorized access. Wireless devices connect to the network using the correct SSID and passphrase, after which communication can be verified through network testing.

Packet analysis is used to observe and understand the flow of data between wireless devices and the router. Using the simulation and packet inspection features of Cisco Packet Tracer, different types of packets such as DHCP, ARP, and data packets can be analyzed. This helps in understanding how devices obtain IP addresses, establish connections, and transmit data over a wireless network. Packet analysis also assists in verifying successful communication and troubleshooting network issues, making it an important part of wireless network implementation.

## Network Topology
- 1 Wireless Router (WRT300N)
- 2 Wireless Clients (Laptop0 and Laptop1)
- WLAN parameters:
  - Network IP: 192.168.0.0/24
  - Router/Gateway IP: 192.168.0.1
  - SSID: HCOE

## Procedure

### Wireless Router Configuration

### Step 1: Basic Setup
1. Click on the wireless router.
2. Go to GUI -> Setup.
3. Configure the following:
   - IP Address: 192.168.0.1
   - Subnet Mask: 255.255.255.0
   - DHCP Server: Enabled

### Step 2: Wireless Configuration
1. Go to Wireless -> Basic Wireless Settings.
2. Configure the following parameters:
   - Network Mode: Mixed
   - SSID: HCOE
   - Channel: Auto
3. Click Save Settings.

### Step 3: Wireless Security
1. Go to Wireless -> Wireless Security.
2. Configure the following:
   - Security Mode: WPA2-Personal
   - Encryption: AES
   - Passphrase: hcoe@123
3. Save the configuration.

### Step 4: Connect Wireless Clients
1. Open Laptop0 and Laptop1 wireless settings.
2. Search for available wireless networks.
3. Select SSID HCOE.
4. Enter the passphrase hcoe@123.
5. Verify that both clients receive IP addresses automatically through DHCP.

### Step 5: Packet Analysis
1. Switch Packet Tracer to Simulation mode.
2. Generate traffic between Laptop0 and Laptop1 (for example, by using ping).
3. Observe packet flow for DHCP, ARP, and ICMP/data frames.
4. Inspect packet details at each hop to verify successful communication.

## Observation
- Both wireless clients detected SSID HCOE and connected successfully using the WPA2 passphrase.
- DHCP assigned valid IP addresses from the router's network pool.
- Simulation mode showed expected DHCP discovery/offer/request/ack sequence, ARP resolution, and data packet transfer.

## Result
The setup successfully established a functional wireless network using a WRT300N router. By setting the SSID to HCOE and enabling the DHCP server at the gateway address 192.168.0.1, the infrastructure was ready for client connection. Both Laptop0 and Laptop1 detected the network with strong signal strength and successfully joined after authenticating with the WPA2-PSK passphrase hcoe@123. The result was a verified connection where both devices received their IP addresses automatically and could exchange data packets through the router.

## Discussion
This lab shows how DHCP and WPA2 security work together to create a usable and safe wireless network. By enabling the DHCP server, the router automatically handled IP addressing for both laptops, which is faster and more reliable than manual setup. Setting security to WPA2-Personal with AES encryption was the most critical step, as it protects the network from unauthorized access by requiring a specific passphrase.

Packet analysis in simulation mode provided visibility into each stage of communication, from address assignment to successful data delivery. This helps in validating the network setup and also in troubleshooting connectivity issues when a wireless client fails to connect.

## Conclusion
The lab successfully demonstrated that a secure and functional wireless network can be established by correctly configuring SSID, WPA2 security, and DHCP services. Packet analysis further confirmed proper network operation and improved understanding of wireless communication behavior in Cisco Packet Tracer.