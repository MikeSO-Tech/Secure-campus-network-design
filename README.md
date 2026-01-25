# Secure Campus Network Design

## Overview
This project simulates a secure enterprise campus network for a fictional
Lockheed Martin factory and office environment. The design follows a
three-tier architecture (Core, Distribution, Access) and implements
routing, segmentation, security, and WAN connectivity.

## Architecture
- Core Layer: OSPF backbone, WAN edge, GRE tunnel termination
- Distribution Layer: Inter-VLAN routing, DHCP, ACL enforcement
- Access Layer: Endpoint connectivity with port security
- WAN Edge: Simulated ISP router for site-to-site connectivity

## VLAN Segmentation
| VLAN | Name         | Purpose               |
|------|-------------|-----------------------|
| 10   | Int_Data    | Internal users        |
| 20   | Factory     | Factory systems       |
| 30   | Voice       | VoIP phones           |
| 40   | Guest       | Isolated guest access |
| 50   | Int_Server  | Internal servers      |
| 99   | MGMT        | Device management     |

## Security Controls
- Guest VLAN isolation via extended ACL
- SSH-only management
- Encrypted credentials & login blocking
- Port-security with sticky MAC
- Centralized Syslog & NTP

## Routing & WAN
- OSPF Area 0 between Core and Distribution
- Default route to ISP
- GRE tunnel between Core and ISP routers
