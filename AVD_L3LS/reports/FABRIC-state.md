
# Validate State Report

**Table of Contents:**

- [Validate State Report](validate-state-report)
  - [Test Results Summary](#test-results-summary)
  - [Failed Test Results Summary](#failed-test-results-summary)
  - [All Test Results](#all-test-results)

## Test Results Summary

### Summary Totals

| Total Tests | Total Tests Passed | Total Tests Failed |
| ----------- | ------------------ | ------------------ |
| 252 | 220 | 32 |

### Summary Totals Devices Under Tests

| DUT | Total Tests | Tests Passed | Tests Failed | Categories Failed |
| --- | ----------- | ------------ | ------------ | ----------------- |
| leaf1 |  48 | 43 | 5 | Interface State, LLDP Topology, BGP, Routing Table, Loopback0 Reachability |
| leaf2 |  48 | 43 | 5 | Interface State, LLDP Topology, BGP, Routing Table, Loopback0 Reachability |
| leaf3 |  48 | 43 | 5 | Interface State, LLDP Topology, BGP, Routing Table, Loopback0 Reachability |
| leaf4 |  48 | 43 | 5 | Interface State, LLDP Topology, BGP, Routing Table, Loopback0 Reachability |
| spine1 |  15 | 15 | 0 | - |
| spine2 |  15 | 15 | 0 | - |
| spine3 |  15 | 15 | 0 | - |
| spine4 |  15 | 3 | 12 | Interface State, LLDP Topology, BGP |

### Summary Totals Per Category

| Test Category | Total Tests | Tests Passed | Tests Failed |
| ------------- | ----------- | ------------ | ------------ |
| NTP |  8 | 8 | 0 |
| Interface State |  88 | 80 | 8 |
| LLDP Topology |  40 | 32 | 8 |
| MLAG |  4 | 4 | 0 |
| BGP |  40 | 32 | 8 |
| Routing Table |  40 | 36 | 4 |
| Loopback0 Reachability |  32 | 28 | 4 |

## Failed Test Results Summary

| Test ID | Node | Test Category | Test Description | Test | Test Result | Failure Reason |
| ------- | ---- | ------------- | ---------------- | ---- | ----------- | -------------- |
| 14 | leaf1 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet6 - P2P_LINK_TO_SPINE4_Ethernet3 | FAIL | Interface shutdown: False - interface status: down - line protocol status: down |
| 21 | leaf2 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet6 - P2P_LINK_TO_SPINE4_Ethernet4 | FAIL | Interface shutdown: False - interface status: down - line protocol status: down |
| 28 | leaf3 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet6 - P2P_LINK_TO_SPINE4_Ethernet5 | FAIL | Interface shutdown: False - interface status: down - line protocol status: down |
| 35 | leaf4 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet6 - P2P_LINK_TO_SPINE4_Ethernet6 | FAIL | Interface shutdown: False - interface status: down - line protocol status: down |
| 49 | spine4 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet3 - P2P_LINK_TO_LEAF1_Ethernet6 | FAIL | Interface shutdown: False - interface status: adminDown - line protocol status: down |
| 50 | spine4 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet4 - P2P_LINK_TO_LEAF2_Ethernet6 | FAIL | Interface shutdown: False - interface status: adminDown - line protocol status: down |
| 51 | spine4 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet5 - P2P_LINK_TO_LEAF3_Ethernet6 | FAIL | Interface shutdown: False - interface status: adminDown - line protocol status: down |
| 52 | spine4 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet6 - P2P_LINK_TO_LEAF4_Ethernet6 | FAIL | Interface shutdown: False - interface status: adminDown - line protocol status: down |
| 102 | leaf1 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet6 - remote: spine4_Ethernet3 | FAIL | Interface Down - N/A |
| 108 | leaf2 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet6 - remote: spine4_Ethernet4 | FAIL | Interface Down - N/A |
| 114 | leaf3 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet6 - remote: spine4_Ethernet5 | FAIL | Interface Down - N/A |
| 120 | leaf4 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet6 - remote: spine4_Ethernet6 | FAIL | Interface Down - N/A |
| 133 | spine4 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet3 - remote: leaf1_Ethernet6 | FAIL | Interface Down - N/A |
| 134 | spine4 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet4 - remote: leaf2_Ethernet6 | FAIL | Interface Down - N/A |
| 135 | spine4 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet5 - remote: leaf3_Ethernet6 | FAIL | Interface Down - N/A |
| 136 | spine4 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet6 - remote: leaf4_Ethernet6 | FAIL | Interface Down - N/A |
| 152 | leaf1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.14 | FAIL | Session state: Active |
| 156 | leaf2 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.14 | FAIL | Session state: Active |
| 160 | leaf3 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.14 | FAIL | Session state: Active |
| 164 | leaf4 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.14 | FAIL | Session state: Active |
| 177 | spine4 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.1 | FAIL | Session state: Active |
| 178 | spine4 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.2 | FAIL | Session state: Active |
| 179 | spine4 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.3 | FAIL | Session state: Active |
| 180 | spine4 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.4 | FAIL | Session state: Active |
| 196 | leaf1 | Routing Table | Remote Lo0 address | 192.168.101.14 | FAIL | Lo0 192.168.101.14 is not in the routing table |
| 204 | leaf2 | Routing Table | Remote Lo0 address | 192.168.101.14 | FAIL | Lo0 192.168.101.14 is not in the routing table |
| 212 | leaf3 | Routing Table | Remote Lo0 address | 192.168.101.14 | FAIL | Lo0 192.168.101.14 is not in the routing table |
| 220 | leaf4 | Routing Table | Remote Lo0 address | 192.168.101.14 | FAIL | Lo0 192.168.101.14 is not in the routing table |
| 228 | leaf1 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf1 - 192.168.101.1 Destination: 192.168.101.14 | FAIL | 100% packet loss |
| 236 | leaf2 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf2 - 192.168.101.2 Destination: 192.168.101.14 | FAIL | 100% packet loss |
| 244 | leaf3 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf3 - 192.168.101.3 Destination: 192.168.101.14 | FAIL | 100% packet loss |
| 252 | leaf4 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf4 - 192.168.101.4 Destination: 192.168.101.14 | FAIL | 100% packet loss |

## All Test Results

| Test ID | Node | Test Category | Test Description | Test | Test Result | Failure Reason |
| ------- | ---- | ------------- | ---------------- | ---- | ----------- | -------------- |
| 1 | leaf1 | NTP | Synchronised with NTP server | NTP | PASS | - |
| 2 | leaf2 | NTP | Synchronised with NTP server | NTP | PASS | - |
| 3 | leaf3 | NTP | Synchronised with NTP server | NTP | PASS | - |
| 4 | leaf4 | NTP | Synchronised with NTP server | NTP | PASS | - |
| 5 | spine1 | NTP | Synchronised with NTP server | NTP | PASS | - |
| 6 | spine2 | NTP | Synchronised with NTP server | NTP | PASS | - |
| 7 | spine3 | NTP | Synchronised with NTP server | NTP | PASS | - |
| 8 | spine4 | NTP | Synchronised with NTP server | NTP | PASS | - |
| 9 | leaf1 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet1 - MLAG_PEER_leaf2_Ethernet1 | PASS | - |
| 10 | leaf1 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet2 - MLAG_PEER_leaf2_Ethernet2 | PASS | - |
| 11 | leaf1 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet3 - P2P_LINK_TO_SPINE1_Ethernet3 | PASS | - |
| 12 | leaf1 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet4 - P2P_LINK_TO_SPINE2_Ethernet3 | PASS | - |
| 13 | leaf1 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet5 - P2P_LINK_TO_SPINE3_Ethernet3 | PASS | - |
| 14 | leaf1 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet6 - P2P_LINK_TO_SPINE4_Ethernet3 | FAIL | Interface shutdown: False - interface status: down - line protocol status: down |
| 15 | leaf1 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet7 - host1_Ethernet1 | PASS | - |
| 16 | leaf2 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet1 - MLAG_PEER_leaf1_Ethernet1 | PASS | - |
| 17 | leaf2 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet2 - MLAG_PEER_leaf1_Ethernet2 | PASS | - |
| 18 | leaf2 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet3 - P2P_LINK_TO_SPINE1_Ethernet4 | PASS | - |
| 19 | leaf2 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet4 - P2P_LINK_TO_SPINE2_Ethernet4 | PASS | - |
| 20 | leaf2 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet5 - P2P_LINK_TO_SPINE3_Ethernet4 | PASS | - |
| 21 | leaf2 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet6 - P2P_LINK_TO_SPINE4_Ethernet4 | FAIL | Interface shutdown: False - interface status: down - line protocol status: down |
| 22 | leaf2 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet7 - host1_Ethernet2 | PASS | - |
| 23 | leaf3 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet1 - MLAG_PEER_leaf4_Ethernet1 | PASS | - |
| 24 | leaf3 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet2 - MLAG_PEER_leaf4_Ethernet2 | PASS | - |
| 25 | leaf3 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet3 - P2P_LINK_TO_SPINE1_Ethernet5 | PASS | - |
| 26 | leaf3 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet4 - P2P_LINK_TO_SPINE2_Ethernet5 | PASS | - |
| 27 | leaf3 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet5 - P2P_LINK_TO_SPINE3_Ethernet5 | PASS | - |
| 28 | leaf3 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet6 - P2P_LINK_TO_SPINE4_Ethernet5 | FAIL | Interface shutdown: False - interface status: down - line protocol status: down |
| 29 | leaf3 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet7 - host3_Ethernet1 | PASS | - |
| 30 | leaf4 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet1 - MLAG_PEER_leaf3_Ethernet1 | PASS | - |
| 31 | leaf4 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet2 - MLAG_PEER_leaf3_Ethernet2 | PASS | - |
| 32 | leaf4 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet3 - P2P_LINK_TO_SPINE1_Ethernet6 | PASS | - |
| 33 | leaf4 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet4 - P2P_LINK_TO_SPINE2_Ethernet6 | PASS | - |
| 34 | leaf4 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet5 - P2P_LINK_TO_SPINE3_Ethernet6 | PASS | - |
| 35 | leaf4 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet6 - P2P_LINK_TO_SPINE4_Ethernet6 | FAIL | Interface shutdown: False - interface status: down - line protocol status: down |
| 36 | leaf4 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet7 - host3_Ethernet2 | PASS | - |
| 37 | spine1 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet3 - P2P_LINK_TO_LEAF1_Ethernet3 | PASS | - |
| 38 | spine1 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet4 - P2P_LINK_TO_LEAF2_Ethernet3 | PASS | - |
| 39 | spine1 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet5 - P2P_LINK_TO_LEAF3_Ethernet3 | PASS | - |
| 40 | spine1 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet6 - P2P_LINK_TO_LEAF4_Ethernet3 | PASS | - |
| 41 | spine2 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet3 - P2P_LINK_TO_LEAF1_Ethernet4 | PASS | - |
| 42 | spine2 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet4 - P2P_LINK_TO_LEAF2_Ethernet4 | PASS | - |
| 43 | spine2 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet5 - P2P_LINK_TO_LEAF3_Ethernet4 | PASS | - |
| 44 | spine2 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet6 - P2P_LINK_TO_LEAF4_Ethernet4 | PASS | - |
| 45 | spine3 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet3 - P2P_LINK_TO_LEAF1_Ethernet5 | PASS | - |
| 46 | spine3 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet4 - P2P_LINK_TO_LEAF2_Ethernet5 | PASS | - |
| 47 | spine3 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet5 - P2P_LINK_TO_LEAF3_Ethernet5 | PASS | - |
| 48 | spine3 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet6 - P2P_LINK_TO_LEAF4_Ethernet5 | PASS | - |
| 49 | spine4 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet3 - P2P_LINK_TO_LEAF1_Ethernet6 | FAIL | Interface shutdown: False - interface status: adminDown - line protocol status: down |
| 50 | spine4 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet4 - P2P_LINK_TO_LEAF2_Ethernet6 | FAIL | Interface shutdown: False - interface status: adminDown - line protocol status: down |
| 51 | spine4 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet5 - P2P_LINK_TO_LEAF3_Ethernet6 | FAIL | Interface shutdown: False - interface status: adminDown - line protocol status: down |
| 52 | spine4 | Interface State | Ethernet Interface & Line Protocol == "up" | Ethernet6 - P2P_LINK_TO_LEAF4_Ethernet6 | FAIL | Interface shutdown: False - interface status: adminDown - line protocol status: down |
| 53 | leaf1 | Interface State | Port-Channel Interface & Line Protocol == "up" | Port-Channel1 - MLAG_PEER_leaf2_Po1 | PASS | - |
| 54 | leaf1 | Interface State | Port-Channel Interface & Line Protocol == "up" | Port-Channel7 - host1_PortChannel host1 | PASS | - |
| 55 | leaf2 | Interface State | Port-Channel Interface & Line Protocol == "up" | Port-Channel1 - MLAG_PEER_leaf1_Po1 | PASS | - |
| 56 | leaf2 | Interface State | Port-Channel Interface & Line Protocol == "up" | Port-Channel7 - host1_PortChannel host1 | PASS | - |
| 57 | leaf3 | Interface State | Port-Channel Interface & Line Protocol == "up" | Port-Channel1 - MLAG_PEER_leaf4_Po1 | PASS | - |
| 58 | leaf3 | Interface State | Port-Channel Interface & Line Protocol == "up" | Port-Channel7 - host3_PortChannel host3 | PASS | - |
| 59 | leaf4 | Interface State | Port-Channel Interface & Line Protocol == "up" | Port-Channel1 - MLAG_PEER_leaf3_Po1 | PASS | - |
| 60 | leaf4 | Interface State | Port-Channel Interface & Line Protocol == "up" | Port-Channel7 - host3_PortChannel host3 | PASS | - |
| 61 | leaf1 | Interface State | Vlan Interface & Line Protocol == "up" | Vlan4093 - MLAG_PEER_L3_PEERING | PASS | - |
| 62 | leaf1 | Interface State | Vlan Interface & Line Protocol == "up" | Vlan4094 - MLAG_PEER | PASS | - |
| 63 | leaf1 | Interface State | Vlan Interface & Line Protocol == "up" | Vlan10 - DMZ | PASS | - |
| 64 | leaf1 | Interface State | Vlan Interface & Line Protocol == "up" | Vlan20 - Internal | PASS | - |
| 65 | leaf1 | Interface State | Vlan Interface & Line Protocol == "up" | Vlan3009 - MLAG_PEER_L3_iBGP: vrf VRF_A | PASS | - |
| 66 | leaf2 | Interface State | Vlan Interface & Line Protocol == "up" | Vlan4093 - MLAG_PEER_L3_PEERING | PASS | - |
| 67 | leaf2 | Interface State | Vlan Interface & Line Protocol == "up" | Vlan4094 - MLAG_PEER | PASS | - |
| 68 | leaf2 | Interface State | Vlan Interface & Line Protocol == "up" | Vlan10 - DMZ | PASS | - |
| 69 | leaf2 | Interface State | Vlan Interface & Line Protocol == "up" | Vlan20 - Internal | PASS | - |
| 70 | leaf2 | Interface State | Vlan Interface & Line Protocol == "up" | Vlan3009 - MLAG_PEER_L3_iBGP: vrf VRF_A | PASS | - |
| 71 | leaf3 | Interface State | Vlan Interface & Line Protocol == "up" | Vlan4093 - MLAG_PEER_L3_PEERING | PASS | - |
| 72 | leaf3 | Interface State | Vlan Interface & Line Protocol == "up" | Vlan4094 - MLAG_PEER | PASS | - |
| 73 | leaf3 | Interface State | Vlan Interface & Line Protocol == "up" | Vlan10 - DMZ | PASS | - |
| 74 | leaf3 | Interface State | Vlan Interface & Line Protocol == "up" | Vlan20 - Internal | PASS | - |
| 75 | leaf3 | Interface State | Vlan Interface & Line Protocol == "up" | Vlan3009 - MLAG_PEER_L3_iBGP: vrf VRF_A | PASS | - |
| 76 | leaf4 | Interface State | Vlan Interface & Line Protocol == "up" | Vlan4093 - MLAG_PEER_L3_PEERING | PASS | - |
| 77 | leaf4 | Interface State | Vlan Interface & Line Protocol == "up" | Vlan4094 - MLAG_PEER | PASS | - |
| 78 | leaf4 | Interface State | Vlan Interface & Line Protocol == "up" | Vlan10 - DMZ | PASS | - |
| 79 | leaf4 | Interface State | Vlan Interface & Line Protocol == "up" | Vlan20 - Internal | PASS | - |
| 80 | leaf4 | Interface State | Vlan Interface & Line Protocol == "up" | Vlan3009 - MLAG_PEER_L3_iBGP: vrf VRF_A | PASS | - |
| 81 | leaf1 | Interface State | Vxlan Interface Status & Line Protocol == "up" | Vxlan1 | PASS | - |
| 82 | leaf2 | Interface State | Vxlan Interface Status & Line Protocol == "up" | Vxlan1 | PASS | - |
| 83 | leaf3 | Interface State | Vxlan Interface Status & Line Protocol == "up" | Vxlan1 | PASS | - |
| 84 | leaf4 | Interface State | Vxlan Interface Status & Line Protocol == "up" | Vxlan1 | PASS | - |
| 85 | leaf1 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback0 - EVPN_Overlay_Peering | PASS | - |
| 86 | leaf1 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback1 - VTEP_VXLAN_Tunnel_Source | PASS | - |
| 87 | leaf2 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback0 - EVPN_Overlay_Peering | PASS | - |
| 88 | leaf2 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback1 - VTEP_VXLAN_Tunnel_Source | PASS | - |
| 89 | leaf3 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback0 - EVPN_Overlay_Peering | PASS | - |
| 90 | leaf3 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback1 - VTEP_VXLAN_Tunnel_Source | PASS | - |
| 91 | leaf4 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback0 - EVPN_Overlay_Peering | PASS | - |
| 92 | leaf4 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback1 - VTEP_VXLAN_Tunnel_Source | PASS | - |
| 93 | spine1 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback0 - EVPN_Overlay_Peering | PASS | - |
| 94 | spine2 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback0 - EVPN_Overlay_Peering | PASS | - |
| 95 | spine3 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback0 - EVPN_Overlay_Peering | PASS | - |
| 96 | spine4 | Interface State | Loopback Interface Status & Line Protocol == "up" | Loopback0 - EVPN_Overlay_Peering | PASS | - |
| 97 | leaf1 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet1 - remote: leaf2_Ethernet1 | PASS | - |
| 98 | leaf1 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet2 - remote: leaf2_Ethernet2 | PASS | - |
| 99 | leaf1 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet3 - remote: spine1_Ethernet3 | PASS | - |
| 100 | leaf1 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet4 - remote: spine2_Ethernet3 | PASS | - |
| 101 | leaf1 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet5 - remote: spine3_Ethernet3 | PASS | - |
| 102 | leaf1 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet6 - remote: spine4_Ethernet3 | FAIL | Interface Down - N/A |
| 103 | leaf2 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet1 - remote: leaf1_Ethernet1 | PASS | - |
| 104 | leaf2 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet2 - remote: leaf1_Ethernet2 | PASS | - |
| 105 | leaf2 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet3 - remote: spine1_Ethernet4 | PASS | - |
| 106 | leaf2 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet4 - remote: spine2_Ethernet4 | PASS | - |
| 107 | leaf2 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet5 - remote: spine3_Ethernet4 | PASS | - |
| 108 | leaf2 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet6 - remote: spine4_Ethernet4 | FAIL | Interface Down - N/A |
| 109 | leaf3 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet1 - remote: leaf4_Ethernet1 | PASS | - |
| 110 | leaf3 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet2 - remote: leaf4_Ethernet2 | PASS | - |
| 111 | leaf3 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet3 - remote: spine1_Ethernet5 | PASS | - |
| 112 | leaf3 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet4 - remote: spine2_Ethernet5 | PASS | - |
| 113 | leaf3 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet5 - remote: spine3_Ethernet5 | PASS | - |
| 114 | leaf3 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet6 - remote: spine4_Ethernet5 | FAIL | Interface Down - N/A |
| 115 | leaf4 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet1 - remote: leaf3_Ethernet1 | PASS | - |
| 116 | leaf4 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet2 - remote: leaf3_Ethernet2 | PASS | - |
| 117 | leaf4 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet3 - remote: spine1_Ethernet6 | PASS | - |
| 118 | leaf4 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet4 - remote: spine2_Ethernet6 | PASS | - |
| 119 | leaf4 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet5 - remote: spine3_Ethernet6 | PASS | - |
| 120 | leaf4 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet6 - remote: spine4_Ethernet6 | FAIL | Interface Down - N/A |
| 121 | spine1 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet3 - remote: leaf1_Ethernet3 | PASS | - |
| 122 | spine1 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet4 - remote: leaf2_Ethernet3 | PASS | - |
| 123 | spine1 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet5 - remote: leaf3_Ethernet3 | PASS | - |
| 124 | spine1 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet6 - remote: leaf4_Ethernet3 | PASS | - |
| 125 | spine2 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet3 - remote: leaf1_Ethernet4 | PASS | - |
| 126 | spine2 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet4 - remote: leaf2_Ethernet4 | PASS | - |
| 127 | spine2 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet5 - remote: leaf3_Ethernet4 | PASS | - |
| 128 | spine2 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet6 - remote: leaf4_Ethernet4 | PASS | - |
| 129 | spine3 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet3 - remote: leaf1_Ethernet5 | PASS | - |
| 130 | spine3 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet4 - remote: leaf2_Ethernet5 | PASS | - |
| 131 | spine3 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet5 - remote: leaf3_Ethernet5 | PASS | - |
| 132 | spine3 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet6 - remote: leaf4_Ethernet5 | PASS | - |
| 133 | spine4 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet3 - remote: leaf1_Ethernet6 | FAIL | Interface Down - N/A |
| 134 | spine4 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet4 - remote: leaf2_Ethernet6 | FAIL | Interface Down - N/A |
| 135 | spine4 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet5 - remote: leaf3_Ethernet6 | FAIL | Interface Down - N/A |
| 136 | spine4 | LLDP Topology | LLDP topology - validate peer and interface | local: Ethernet6 - remote: leaf4_Ethernet6 | FAIL | Interface Down - N/A |
| 137 | leaf1 | MLAG | MLAG State active & Status connected | MLAG | PASS | - |
| 138 | leaf2 | MLAG | MLAG State active & Status connected | MLAG | PASS | - |
| 139 | leaf3 | MLAG | MLAG State active & Status connected | MLAG | PASS | - |
| 140 | leaf4 | MLAG | MLAG State active & Status connected | MLAG | PASS | - |
| 141 | leaf1 | BGP | ArBGP is configured and operating | ArBGP | PASS | - |
| 142 | leaf2 | BGP | ArBGP is configured and operating | ArBGP | PASS | - |
| 143 | leaf3 | BGP | ArBGP is configured and operating | ArBGP | PASS | - |
| 144 | leaf4 | BGP | ArBGP is configured and operating | ArBGP | PASS | - |
| 145 | spine1 | BGP | ArBGP is configured and operating | ArBGP | PASS | - |
| 146 | spine2 | BGP | ArBGP is configured and operating | ArBGP | PASS | - |
| 147 | spine3 | BGP | ArBGP is configured and operating | ArBGP | PASS | - |
| 148 | spine4 | BGP | ArBGP is configured and operating | ArBGP | PASS | - |
| 149 | leaf1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.11 | PASS | - |
| 150 | leaf1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.12 | PASS | - |
| 151 | leaf1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.13 | PASS | - |
| 152 | leaf1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.14 | FAIL | Session state: Active |
| 153 | leaf2 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.11 | PASS | - |
| 154 | leaf2 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.12 | PASS | - |
| 155 | leaf2 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.13 | PASS | - |
| 156 | leaf2 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.14 | FAIL | Session state: Active |
| 157 | leaf3 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.11 | PASS | - |
| 158 | leaf3 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.12 | PASS | - |
| 159 | leaf3 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.13 | PASS | - |
| 160 | leaf3 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.14 | FAIL | Session state: Active |
| 161 | leaf4 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.11 | PASS | - |
| 162 | leaf4 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.12 | PASS | - |
| 163 | leaf4 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.13 | PASS | - |
| 164 | leaf4 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.14 | FAIL | Session state: Active |
| 165 | spine1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.1 | PASS | - |
| 166 | spine1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.2 | PASS | - |
| 167 | spine1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.3 | PASS | - |
| 168 | spine1 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.4 | PASS | - |
| 169 | spine2 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.1 | PASS | - |
| 170 | spine2 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.2 | PASS | - |
| 171 | spine2 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.3 | PASS | - |
| 172 | spine2 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.4 | PASS | - |
| 173 | spine3 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.1 | PASS | - |
| 174 | spine3 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.2 | PASS | - |
| 175 | spine3 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.3 | PASS | - |
| 176 | spine3 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.4 | PASS | - |
| 177 | spine4 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.1 | FAIL | Session state: Active |
| 178 | spine4 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.2 | FAIL | Session state: Active |
| 179 | spine4 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.3 | FAIL | Session state: Active |
| 180 | spine4 | BGP | bgp evpn peer state established (evpn) | bgp_neighbor: 192.168.101.4 | FAIL | Session state: Active |
| 181 | leaf1 | Routing Table | Remote VTEP address | 192.168.102.1 | PASS | - |
| 182 | leaf1 | Routing Table | Remote VTEP address | 192.168.102.3 | PASS | - |
| 183 | leaf2 | Routing Table | Remote VTEP address | 192.168.102.1 | PASS | - |
| 184 | leaf2 | Routing Table | Remote VTEP address | 192.168.102.3 | PASS | - |
| 185 | leaf3 | Routing Table | Remote VTEP address | 192.168.102.1 | PASS | - |
| 186 | leaf3 | Routing Table | Remote VTEP address | 192.168.102.3 | PASS | - |
| 187 | leaf4 | Routing Table | Remote VTEP address | 192.168.102.1 | PASS | - |
| 188 | leaf4 | Routing Table | Remote VTEP address | 192.168.102.3 | PASS | - |
| 189 | leaf1 | Routing Table | Remote Lo0 address | 192.168.101.1 | PASS | - |
| 190 | leaf1 | Routing Table | Remote Lo0 address | 192.168.101.2 | PASS | - |
| 191 | leaf1 | Routing Table | Remote Lo0 address | 192.168.101.3 | PASS | - |
| 192 | leaf1 | Routing Table | Remote Lo0 address | 192.168.101.4 | PASS | - |
| 193 | leaf1 | Routing Table | Remote Lo0 address | 192.168.101.11 | PASS | - |
| 194 | leaf1 | Routing Table | Remote Lo0 address | 192.168.101.12 | PASS | - |
| 195 | leaf1 | Routing Table | Remote Lo0 address | 192.168.101.13 | PASS | - |
| 196 | leaf1 | Routing Table | Remote Lo0 address | 192.168.101.14 | FAIL | Lo0 192.168.101.14 is not in the routing table |
| 197 | leaf2 | Routing Table | Remote Lo0 address | 192.168.101.1 | PASS | - |
| 198 | leaf2 | Routing Table | Remote Lo0 address | 192.168.101.2 | PASS | - |
| 199 | leaf2 | Routing Table | Remote Lo0 address | 192.168.101.3 | PASS | - |
| 200 | leaf2 | Routing Table | Remote Lo0 address | 192.168.101.4 | PASS | - |
| 201 | leaf2 | Routing Table | Remote Lo0 address | 192.168.101.11 | PASS | - |
| 202 | leaf2 | Routing Table | Remote Lo0 address | 192.168.101.12 | PASS | - |
| 203 | leaf2 | Routing Table | Remote Lo0 address | 192.168.101.13 | PASS | - |
| 204 | leaf2 | Routing Table | Remote Lo0 address | 192.168.101.14 | FAIL | Lo0 192.168.101.14 is not in the routing table |
| 205 | leaf3 | Routing Table | Remote Lo0 address | 192.168.101.1 | PASS | - |
| 206 | leaf3 | Routing Table | Remote Lo0 address | 192.168.101.2 | PASS | - |
| 207 | leaf3 | Routing Table | Remote Lo0 address | 192.168.101.3 | PASS | - |
| 208 | leaf3 | Routing Table | Remote Lo0 address | 192.168.101.4 | PASS | - |
| 209 | leaf3 | Routing Table | Remote Lo0 address | 192.168.101.11 | PASS | - |
| 210 | leaf3 | Routing Table | Remote Lo0 address | 192.168.101.12 | PASS | - |
| 211 | leaf3 | Routing Table | Remote Lo0 address | 192.168.101.13 | PASS | - |
| 212 | leaf3 | Routing Table | Remote Lo0 address | 192.168.101.14 | FAIL | Lo0 192.168.101.14 is not in the routing table |
| 213 | leaf4 | Routing Table | Remote Lo0 address | 192.168.101.1 | PASS | - |
| 214 | leaf4 | Routing Table | Remote Lo0 address | 192.168.101.2 | PASS | - |
| 215 | leaf4 | Routing Table | Remote Lo0 address | 192.168.101.3 | PASS | - |
| 216 | leaf4 | Routing Table | Remote Lo0 address | 192.168.101.4 | PASS | - |
| 217 | leaf4 | Routing Table | Remote Lo0 address | 192.168.101.11 | PASS | - |
| 218 | leaf4 | Routing Table | Remote Lo0 address | 192.168.101.12 | PASS | - |
| 219 | leaf4 | Routing Table | Remote Lo0 address | 192.168.101.13 | PASS | - |
| 220 | leaf4 | Routing Table | Remote Lo0 address | 192.168.101.14 | FAIL | Lo0 192.168.101.14 is not in the routing table |
| 221 | leaf1 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf1 - 192.168.101.1 Destination: 192.168.101.1 | PASS | - |
| 222 | leaf1 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf1 - 192.168.101.1 Destination: 192.168.101.2 | PASS | - |
| 223 | leaf1 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf1 - 192.168.101.1 Destination: 192.168.101.3 | PASS | - |
| 224 | leaf1 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf1 - 192.168.101.1 Destination: 192.168.101.4 | PASS | - |
| 225 | leaf1 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf1 - 192.168.101.1 Destination: 192.168.101.11 | PASS | - |
| 226 | leaf1 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf1 - 192.168.101.1 Destination: 192.168.101.12 | PASS | - |
| 227 | leaf1 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf1 - 192.168.101.1 Destination: 192.168.101.13 | PASS | - |
| 228 | leaf1 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf1 - 192.168.101.1 Destination: 192.168.101.14 | FAIL | 100% packet loss |
| 229 | leaf2 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf2 - 192.168.101.2 Destination: 192.168.101.1 | PASS | - |
| 230 | leaf2 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf2 - 192.168.101.2 Destination: 192.168.101.2 | PASS | - |
| 231 | leaf2 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf2 - 192.168.101.2 Destination: 192.168.101.3 | PASS | - |
| 232 | leaf2 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf2 - 192.168.101.2 Destination: 192.168.101.4 | PASS | - |
| 233 | leaf2 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf2 - 192.168.101.2 Destination: 192.168.101.11 | PASS | - |
| 234 | leaf2 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf2 - 192.168.101.2 Destination: 192.168.101.12 | PASS | - |
| 235 | leaf2 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf2 - 192.168.101.2 Destination: 192.168.101.13 | PASS | - |
| 236 | leaf2 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf2 - 192.168.101.2 Destination: 192.168.101.14 | FAIL | 100% packet loss |
| 237 | leaf3 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf3 - 192.168.101.3 Destination: 192.168.101.1 | PASS | - |
| 238 | leaf3 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf3 - 192.168.101.3 Destination: 192.168.101.2 | PASS | - |
| 239 | leaf3 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf3 - 192.168.101.3 Destination: 192.168.101.3 | PASS | - |
| 240 | leaf3 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf3 - 192.168.101.3 Destination: 192.168.101.4 | PASS | - |
| 241 | leaf3 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf3 - 192.168.101.3 Destination: 192.168.101.11 | PASS | - |
| 242 | leaf3 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf3 - 192.168.101.3 Destination: 192.168.101.12 | PASS | - |
| 243 | leaf3 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf3 - 192.168.101.3 Destination: 192.168.101.13 | PASS | - |
| 244 | leaf3 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf3 - 192.168.101.3 Destination: 192.168.101.14 | FAIL | 100% packet loss |
| 245 | leaf4 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf4 - 192.168.101.4 Destination: 192.168.101.1 | PASS | - |
| 246 | leaf4 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf4 - 192.168.101.4 Destination: 192.168.101.2 | PASS | - |
| 247 | leaf4 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf4 - 192.168.101.4 Destination: 192.168.101.3 | PASS | - |
| 248 | leaf4 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf4 - 192.168.101.4 Destination: 192.168.101.4 | PASS | - |
| 249 | leaf4 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf4 - 192.168.101.4 Destination: 192.168.101.11 | PASS | - |
| 250 | leaf4 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf4 - 192.168.101.4 Destination: 192.168.101.12 | PASS | - |
| 251 | leaf4 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf4 - 192.168.101.4 Destination: 192.168.101.13 | PASS | - |
| 252 | leaf4 | Loopback0 Reachability | Loopback0 Reachability | Source: leaf4 - 192.168.101.4 Destination: 192.168.101.14 | FAIL | 100% packet loss |
