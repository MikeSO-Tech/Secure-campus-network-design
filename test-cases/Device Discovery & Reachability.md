# Device Discovery & Reachability

## Purpose
Validate inter-VLAN connectivity for internal networks and confirm
Guest VLAN isolation with permitted external access.

## Environment
- VLAN 10 – Internal Users (Worker1)
- VLAN 20 – Factory Systems (Machine PC)
- VLAN 40 – Guest (LT Laptop)
- VLAN 50 – Internal Servers

## Validation Method
ICMP testing (ping) between VLANs after verifying correct IP assignment.

## Expected Results
| Source VLAN | Destination | Result |
|------------|-------------|--------|
| 10 | 20 | PASS |
| 10 | 50 | PASS |
| 40 | 10 | BLOCKED |
| 40 | 20 | BLOCKED |
| 40 | 50 | BLOCKED |
| 40 | ISP Server | PASS |

## Test Steps
1. Verify IP with `ipconfig`
2. Ping target devices
3. Capture results

## Evidence
### VLAN 20 → VLAN 50 (PASS)

### VLAN 40 → VLAN 10 (BLOCKED)


### VLAN 40 → ISP Server (PASS)


## Outcome
**PASS** – Segmentation and ACL enforcement operate as designed.