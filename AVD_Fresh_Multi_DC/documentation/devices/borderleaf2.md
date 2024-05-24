# borderleaf2

## Table of Contents

- [Management](#management)
  - [Management API HTTP](#management-api-http)
- [Spanning Tree](#spanning-tree)
  - [Spanning Tree Summary](#spanning-tree-summary)
  - [Spanning Tree Device Configuration](#spanning-tree-device-configuration)
- [Internal VLAN Allocation Policy](#internal-vlan-allocation-policy)
  - [Internal VLAN Allocation Policy Summary](#internal-vlan-allocation-policy-summary)
  - [Internal VLAN Allocation Policy Configuration](#internal-vlan-allocation-policy-configuration)
- [VLANs](#vlans)
  - [VLANs Summary](#vlans-summary)
  - [VLANs Device Configuration](#vlans-device-configuration)
- [Interfaces](#interfaces)
  - [Ethernet Interfaces](#ethernet-interfaces)
  - [Loopback Interfaces](#loopback-interfaces)
  - [VLAN Interfaces](#vlan-interfaces)
  - [VXLAN Interface](#vxlan-interface)
- [Routing](#routing)
  - [Service Routing Protocols Model](#service-routing-protocols-model)
  - [Virtual Router MAC Address](#virtual-router-mac-address)
  - [IP Routing](#ip-routing)
  - [IPv6 Routing](#ipv6-routing)
  - [Router BGP](#router-bgp)
- [BFD](#bfd)
  - [Router BFD](#router-bfd)
- [Multicast](#multicast)
  - [IP IGMP Snooping](#ip-igmp-snooping)
- [Filters](#filters)
  - [Prefix-lists](#prefix-lists)
  - [Route-maps](#route-maps)
- [VRF Instances](#vrf-instances)
  - [VRF Instances Summary](#vrf-instances-summary)
  - [VRF Instances Device Configuration](#vrf-instances-device-configuration)

## Management

### Management API HTTP

#### Management API HTTP Summary

| HTTP | HTTPS | Default Services |
| ---- | ----- | ---------------- |
| False | True | - |

#### Management API VRF Access

| VRF Name | IPv4 ACL | IPv6 ACL |
| -------- | -------- | -------- |
| MGMT | - | - |

#### Management API HTTP Configuration

```eos
!
management api http-commands
   protocol https
   no shutdown
   !
   vrf MGMT
      no shutdown
```

## Spanning Tree

### Spanning Tree Summary

STP mode: **mstp**

#### MSTP Instance and Priority

| Instance(s) | Priority |
| -------- | -------- |
| 0 | 16384 |

### Spanning Tree Device Configuration

```eos
!
spanning-tree mode mstp
spanning-tree mst 0 priority 16384
```

## Internal VLAN Allocation Policy

### Internal VLAN Allocation Policy Summary

| Policy Allocation | Range Beginning | Range Ending |
| ------------------| --------------- | ------------ |
| ascending | 1006 | 1199 |

### Internal VLAN Allocation Policy Configuration

```eos
!
vlan internal order ascending range 1006 1199
```

## VLANs

### VLANs Summary

| VLAN ID | Name | Trunk Groups |
| ------- | ---- | ------------ |
| 10 | DMZ | - |
| 20 | Internal | - |
| 30 | Test | - |

### VLANs Device Configuration

```eos
!
vlan 10
   name DMZ
!
vlan 20
   name Internal
!
vlan 30
   name Test
```

## Interfaces

### Ethernet Interfaces

#### Ethernet Interfaces Summary

##### L2

| Interface | Description | Mode | VLANs | Native VLAN | Trunk Group | Channel-Group |
| --------- | ----------- | ---- | ----- | ----------- | ----------- | ------------- |

*Inherited from Port-Channel Interface

##### IPv4

| Interface | Description | Type | Channel Group | IP Address | VRF |  MTU | Shutdown | ACL In | ACL Out |
| --------- | ----------- | -----| ------------- | ---------- | ----| ---- | -------- | ------ | ------- |
| Ethernet1 | P2P_LINK_TO_borderleaf1_Ethernet1 | routed | - | 192.168.99.1/31 | default | 1550 | False | - | - |
| Ethernet2 | P2P_LINK_TO_borderleaf1_Ethernet2 | routed | - | 192.168.99.3/31 | default | 1550 | False | - | - |
| Ethernet5 | P2P_LINK_TO_SPINE3_Ethernet8 | routed | - | 192.168.3.9/31 | default | 1550 | False | - | - |
| Ethernet6 | P2P_LINK_TO_SPINE4_Ethernet8 | routed | - | 192.168.3.11/31 | default | 1550 | False | - | - |

#### Ethernet Interfaces Device Configuration

```eos
!
interface Ethernet1
   description P2P_LINK_TO_borderleaf1_Ethernet1
   no shutdown
   mtu 1550
   no switchport
   ip address 192.168.99.1/31
!
interface Ethernet2
   description P2P_LINK_TO_borderleaf1_Ethernet2
   no shutdown
   mtu 1550
   no switchport
   ip address 192.168.99.3/31
!
interface Ethernet5
   description P2P_LINK_TO_SPINE3_Ethernet8
   no shutdown
   mtu 1550
   no switchport
   ip address 192.168.3.9/31
!
interface Ethernet6
   description P2P_LINK_TO_SPINE4_Ethernet8
   no shutdown
   mtu 1550
   no switchport
   ip address 192.168.3.11/31
```

### Loopback Interfaces

#### Loopback Interfaces Summary

##### IPv4

| Interface | Description | VRF | IP Address |
| --------- | ----------- | --- | ---------- |
| Loopback0 | EVPN_Overlay_Peering | default | 192.168.201.3/32 |
| Loopback1 | VTEP_VXLAN_Tunnel_Source | default | 192.168.202.3/32 |

##### IPv6

| Interface | Description | VRF | IPv6 Address |
| --------- | ----------- | --- | ------------ |
| Loopback0 | EVPN_Overlay_Peering | default | - |
| Loopback1 | VTEP_VXLAN_Tunnel_Source | default | - |


#### Loopback Interfaces Device Configuration

```eos
!
interface Loopback0
   description EVPN_Overlay_Peering
   no shutdown
   ip address 192.168.201.3/32
!
interface Loopback1
   description VTEP_VXLAN_Tunnel_Source
   no shutdown
   ip address 192.168.202.3/32
```

### VLAN Interfaces

#### VLAN Interfaces Summary

| Interface | Description | VRF |  MTU | Shutdown |
| --------- | ----------- | --- | ---- | -------- |
| Vlan10 | DMZ | VRF_A | - | False |
| Vlan20 | Internal | VRF_A | - | False |
| Vlan30 | Test | John | - | False |

##### IPv4

| Interface | VRF | IP Address | IP Address Virtual | IP Router Virtual Address | VRRP | ACL In | ACL Out |
| --------- | --- | ---------- | ------------------ | ------------------------- | ---- | ------ | ------- |
| Vlan10 |  VRF_A  |  -  |  10.1.10.1/24  |  -  |  -  |  -  |  -  |
| Vlan20 |  VRF_A  |  -  |  10.1.20.1/24  |  -  |  -  |  -  |  -  |
| Vlan30 |  John  |  -  |  10.1.30.1/24  |  -  |  -  |  -  |  -  |

#### VLAN Interfaces Device Configuration

```eos
!
interface Vlan10
   description DMZ
   no shutdown
   vrf VRF_A
   ip address virtual 10.1.10.1/24
!
interface Vlan20
   description Internal
   no shutdown
   vrf VRF_A
   ip address virtual 10.1.20.1/24
!
interface Vlan30
   description Test
   no shutdown
   vrf John
   ip address virtual 10.1.30.1/24
```

### VXLAN Interface

#### VXLAN Interface Summary

| Setting | Value |
| ------- | ----- |
| Source Interface | Loopback1 |
| UDP port | 4789 |

##### VLAN to VNI, Flood List and Multicast Group Mappings

| VLAN | VNI | Flood List | Multicast Group |
| ---- | --- | ---------- | --------------- |
| 10 | 10010 | - | - |
| 20 | 10020 | - | - |
| 30 | 20030 | - | - |

##### VRF to VNI and Multicast Group Mappings

| VRF | VNI | Multicast Group |
| ---- | --- | --------------- |
| John | 20 | - |
| VRF_A | 10 | - |

#### VXLAN Interface Device Configuration

```eos
!
interface Vxlan1
   description borderleaf2_VTEP
   vxlan source-interface Loopback1
   vxlan udp-port 4789
   vxlan vlan 10 vni 10010
   vxlan vlan 20 vni 10020
   vxlan vlan 30 vni 20030
   vxlan vrf John vni 20
   vxlan vrf VRF_A vni 10
```

## Routing

### Service Routing Protocols Model

Multi agent routing protocol model enabled

```eos
!
service routing protocols model multi-agent
```

### Virtual Router MAC Address

#### Virtual Router MAC Address Summary

##### Virtual Router MAC Address: 00:1c:73:00:00:99

#### Virtual Router MAC Address Configuration

```eos
!
ip virtual-router mac-address 00:1c:73:00:00:99
```

### IP Routing

#### IP Routing Summary

| VRF | Routing Enabled |
| --- | --------------- |
| default | True |
| John | True |
| MGMT | False |
| VRF_A | True |

#### IP Routing Device Configuration

```eos
!
ip routing
ip routing vrf John
no ip routing vrf MGMT
ip routing vrf VRF_A
```

### IPv6 Routing

#### IPv6 Routing Summary

| VRF | Routing Enabled |
| --- | --------------- |
| default | False |
| John | false |
| MGMT | false |
| VRF_A | false |

### Router BGP

#### Router BGP Summary

| BGP AS | Router ID |
| ------ | --------- |
| 65203|  192.168.201.3 |

| BGP Tuning |
| ---------- |
| no bgp default ipv4-unicast |
| maximum-paths 4 ecmp 4 |

#### Router BGP Peer Groups

##### EVPN-OVERLAY-PEERS

| Settings | Value |
| -------- | ----- |
| Address Family | evpn |
| Source | Loopback0 |
| BFD | True |
| Ebgp multihop | 3 |
| Send community | all |
| Maximum routes | 0 (no limit) |

##### IPv4-UNDERLAY-PEERS

| Settings | Value |
| -------- | ----- |
| Address Family | ipv4 |
| Send community | all |
| Maximum routes | 12000 |

#### BGP Neighbors

| Neighbor | Remote AS | VRF | Shutdown | Send-community | Maximum-routes | Allowas-in | BFD | RIB Pre-Policy Retain | Route-Reflector Client | Passive |
| -------- | --------- | --- | -------- | -------------- | -------------- | ---------- | --- | --------------------- | ---------------------- | ------- |
| 192.168.3.8 | 65002 | default | - | Inherited from peer group IPv4-UNDERLAY-PEERS | Inherited from peer group IPv4-UNDERLAY-PEERS | - | - | - | - | - |
| 192.168.3.10 | 65002 | default | - | Inherited from peer group IPv4-UNDERLAY-PEERS | Inherited from peer group IPv4-UNDERLAY-PEERS | - | - | - | - | - |
| 192.168.99.0 | 65198 | default | - | Inherited from peer group IPv4-UNDERLAY-PEERS | Inherited from peer group IPv4-UNDERLAY-PEERS | - | - | - | - | - |
| 192.168.99.2 | 65198 | default | - | Inherited from peer group IPv4-UNDERLAY-PEERS | Inherited from peer group IPv4-UNDERLAY-PEERS | - | - | - | - | - |
| 192.168.201.13 | 65002 | default | - | Inherited from peer group EVPN-OVERLAY-PEERS | Inherited from peer group EVPN-OVERLAY-PEERS | - | Inherited from peer group EVPN-OVERLAY-PEERS | - | - | - |
| 192.168.201.14 | 65002 | default | - | Inherited from peer group EVPN-OVERLAY-PEERS | Inherited from peer group EVPN-OVERLAY-PEERS | - | Inherited from peer group EVPN-OVERLAY-PEERS | - | - | - |

#### Router BGP EVPN Address Family

##### EVPN Peer Groups

| Peer Group | Activate | Encapsulation |
| ---------- | -------- | ------------- |
| EVPN-OVERLAY-PEERS | True | default |

#### Router BGP VLANs

| VLAN | Route-Distinguisher | Both Route-Target | Import Route Target | Export Route-Target | Redistribute |
| ---- | ------------------- | ----------------- | ------------------- | ------------------- | ------------ |
| 10 | 192.168.201.3:10010 | 10010:10010 | - | - | learned |
| 20 | 192.168.201.3:10020 | 10020:10020 | - | - | learned |
| 30 | 192.168.201.3:20030 | 20030:20030 | - | - | learned |

#### Router BGP VRFs

| VRF | Route-Distinguisher | Redistribute |
| --- | ------------------- | ------------ |
| John | 192.168.201.3:20 | connected |
| VRF_A | 192.168.201.3:10 | connected |

#### Router BGP Device Configuration

```eos
!
router bgp 65203
   router-id 192.168.201.3
   maximum-paths 4 ecmp 4
   no bgp default ipv4-unicast
   neighbor EVPN-OVERLAY-PEERS peer group
   neighbor EVPN-OVERLAY-PEERS update-source Loopback0
   neighbor EVPN-OVERLAY-PEERS bfd
   neighbor EVPN-OVERLAY-PEERS ebgp-multihop 3
   neighbor EVPN-OVERLAY-PEERS send-community
   neighbor EVPN-OVERLAY-PEERS maximum-routes 0
   neighbor IPv4-UNDERLAY-PEERS peer group
   neighbor IPv4-UNDERLAY-PEERS send-community
   neighbor IPv4-UNDERLAY-PEERS maximum-routes 12000
   neighbor 192.168.3.8 peer group IPv4-UNDERLAY-PEERS
   neighbor 192.168.3.8 remote-as 65002
   neighbor 192.168.3.8 description spine3_Ethernet8
   neighbor 192.168.3.10 peer group IPv4-UNDERLAY-PEERS
   neighbor 192.168.3.10 remote-as 65002
   neighbor 192.168.3.10 description spine4_Ethernet8
   neighbor 192.168.99.0 peer group IPv4-UNDERLAY-PEERS
   neighbor 192.168.99.0 remote-as 65198
   neighbor 192.168.99.0 local-as 65298 no-prepend replace-as
   neighbor 192.168.99.0 description borderleaf1
   neighbor 192.168.99.2 peer group IPv4-UNDERLAY-PEERS
   neighbor 192.168.99.2 remote-as 65198
   neighbor 192.168.99.2 local-as 65298 no-prepend replace-as
   neighbor 192.168.99.2 description borderleaf1
   neighbor 192.168.201.13 peer group EVPN-OVERLAY-PEERS
   neighbor 192.168.201.13 remote-as 65002
   neighbor 192.168.201.13 description spine3
   neighbor 192.168.201.14 peer group EVPN-OVERLAY-PEERS
   neighbor 192.168.201.14 remote-as 65002
   neighbor 192.168.201.14 description spine4
   redistribute connected route-map RM-CONN-2-BGP
   !
   vlan 10
      rd 192.168.201.3:10010
      route-target both 10010:10010
      redistribute learned
   !
   vlan 20
      rd 192.168.201.3:10020
      route-target both 10020:10020
      redistribute learned
   !
   vlan 30
      rd 192.168.201.3:20030
      route-target both 20030:20030
      redistribute learned
   !
   address-family evpn
      neighbor EVPN-OVERLAY-PEERS activate
   !
   address-family ipv4
      no neighbor EVPN-OVERLAY-PEERS activate
      neighbor IPv4-UNDERLAY-PEERS activate
   !
   vrf John
      rd 192.168.201.3:20
      route-target import evpn 20:20
      route-target export evpn 20:20
      router-id 192.168.201.3
      redistribute connected
   !
   vrf VRF_A
      rd 192.168.201.3:10
      route-target import evpn 10:10
      route-target export evpn 10:10
      router-id 192.168.201.3
      redistribute connected
```

## BFD

### Router BFD

#### Router BFD Multihop Summary

| Interval | Minimum RX | Multiplier |
| -------- | ---------- | ---------- |
| 300 | 300 | 3 |

#### Router BFD Device Configuration

```eos
!
router bfd
   multihop interval 300 min-rx 300 multiplier 3
```

## Multicast

### IP IGMP Snooping

#### IP IGMP Snooping Summary

| IGMP Snooping | Fast Leave | Interface Restart Query | Proxy | Restart Query Interval | Robustness Variable |
| ------------- | ---------- | ----------------------- | ----- | ---------------------- | ------------------- |
| Enabled | - | - | - | - | - |

#### IP IGMP Snooping Device Configuration

```eos
```

## Filters

### Prefix-lists

#### Prefix-lists Summary

##### PL-LOOPBACKS-EVPN-OVERLAY

| Sequence | Action |
| -------- | ------ |
| 10 | permit 192.168.201.0/24 eq 32 |
| 20 | permit 192.168.202.0/24 eq 32 |

#### Prefix-lists Device Configuration

```eos
!
ip prefix-list PL-LOOPBACKS-EVPN-OVERLAY
   seq 10 permit 192.168.201.0/24 eq 32
   seq 20 permit 192.168.202.0/24 eq 32
```

### Route-maps

#### Route-maps Summary

##### RM-CONN-2-BGP

| Sequence | Type | Match | Set | Sub-Route-Map | Continue |
| -------- | ---- | ----- | --- | ------------- | -------- |
| 10 | permit | ip address prefix-list PL-LOOPBACKS-EVPN-OVERLAY | - | - | - |

#### Route-maps Device Configuration

```eos
!
route-map RM-CONN-2-BGP permit 10
   match ip address prefix-list PL-LOOPBACKS-EVPN-OVERLAY
```

## VRF Instances

### VRF Instances Summary

| VRF Name | IP Routing |
| -------- | ---------- |
| John | enabled |
| MGMT | disabled |
| VRF_A | enabled |

### VRF Instances Device Configuration

```eos
!
vrf instance John
!
vrf instance MGMT
!
vrf instance VRF_A
```
