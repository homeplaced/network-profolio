# Project 01: pfSense VirtualBox Lab (Router/Firewall)

## Goal
Build a small lab network using pfSense in VirtualBox and validate LAN routing + management access.

## Environment
- Host OS: Windows 11
- VirtualBox: 7.x
- pfSense: (version)
- RAM/CPU: 1GB / 1 vCPU
- Storage: 20GB

## Topology
- WAN: VirtualBox NAT
- LAN: VirtualBox Host-only
- pfSense LAN IP: 192.168.10.1/24

## IP Plan
- LAN subnet: 192.168.10.0/24
- pfSense: 192.168.10.1
- DHCP scope: 192.168.10.100-192.168.10.200 (if enabled)

## Build Steps (high level)
1. Create VM, attach pfSense ISO
2. Add 2 NICs: WAN=NAT, LAN=Host-only
3. Assign interfaces in console (WAN/LAN)
4. Configure LAN IP and access Web UI

## Validation / Evidence
- Host can reach pfSense web UI at https://192.168.10.1
- Evidence: see `/evidence`
- Ubuntu LAN client received DHCP lease from pfSense
- Default gateway set to pfSense LAN IP (192.168.10.1)
- Client can reach pfSense gateway
- DNS resolution and internet connectivity verified
- Evidence screenshots located in `/evidence`

### Tests Performed
  - [x] `ping 192.168.10.1`
  - [x] Browser access to Web UI

## Issues & Fixes
- ISO access issues (Windows blocking/permissions) → moved ISO + unblocked
- ISO not attached (optical drive empty) → attached ISO under Storage

## Next Improvements
- Add Ubuntu client VM on LAN
- Enable DHCP on LAN and verify lease
- Verify DNS resolution + internet access from client
- Add guest isolation rules
- Implement and test LAN firewall rules
- Capture DHCP/DNS/TCP traffic in Wireshark and explain it
