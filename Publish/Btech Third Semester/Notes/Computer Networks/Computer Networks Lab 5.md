---
Title: Computer Networks Lab 5
Status: 
marker: 
tags: 
Date: 2024.08.12
Time: 10:41
---
# Topologies in Cisco Packet Tracer

We have various types of [topologies](#topologies-in-cisco-packet-tracer) that we use in a network. Today we will be simulating a:

- [Ring Topology](#ring-topology)
- [Star Topology](#star-topology)
- [Mesh Topology](#mesh-topology)
- [Bus Topology](#bus-topology)
- [Tree Topology](#tree-topology)
- [Hybrid Topology](#hybrid-topology)

## Ring Topology
- Devices are connected in a circular fashion, and each device is connected to two other devices, forming a ring.
- If one connection fails, the data can still circulate in the opposite direction.

![[Pasted image 20240812104120.png]]

## Star Topology
- All devices are connected to a central hub or switch. Each device has a point-to-point connection with the hub.
- Easy to manage and troubleshoot, but the hub represents a single point of failure.
![[Pasted image 20240812104342.png]]

## Mesh Topology
- Every device is connected to every other device in the network.
- Provides high redundancy and reliability as there are multiple paths for data transmission.
![[Pasted image 20240812104355.png]]

## Bus Topology
- All devices share a single central cable or backbone.
- If the central cable fails, the entire network can be disrupted.
![[Pasted image 20240812104422.png]]

## Tree Topology
A hybrid topology combining characteristics of star and bus topologies. Devices are grouped in star-configured clusters connected to a central bus backbone.

## Hybrid Topology
A combination of two or more different topologies. Provides greater flexibility and can be tailored to specific network needs.

# References

###### Information
- date: 2024.08.12
- time: 10:41
