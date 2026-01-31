<!-- Lab 2: Network Commands for Testing and Troubleshooting -->

# Lab 2: Network Commands for Testing and Troubleshooting

## Objective:
To familiarize with essential network commands used for testing and troubleshooting network connectivity issues.

## Required Tools:
- A computer with command line interface (CLI) access
- Network connection (wired or wireless)

## Network Commands:
<!-- Used Commands: ping, ipconfig, tracert, netstat (-a,-n), nslookup, arp, telnet, netsh wlan, pathping, route print, getmac, nbtstat, whois -->

### Syntax and Usage of Common Network Commands:

1. **ping**
   - Syntax: `ping [hostname or IP address]`
   - Usage: Tests the reachability of a host on an IP network and measures the round-trip time for messages sent from the originating host to a destination computer.

2. **ipconfig (Windows) / ifconfig (Linux)**
   - Syntax: `ipconfig` or `ifconfig`
   - Usage: Displays all current TCP/IP network configuration values and refreshes DHCP and DNS settings.

3. **tracert (Windows) / traceroute (Linux)**
   - Syntax: `tracert [hostname or IP address]` or `traceroute [hostname or IP address]`
   - Usage: Determines the route taken by packets to reach a specific host by listing all the intermediate routers.

4. **netstat**
   - Syntax: `netstat -a` or `netstat -n`
   - Usage: Displays active TCP connections, ports on which the computer is listening, Ethernet statistics, and more.

5. **nslookup**
   - Syntax: `nslookup [hostname]`
   - Usage: Queries the Domain Name System (DNS) to obtain domain name or IP address mapping information.

6. **arp**
   - Syntax: `arp -a`
   - Usage: Displays and modifies the IP-to-Physical (MAC) address translation table used by the Address Resolution Protocol (ARP).

7. **telnet**
   - Syntax: `telnet [hostname or IP address] [port]`
   - Usage: Connects to a remote host using the Telnet protocol, useful for testing connectivity to specific ports.
   
8. **netsh wlan (Windows)**
   - Syntax: `netsh wlan show profiles` or `netsh wlan connect name=[profile name]`
   - Usage: Manages wireless network profiles and connections on Windows systems.

9. **pathping**
   - Syntax: `pathping [hostname or IP address]`
   - Usage: Combines the functionality of ping and tracert to provide information about network latency and packet loss at each hop.

10. **route print**
    - Syntax: `route print`
    - Usage: Displays the current IP routing table on the local machine.

11. **getmac**
    - Syntax: `getmac`
    - Usage: Displays the MAC addresses for network adapters on the local machine.

12. **nbtstat**
    - Syntax: `nbtstat -a [hostname]`
    - Usage: Displays NetBIOS over TCP/IP statistics, including the NetBIOS name table of a remote computer.

13. **whois**
    - Syntax: `whois [domain name]`
    - Usage: Retrieves registration information about a domain name from the WHOIS database.

## Procedure:
1. Open the command line interface (CLI) on your computer.
2. Use the `ipconfig` or `ifconfig` command to check your current network configuration.
3. Usage of the commands are shown in the output files.

## Output:
<!-- Format of Table 3*3
 <table>
   <tr>
      <td align="center">
         <img src="path/to/image" alt="Image Description" width="180" />
         <br />Fig: Image Description
      </td>
      <td align="center">
         <img src="path/to/image" alt="Image Description" width="180" />
         <br />Fig: Image Description
      </td>
      <td align="center">
         <img src="path/to/image" alt="Image Description" width="180" />
         <br />Fig: Image Description
   </tr>
</table>
 -->

- ![GETMAC Command Output](outputs/getmac.png "GETMAC Command Output") Fig : GETMAC Command Output

- ![IPCONFIG Command Output](outputs/ipconfig.png "IPCONFIG Command Output") Fig : IPCONFIG Command Output

- ![NETSH Command Output](outputs/netsh.png "NETSH Command Output") Fig : NETSH Command Output

- ![NETSTAT -A Command Output](outputs/netstat-a.png "NETSTAT -A Command Output") Fig : NETSTAT -A Command Output

- ![NETSTAT -N Command Output](outputs/netstat-n.png "NETSTAT -N Command Output") Fig : NETSTAT -N Command Output

- ![NSLOOKUP Command Output](outputs/nslookup.png "NSLOOKUP Command Output") Fig : NSLOOKUP Command Output

- ![PATHPING Command Output](outputs/pathping.png "PATHPING Command Output") Fig : PATHPING Command Output

- ![PING Command Output](outputs/ping.png "PING Command Output") Fig : PING Command Output

- ![ROUTE PRINT Command Output](outputs/routeprint.png "ROUTE PRINT Command Output") Fig : ROUTE PRINT Command Output

- ![TELNET Command Output](outputs/telnet.png "TELNET Command Output") Fig : TELNET Command Output

- ![TRACERT Command Output](outputs/tracert.png "TRACERT Command Output") Fig : TRACERT Command Output

- ![UNRECOGNIZED Command Output](outputs/unrecognized.png "UNRECOGNIZED Command Output") Fig : UNRECOGNIZED Command Output


## Conclusion:
This lab provided hands-on experience with various network commands essential for diagnosing and troubleshooting network issues. Mastery of these commands is crucial for network administrators and IT professionals to maintain network health and performance.