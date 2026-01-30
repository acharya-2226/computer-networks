# Lab 5 : Configuration of static routes and default routes

## Objective
- To understand the concepts of static routing and default routing.
- To learn how to configure static routes and default routes on network devices using UI and CLI.

## Theory
- Static Routing: Static routing is a method of routing where the network administrator manually configures the routing table on each router. Static routes do not change unless manually updated by the administrator. They are typically used in small networks or for specific routes that require consistent paths.
- Default Routing: A default route is a special type of static route that is used when there is no specific route for a destination in the routing table. It acts as a catch-all route, directing traffic to a specified next-hop address or exit interface when no other routes match the destination IP address.
- CLI : Command Line Interface (CLI) is a text-based interface used to interact with network devices. It allows administrators to configure, manage, and troubleshoot network devices using commands.

## Procedure
1. In Cisco Packet Tracer, create a network topology with at least two routers and multiple networks with multiple devices.
2. Assign IP addresses to all devices and configure basic settings such as IP addresses, subnet masks, and gateways.
3. Configure static routes on each router to enable communication between different networks. Use the following command in CLI mode:
   ```
   Router(config)# ip route [destination_network] [subnet_mask] [next_hop_address or exit_interface]
   ```

   **Basic Syntax:**
   ```
   Router> enable
   Router# configure terminal
   Router(config)# ip route <destination_network> <subnet_mask> <next_hop_address>
   ```

   **Router 1 Configuration Example:**
   ```
   Router> enable
   Router# configure terminal
   Router(config)# ip route 192.168.2.0 255.255.255.0 10.0.0.2
   ```

   **Router 2 Configuration Example:**
   ```
   Router> enable
   Router# configure terminal
   Router(config)# ip route 192.168.1.0 255.255.255.0 10.0.0.1
   ```

4. Configure a default route on each router to handle traffic destined for unknown networks. Use the following command in CLI mode:
   ```
   Router(config)# ip route 0.0.0.0 0.0.0.0 <next_hop_address or exit_interface>
   ```

   **Basic Syntax:**
   ```
   Router> enable
   Router# configure terminal
   Router(config)# ip route 0.0.0.0 0.0.0.0 <next_hop_address>
   ```

   **Router 1 Configuration Example:**
   ```
   Router> enable
   Router# configure terminal
   Router(config)# ip route 0.0.0.0 0.0.0.0 10.0.0.2
   ```

   **Router 2 Configuration Example:**
   ```
   Router> enable
   Router# configure terminal
   Router(config)# ip route 0.0.0.0 0.0.0.0 10.0.0.1
   ```
5. Verify the routing configuration by sending ping requests between devices on different networks. Use the following command in CMD mode:
   ```
   ping [destination_IP_address]
   ```

## Observations
- Successful ping responses indicate that the static routes and default routes are correctly configured, allowing communication between different networks.

## Conclusion
- In this lab, we learned how to configure static routes and default routes on network devices using CLI. We understood the importance of static routing for specific network paths and default routing for handling unknown destinations. Proper configuration of these routes is essential for efficient network communication and management.

