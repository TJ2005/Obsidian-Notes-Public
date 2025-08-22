### Link State Routing

**Link State Routing** is a type of network routing protocol that helps determine the shortest path between nodes in a network. This protocol is used to improve the efficiency and speed of packet transmission across large networks by enabling routers to have a complete view of the network.

#### Key Features:

- **Objective**: To determine the shortest path from one node to every other node in the network.
- **Approach**: It relies on the "link-state" approach, where each router sends information about its directly connected neighbors to all other routers in the network.
- **Algorithm Used**: Dijkstra’s algorithm is often used for computing the shortest path in Link State Routing.

### Phases of Link State Routing:

1. **Phase 1: Reliable Flooding**
   - In this phase, each node in the network shares the cost to reach its directly connected neighbors with all other nodes.
   - This is done through a process known as **[[flooding]]**, ensuring every node knows the complete structure of the network, including the cost of each link.
   - After receiving this information, each router builds a topology map of the network.
   - The flooding runs during the complete duration of the process until the entire map is built. This means that the flooding happens and then the neighboring information is also represented in the map.

2. **Phase 2: Shortest Path Calculation**
   - Once the network's complete topology is known, each router can individually calculate the shortest path to every other router using Dijkstra’s algorithm.
   - These calculations are stored in a **[[routing table]]** at each node.

### Understanding the Tables in the Image:
In the image, you can see various **Node-Cost tables** for each node. These tables represent the cost (or distance) from one node to its neighboring nodes. The numbers indicate the cost or weight associated with each link. For example:

- **Table for Node A:**
  - Node B has a cost of 3.
  - Node C has a cost of 2.

This means Node A can directly reach Node B at a cost of 3 units (distance, time, etc.), and Node C at a cost of 2.

- **Table for Node D:**
  - Node C has a cost of 2.
  - Node E has a cost of 3.
  - Node A has a cost of 1.

This indicates Node D has direct connections to Nodes C, E, and A, with respective costs of 2, 3, and 1.

### Summary of the Tables:
Each table is part of the Link State Routing algorithm's **Phase 1 (Reliable Flooding)**, where each node has collected the cost information from its neighbors. These tables are then used by each node to construct a complete topology of the network, which will be utilized in **Phase 2** to calculate the shortest paths.

In conclusion, the tables serve as the local information gathered by each node about its neighbors. Once all nodes share their information, the network becomes fully aware of its structure, and shortest paths can be calculated efficiently.

### Diagram:

The image represents a sample network where:
- Each node has neighbors and costs associated with reaching them.
- Lines between nodes represent direct connections, and the numbers on the lines denote the cost to travel between those nodes.

---

This should give you a clear overview of how **Link State Routing** works and the significance of the tables shown in the diagram. Let me know if you need further details!