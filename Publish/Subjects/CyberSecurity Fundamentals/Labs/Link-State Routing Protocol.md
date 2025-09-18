---
Title: Link-State Routing Protocol
Status:
marker:
  - "[[Computer Networks]]"
  - "[[Cybersecurity Fundamentals]]"
tags:
Date: 2025.09.05
Time: 10:26
---
# Link-State Routing Protocol

Link-state routing is a **dynamic routing method** used in computer networks where routers exchange information about the *state of their links* (connections to neighbors) to build a complete map of the network.

## Key Idea

* Each router discovers its neighbors and measures the **cost/metric** of the links (like bandwidth, delay, or hop count).
* It floods this information (Link-State Advertisements, LSAs) throughout the network.
* Every router then builds the **same topology map** of the entire network.
* Using Dijkstra’s **Shortest Path First (SPF)** algorithm, each router computes the best path to every destination.

---

## Steps in Link-State Routing

1. **Neighbor Discovery**
   Routers identify directly connected neighbors (via "Hello" packets).

2. **Link-State Advertisement (LSA)**
   Each router creates an LSA describing its links and costs, then floods it to all routers in the area.

3. **Database Synchronization**
   All routers store LSAs in a **Link-State Database (LSDB)**, which is identical for all routers in the same area.

4. **Shortest Path Calculation**
   Each router independently runs Dijkstra’s SPF on the LSDB to compute the **routing table**.

---
## Features

* **Converges quickly** (faster than distance-vector protocols like RIP).
* **Scalable** for larger networks.
* Uses **more memory and CPU** since each router maintains the full network topology.

## Examples of Link-State Protocols
* **OSPF (Open Shortest Path First)**
* **IS-IS (Intermediate System to Intermediate System)**

---

In short:
**Link-state routing = each router has a full map of the network, uses Dijkstra’s algorithm, and independently calculates the best paths.**

---

Do you want me to also compare it side-by-side with **distance-vector routing** (like RIP) so you can see the differences clearly?



# References


###### Information
- date: 2025.09.05
- time: 10:26