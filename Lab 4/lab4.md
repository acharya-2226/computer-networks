<!-- Subnetting and Supernetting -->
# Lab 4: Subnetting and Supernetting

Subnet Table

Initial IP Address: 192.168.1.0/24
Required Subnets: 4
Host Bits : 6

| Subnet Number | Subnet Mask     | First Usable IP    | Last Usable IP      | Broadcast Address | Network Address |
|---------------|-----------------|--------------------|--------------------|-------------------|-----------------|
| 1             | 255.255.255.192 | 192.168.1.1/26     | 192.168.1.62/26    | 192.168.1.63      | 192.168.1.0     |
| 2             | 255.255.255.192 | 192.168.1.65/26    | 192.168.1.126/26   | 192.168.1.127     | 192.168.1.64    |
| 3             | 255.255.255.192 | 192.168.1.129/26   | 192.168.1.190/26   | 192.168.1.191     | 192.168.1.128   |
| 4             | 255.255.255.192 | 192.168.1.193/26   | 192.168.1.254/26   | 192.168.1.255     | 192.168.1.192   |


Criterias for Supernetting

Network Addresses must be contiguous.
The number of networks to be combined must be a power of 2 (i.e., 2, 4, 8, 16, etc.).

Supernet: 

Device IP | Subnet Mask 
192.168.1.10|255.255.252.0
192.168.2.10|255.255.252.0
192.168.3.10|255.255.252.0
192.168.4.10|255.255.252.0

| Supernet Address | Supernet Mask   | First Usable IP    | Last Usable IP     | Broadcast Address  | Network Address  |
|------------------|-----------------|--------------------|--------------------|--------------------|------------------|
|192.168.1.1|255.255.255.192|