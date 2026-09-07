# windows-network-troubleshooting

# Windows Network Troubleshooting Lab

## Overview

This project documents a Windows 11 network troubleshooting exercise performed in a home lab environment.

The objective was to verify local network connectivity, Internet connectivity, DNS resolution, DNS caching, and ARP entries using built-in Windows networking tools.

## Environment

- Operating System: Windows 11
- Network Connection: Wi-Fi
- Virtualization: VMware
- Network Type: Private home lab
- DNS: Router-based DNS forwarding

## Tools Used

- `ipconfig /all`
- `ping`
- `nslookup`
- `ipconfig /displaydns`
- `arp -a`

## Network Configuration

The workstation received its IPv4 configuration through DHCP.

Sanitized configuration:

| Parameter | Value |

| IPv4 Address         | 192.168.10.25 |
| Subnet Mask          | 255.255.255.0 |
| Default Gateway      | 192.168.10.1 |
| DNS Server           | 192.168.10.1 |
| DHCP                 | Enabled |

Sensitive information such as MAC addresses, public IPv6 addresses, and device-specific identifiers has been removed or replaced.

## Troubleshooting Process

### 1. Verify the default gateway

Command:

`ping 192.168.10.1`

Result:

- 4 packets sent
- 4 packets received
- 0% packet loss
- Average latency: approximately 2 ms

This confirmed connectivity between the workstation and the local gateway.

### 2. Verify Internet connectivity

Command:

`ping 8.8.8.8`

Result:

- 4 packets sent
- 4 packets received
- 0% packet loss
- Average latency: approximately 6 ms

This confirmed Internet connectivity using an IP address.

### 3. Verify DNS resolution

Command:

`nslookup google.com`

The DNS server successfully resolved the hostname to IPv4 and IPv6 addresses.

This confirmed that DNS name resolution was functioning correctly.

### 4. Examine the DNS cache

Command:

`ipconfig /displaydns`

The DNS cache contained records for Microsoft and other services.

The output demonstrated:

- A records
- AAAA records
- CNAME records
- TTL values

# 5. Examine the ARP table

Command:

`arp -a`

The ARP table contained mappings between local IPv4 addresses and MAC addresses.

This demonstrated how Windows resolves local IP addresses to Layer 2 MAC addresses.

# Findings

The workstation had:

- Valid DHCP configuration
- Connectivity to the default gateway
- Internet connectivity
- Working DNS resolution
- Active DNS cache entries
- Valid ARP entries
- VMware virtual network interfaces

No connectivity issue was identified during the test.

# Skills Demonstrated

- Windows network troubleshooting
- TCP/IP fundamentals
- IPv4 addressing
- DHCP
- DNS
- ARP
- Network diagnostics
- VMware networking
- Command-line troubleshooting
- Basic cybersecurity networking concepts

# Conclusion

The troubleshooting exercise confirmed that the Windows workstation had functional connectivity from the local network through the gateway and to the Internet.

The exercise also demonstrated the relationship between Layer 2 and Layer 3 networking, DNS resolution, and Windows network configuration.
