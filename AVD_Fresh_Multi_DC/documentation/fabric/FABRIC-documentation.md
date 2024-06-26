# FABRIC

## Table of Contents

- [Fabric Switches and Management IP](#fabric-switches-and-management-ip)
  - [Fabric Switches with inband Management IP](#fabric-switches-with-inband-management-ip)
- [Fabric Topology](#fabric-topology)
- [Fabric IP Allocation](#fabric-ip-allocation)
  - [Fabric Point-To-Point Links](#fabric-point-to-point-links)
  - [Point-To-Point Links Node Allocation](#point-to-point-links-node-allocation)
  - [Loopback Interfaces (BGP EVPN Peering)](#loopback-interfaces-bgp-evpn-peering)
  - [Loopback0 Interfaces Node Allocation](#loopback0-interfaces-node-allocation)
  - [VTEP Loopback VXLAN Tunnel Source Interfaces (VTEPs Only)](#vtep-loopback-vxlan-tunnel-source-interfaces-vteps-only)
  - [VTEP Loopback Node allocation](#vtep-loopback-node-allocation)

## Fabric Switches and Management IP

| POD | Type | Node | Management IP | Platform | Provisioned in CloudVision | Serial Number |
| --- | ---- | ---- | ------------- | -------- | -------------------------- | ------------- |
| FABRIC | l3leaf | borderleaf1 | - | cEOS-lab | Provisioned | - |
| FABRIC | l3leaf | borderleaf2 | - | cEOS-lab | Provisioned | - |
| FABRIC | l3leaf | leaf1 | - | cEOS-lab | Provisioned | - |
| FABRIC | l3leaf | leaf2 | - | cEOS-lab | Provisioned | - |
| FABRIC | l3leaf | leaf3 | - | cEOS-lab | Provisioned | - |
| FABRIC | l3leaf | leaf4 | - | cEOS-lab | Provisioned | - |
| FABRIC | spine | spine1 | - | cEOS-lab | Provisioned | - |
| FABRIC | spine | spine2 | - | cEOS-lab | Provisioned | - |
| FABRIC | spine | spine3 | - | cEOS-lab | Provisioned | - |
| FABRIC | spine | spine4 | - | cEOS-lab | Provisioned | - |

> Provision status is based on Ansible inventory declaration and do not represent real status from CloudVision.

### Fabric Switches with inband Management IP

| POD | Type | Node | Management IP | Inband Interface |
| --- | ---- | ---- | ------------- | ---------------- |

## Fabric Topology

| Type | Node | Node Interface | Peer Type | Peer Node | Peer Interface |
| ---- | ---- | -------------- | --------- | ----------| -------------- |
| l3leaf | borderleaf1 | Ethernet1 | l3leaf | borderleaf2 | Ethernet1 |
| l3leaf | borderleaf1 | Ethernet2 | l3leaf | borderleaf2 | Ethernet2 |
| l3leaf | borderleaf1 | Ethernet3 | spine | spine1 | Ethernet7 |
| l3leaf | borderleaf1 | Ethernet4 | spine | spine2 | Ethernet7 |
| l3leaf | borderleaf2 | Ethernet5 | spine | spine3 | Ethernet8 |
| l3leaf | borderleaf2 | Ethernet6 | spine | spine4 | Ethernet8 |
| l3leaf | leaf1 | Ethernet1 | mlag_peer | leaf2 | Ethernet1 |
| l3leaf | leaf1 | Ethernet2 | mlag_peer | leaf2 | Ethernet2 |
| l3leaf | leaf1 | Ethernet3 | spine | spine1 | Ethernet3 |
| l3leaf | leaf1 | Ethernet4 | spine | spine2 | Ethernet3 |
| l3leaf | leaf2 | Ethernet3 | spine | spine1 | Ethernet4 |
| l3leaf | leaf2 | Ethernet4 | spine | spine2 | Ethernet4 |
| l3leaf | leaf3 | Ethernet1 | mlag_peer | leaf4 | Ethernet1 |
| l3leaf | leaf3 | Ethernet2 | mlag_peer | leaf4 | Ethernet2 |
| l3leaf | leaf3 | Ethernet5 | spine | spine3 | Ethernet5 |
| l3leaf | leaf3 | Ethernet6 | spine | spine4 | Ethernet5 |
| l3leaf | leaf4 | Ethernet5 | spine | spine3 | Ethernet6 |
| l3leaf | leaf4 | Ethernet6 | spine | spine4 | Ethernet6 |

## Fabric IP Allocation

### Fabric Point-To-Point Links

| Uplink IPv4 Pool | Available Addresses | Assigned addresses | Assigned Address % |
| ---------------- | ------------------- | ------------------ | ------------------ |
| 192.168.03.0/24 | 256 | 12 | 4.69 % |
| 192.168.103.0/24 | 256 | 12 | 4.69 % |

### Point-To-Point Links Node Allocation

| Node | Node Interface | Node IP Address | Peer Node | Peer Interface | Peer IP Address |
| ---- | -------------- | --------------- | --------- | -------------- | --------------- |
| borderleaf1 | Ethernet1 | 192.168.99.0/31 | borderleaf2 | Ethernet1 | 192.168.99.1/31 |
| borderleaf1 | Ethernet2 | 192.168.99.2/31 | borderleaf2 | Ethernet2 | 192.168.99.3/31 |
| borderleaf1 | Ethernet3 | 192.168.103.9/31 | spine1 | Ethernet7 | 192.168.103.8/31 |
| borderleaf1 | Ethernet4 | 192.168.103.11/31 | spine2 | Ethernet7 | 192.168.103.10/31 |
| borderleaf2 | Ethernet5 | 192.168.3.9/31 | spine3 | Ethernet8 | 192.168.3.8/31 |
| borderleaf2 | Ethernet6 | 192.168.3.11/31 | spine4 | Ethernet8 | 192.168.3.10/31 |
| leaf1 | Ethernet3 | 192.168.103.1/31 | spine1 | Ethernet3 | 192.168.103.0/31 |
| leaf1 | Ethernet4 | 192.168.103.3/31 | spine2 | Ethernet3 | 192.168.103.2/31 |
| leaf2 | Ethernet3 | 192.168.103.5/31 | spine1 | Ethernet4 | 192.168.103.4/31 |
| leaf2 | Ethernet4 | 192.168.103.7/31 | spine2 | Ethernet4 | 192.168.103.6/31 |
| leaf3 | Ethernet5 | 192.168.3.1/31 | spine3 | Ethernet5 | 192.168.3.0/31 |
| leaf3 | Ethernet6 | 192.168.3.3/31 | spine4 | Ethernet5 | 192.168.3.2/31 |
| leaf4 | Ethernet5 | 192.168.3.5/31 | spine3 | Ethernet6 | 192.168.3.4/31 |
| leaf4 | Ethernet6 | 192.168.3.7/31 | spine4 | Ethernet6 | 192.168.3.6/31 |

### Loopback Interfaces (BGP EVPN Peering)

| Loopback Pool | Available Addresses | Assigned addresses | Assigned Address % |
| ------------- | ------------------- | ------------------ | ------------------ |
| 192.168.101.0/24 | 256 | 5 | 1.96 % |
| 192.168.201.0/24 | 256 | 5 | 1.96 % |

### Loopback0 Interfaces Node Allocation

| POD | Node | Loopback0 |
| --- | ---- | --------- |
| FABRIC | borderleaf1 | 192.168.101.3/32 |
| FABRIC | borderleaf2 | 192.168.201.3/32 |
| FABRIC | leaf1 | 192.168.101.1/32 |
| FABRIC | leaf2 | 192.168.101.2/32 |
| FABRIC | leaf3 | 192.168.201.1/32 |
| FABRIC | leaf4 | 192.168.201.2/32 |
| FABRIC | spine1 | 192.168.101.11/32 |
| FABRIC | spine2 | 192.168.101.12/32 |
| FABRIC | spine3 | 192.168.201.13/32 |
| FABRIC | spine4 | 192.168.201.14/32 |

### VTEP Loopback VXLAN Tunnel Source Interfaces (VTEPs Only)

| VTEP Loopback Pool | Available Addresses | Assigned addresses | Assigned Address % |
| --------------------- | ------------------- | ------------------ | ------------------ |
| 192.168.102.0/24 | 256 | 3 | 1.18 % |
| 192.168.202.0/24 | 256 | 3 | 1.18 % |

### VTEP Loopback Node allocation

| POD | Node | Loopback1 |
| --- | ---- | --------- |
| FABRIC | borderleaf1 | 192.168.102.3/32 |
| FABRIC | borderleaf2 | 192.168.202.3/32 |
| FABRIC | leaf1 | 192.168.102.1/32 |
| FABRIC | leaf2 | 192.168.102.1/32 |
| FABRIC | leaf3 | 192.168.202.1/32 |
| FABRIC | leaf4 | 192.168.202.1/32 |
