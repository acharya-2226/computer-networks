# Lab 8: Server Configuration - DHCP, DNS and Web Server in Cisco Packet Tracer

## Objectives
- To configure a server to provide DHCP, DNS, and Web (HTTP) services in Cisco Packet Tracer.
- To understand how DHCP assigns IP addresses and how DNS resolves domain names in a network.
- To verify the proper functioning of server services by accessing the web server from client devices.

## Theory

### 1) Server Configuration
Server configuration is the process of setting up a server to provide services to client devices in a network. A server is usually assigned a static IP address so that clients can reliably access its services. In this lab, a single server is configured to provide DHCP, DNS, and Web (HTTP) services. Proper server configuration ensures smooth communication, centralized control, and efficient network management.

### 2) DHCP (Dynamic Host Configuration Protocol)
DHCP is a network protocol that automatically assigns IP addresses and other network parameters such as subnet mask, default gateway, and DNS server to client devices. Instead of manually configuring each PC, DHCP dynamically provides these details when a device joins the network. This reduces configuration errors, saves time, and makes network management easier. In this lab, the DHCP server creates a pool of IP addresses and distributes them to client PCs automatically.

### 3) DNS (Domain Name System)
DNS is used to convert domain names into IP addresses. Humans find it easier to remember names like www.hcoe.com rather than numerical IP addresses. The DNS server stores records that map domain names to corresponding IP addresses. When a client requests a website using a domain name, the DNS server resolves the name and returns the correct IP address. In this lab, DNS records are added so clients can access the web server using a domain name.

### 4) Web Server (HTTP Service)
A web server provides web pages to clients using the HTTP protocol. It hosts website files such as HTML pages and responds to client requests made through a web browser. In this lab, the HTTP service is enabled on the server, allowing client PCs to access a webpage using a browser. This demonstrates how websites are hosted and accessed within a network environment.

### Integration of DHCP, DNS, and Web Server
DHCP, DNS, and Web Server services work together to provide a complete networking experience. DHCP assigns IP addresses, DNS resolves domain names, and the web server delivers web content. The integration of these services allows users to access web resources easily without manual configuration, demonstrating the importance of centralized server-based services in modern networks.

## Network Topology
- 1 Server (Server0)
- 2 PCs (PC0, PC1)
- 1 Router/Gateway
- Switched LAN network: 192.168.1.0/24

## Configuration

### IP Addressing Scheme

| Device | IP Address | Subnet Mask | Gateway |
|--------|------------|-------------|---------|
| Server0 | 192.168.1.2 | 255.255.255.0 | 192.168.1.1 |
| PCs | DHCP | DHCP | DHCP |

### Client Details (After DHCP)

| Device | IPv4 Address | Subnet Mask | Default Gateway | DNS Server |
|--------|--------------|-------------|-----------------|------------|
| PC0 | 192.168.1.10 (example) | 255.255.255.0 | 192.168.1.1 | 192.168.1.2 |
| PC1 | 192.168.1.11 (example) | 255.255.255.0 | 192.168.1.1 | 192.168.1.2 |

### Server Network Parameters

| Device | Default Gateway | DNS Server |
|--------|-----------------|------------|
| Server0 | 192.168.1.1 | 192.168.1.2 |

## Procedure

### Server Configuration

### Step 1: Assign Static IP to Server
1. Click on Server.
2. Go to Desktop -> IP Configuration.
3. Configure the following:
   - IP Address: 192.168.1.2
   - Subnet Mask: 255.255.255.0
   - Default Gateway: 192.168.1.1
   - DNS Server: 192.168.1.2

### DHCP Configuration

### Step 2: Enable DHCP Service
1. Go to Server -> Services -> DHCP.
2. Turn DHCP: ON.

### Step 3: Create DHCP Pool
1. Click Add after filling pool values:

| Field | Value |
|-------|-------|
| Pool Name | LAB_POOL |
| Default Gateway | 192.168.1.1 |
| DNS Server | 192.168.1.2 |
| Start IP Address | 192.168.1.10 |
| Subnet Mask | 255.255.255.0 |
| Maximum Users | 50 |

### Verification (DHCP)
On each PC:
- Go to Desktop -> IP Configuration.
- Select DHCP.

### DNS Server Configuration

### Step 4: Enable DNS Service
1. Go to Server -> Services -> DNS.
2. Turn DNS: ON.

### Step 5: Add DNS Records
- Name: www.hcoe.com
- Type: A Record
- Address: 192.168.1.2
- Click Add.

### Verification (DNS)
On each PC:
- Open Command Prompt.
- Ping: www.hcoe.com

### Web Server Configuration

### Step 6: Enable HTTP Service
1. Go to Server -> Services -> HTTP.
2. Turn HTTP: ON.
3. Edit index.html (optional).

### Verification (Web)
On PC:
- Go to Desktop -> Browser.
- Type: http://www.hcoe.com

## Result
The DHCP, DNS, and web server were successfully configured in Cisco Packet Tracer as per the lab objectives. The server was assigned a static IP address, and all client PCs obtained valid network configuration automatically through the DHCP service. DNS name resolution worked correctly, allowing clients to access the web server using the configured domain name. The HTTP service was enabled, and the webpage was accessed successfully from client devices, confirming proper operation of all configured services.

## Discussion
This lab demonstrated the practical implementation of essential network services and their role in efficient network communication. DHCP reduced manual IP configuration, while DNS simplified access to network resources through domain names. The successful web server access verified proper application-layer communication. The lab also improved understanding of service dependency, correct parameter configuration, and basic troubleshooting in a simulated networking environment.

## Conclusion
The objectives of configuring DHCP, DNS, and HTTP services on a server in Cisco Packet Tracer were successfully achieved, with proper IP address assignment, domain name resolution, and verified web server access from client devices.