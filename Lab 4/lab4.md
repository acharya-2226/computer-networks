# Lab 4: Subnetting and Supernetting

## Objectives:
- Understand the concepts of subnetting and supernetting.
- Learn how to divide a larger network into smaller subnets.
- Learn how to combine smaller networks into a larger supernet.

## Theory

### Subnetting

Subnetting is the process of dividing a larger IP network into smaller, more manageable sub-networks or subnets. This is done by borrowing bits from the host portion of the IP address to create additional network bits.

### Supernetting

Supernetting is the process of combining multiple smaller networks into a larger network. This is typically done by reducing the number of network bits in the subnet mask, allowing for a larger address space.

## Subnetting Example
Given an IP address of 192.168.1.0/24, we want to create 4 subnets.

### Steps to Subnet
1. Determine the number of bits needed to create the required number of subnets. For 4 subnets, we need 2 bits (2^2 = 4).
2. Calculate the new subnet mask by adding the borrowed bits to the original subnet mask. The original subnet mask is /24 (/24 + 2 = /26).
3. Calculate the number of hosts per subnet using the formula 2^h - 2, where h is the number of host bits. With a /26 subnet mask, we have 6 host bits (32 - 26 = 6), resulting in 62 hosts per subnet (2^6 - 2 = 62).
4. Determine the subnet addresses, broadcast addresses, and usable IP ranges for each subnet.

## Supernetting Example

Given the following networks:
- 192.168.1.0/24
- 192.168.2.0/24
- 192.168.3.0/24
- 192.168.4.0/24

### Steps to Supernet
1. Identify the contiguous networks to be combined.
2. Determine the new subnet mask by reducing the number of network bits.
3. Calculate the new network address and broadcast address for the supernet.

## Subnet Table

**Initial IP Address:** 192.168.1.0/24  
**Required Subnets:** 4  
**Host Bits:** 6

| Subnet Number | Subnet Mask     | First Usable IP    | Last Usable IP      | Broadcast Address | Network Address |
|---------------|-----------------|--------------------|--------------------|-------------------|-----------------|
| 1             | 255.255.255.192 | 192.168.1.1/26     | 192.168.1.62/26    | 192.168.1.63      | 192.168.1.0     |
| 2             | 255.255.255.192 | 192.168.1.65/26    | 192.168.1.126/26   | 192.168.1.127     | 192.168.1.64    |
| 3             | 255.255.255.192 | 192.168.1.129/26   | 192.168.1.190/26   | 192.168.1.191     | 192.168.1.128   |
| 4             | 255.255.255.192 | 192.168.1.193/26   | 192.168.1.254/26   | 192.168.1.255     | 192.168.1.192   |

## Criteria for Supernetting

- Network Addresses must be contiguous.
- The number of networks to be combined must be a power of 2 (i.e., 2, 4, 8, 16, etc.).

## Supernet Table

| Device IP    | Subnet Mask   |
|--------------|---------------|
| 192.168.1.10 | 255.255.252.0 |
| 192.168.2.10 | 255.255.252.0 |
| 192.168.3.10 | 255.255.252.0 |
| 192.168.4.10 | 255.255.252.0 |

**Supernet Address:**
- Network Address: 192.168.0.0/22
- Broadcast Address: 192.168.3.255
- Usable IP Range: 192.168.0.1 - 192.168.3.254

## Conclusion
Subnetting and supernetting are essential techniques in network design and management. They help optimize IP address allocation and improve network performance. Understanding these concepts is crucial for network administrators and engineers. is yet to be defined and will cover advanced networking topics.