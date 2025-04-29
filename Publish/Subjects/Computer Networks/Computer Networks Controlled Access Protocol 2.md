---
Title: Computer Networks Controlled Access Protocol
Status: 
marker:
  - "[[Computer Networks]]"
  - "[[Reservation Protocol]]"
  - "[[Rolling Protocol]]"
  - "[[Token Passing]]"
tags:
  - BTech
Date: 2024.10.07
Time: 06:58
---
### **Controlled Access Protocol**

**Controlled Access Protocol** is a type of **media access control (MAC)** protocol used to manage how multiple devices share a communication channel. In contrast to **[[Computer Networks Random Access Protocol|random access protocols]]** like **[[Computer Networks ALOHA|ALOHA]]** or **[[Computer Networks CSMA(CD CA)|CSMA]]**, where devices can transmit whenever the medium is free, **controlled access protocols** ensure that only one device can transmit at a time. This is done using a structured mechanism, which eliminates the chances of collisions, but it requires coordination among the devices.

### Key Characteristics:
- **Centralized or Distributed Control**: Controlled access protocols involve some form of control, either through a **[[Computer Networks Centralized Control|central authority]]** or a **[[Computer Networks Distributed Control|distributed mechanism]]**, that determines which device has the right to transmit.
- **Eliminates Collisions**: Since only one device can transmit at a time, collisions (where two devices send data simultaneously, causing corruption) are avoided.
- **Coordination Needed**: Devices either request permission to transmit or take turns in an orderly fashion. This requires more overhead and management than **[[Computer Networks Random Access Protocol|random access protocols]]**.

### Types of Controlled Access Protocols:
There are three main types of controlled access protocols:

---

### 1. **Reservation Protocol**
In **[[Computer Networks Reservation Protocol|reservation-based access]]**, devices reserve the communication channel before transmitting data. This approach ensures that only one device is using the medium at a given time.

#### How it Works:
- The medium is divided into **[[Computer Networks Time Slots|time slots]]** or periods.
- Devices that wish to transmit data first **reserve the medium** during a reservation period. They request the use of the medium by sending a **reservation request**.
- Once the medium is reserved for a specific device, it can transmit its data without risk of collisions.

#### Example:
- In **[[Computer Networks TDMA|TDMA (Time Division Multiple Access)]]**, time is divided into slots, and each device is assigned a specific time slot for transmission. The device can only transmit during its allocated slot, eliminating collisions.

---

### 2. **Polling Protocol**
In **[[Computer Networks Polling Protocol|polling]]**, a central controller (also called the **[[Computer Networks Master|master]]** or **polling device**) manages which device is allowed to transmit. The controller "polls" each device to see if it has data to transmit.

#### How it Works:
- The central controller polls each device in a **[[Round Robin Algorithm|round-robin]]** fashion or based on a **[[Computer Networks Priority Scheme|priority scheme]]**.
- If a device has data to send, it transmits when it is polled.
- **Polling** is a mechanism where a central device (the controller or master) periodically **asks** each connected device if it needs to communicate, such as whether it has data ready to be transmitted over the network.
- If it has no data to send, the controller moves to the next device.

#### Example:
- **[[Computer Networks Token Bus|Token Bus]]** or **[[Computer Networks Token Ring|Token Ring]]** protocols use polling mechanisms to give each device the opportunity to transmit in an orderly fashion.
- **[[USB]]** uses polling between the host and devices connected to the bus. The host periodically checks each device to see if it has data to send or receive.

---

### 3. **Token Passing Protocol**
In **[[Computer Networks Controlled Access Protocol#3. **Token Passing Protocol**|token passing]]**, a special data packet called a **[[Computer Networks Token|token]]** circulates through the network. Only the device that holds the token can transmit. Once the device is done transmitting, it passes the token to the next device.

#### How it Works:
- A **token** (a small data packet) is passed from one device to another in a logical or physical **[[Computer Networks Ring Topology|ring]]**.
- When a device receives the token, it can transmit its data.
- After finishing transmission, the device passes the token to the next device in the sequence.
- If a device has no data to send, it passes the token immediately to the next device.

#### Example:
- **[[Computer Networks Token Ring|Token Ring (IEEE 802.5)]]** is a network protocol where devices are connected in a ring topology, and a token is passed between them to control access to the communication channel.
- **[[Computer Networks Token Bus|Token Bus (IEEE 802.4)]]** also uses the token passing mechanism, but in a **[[Computer Networks Bus Topology|bus topology]]**.

---

### **Advantages of Controlled Access Protocols**:
- **No Collisions**: Since only one device is allowed to transmit at a time, there is no risk of data collisions. This makes controlled access protocols more efficient in **[[Computer Networks High Traffic Networks|networks with high traffic]]**.
- **Deterministic**: Controlled access provides **[[Computer Networks Deterministic Access|deterministic]]** behavior, meaning each device knows when it will be able to transmit, reducing the uncertainty present in **[[Computer Networks Random Access Protocol|random access protocols]]**.

### **Disadvantages of Controlled Access Protocols**:
- **Overhead**: The control mechanisms (such as reservation, polling, or token passing) introduce additional overhead, which can slow down the network when traffic is low.
- **Centralized Control (Polling)**: In systems where polling is used, the central controller can become a bottleneck or point of failure if it malfunctions.
- **Latency**: Devices may need to wait for their turn (polling or token passing), which introduces some delay (latency) compared to **[[Computer Network Random Access Protocol|Random Access Protocol]]** where devices can transmit as soon as the medium is free.

---

### **Comparison of Controlled Access Protocols with Random Access Protocols**:

| Feature            | **Controlled Access Protocols**                                                 | **Random Access Protocols** (e.g., **CSMA**, **ALOHA**)      |
| ------------------ | ------------------------------------------------------------------------------- | ------------------------------------------------------------ |
| **Collision Risk** | No collisions (devices take turns)                                              | High risk of collisions (devices compete to transmit)        |
| **Efficiency**     | High in high-traffic networks                                                   | Low efficiency in high-traffic networks due to collisions    |
| **Access Control** | Centralized or decentralized control (polling, token passing)                   | Decentralized (devices transmit whenever the medium is idle) |
| **Overhead**       | Higher overhead (due to coordination mechanisms)                                | Lower overhead                                               |
| **Latency**        | Predictable, but potentially higher                                             | Variable, depends on traffic and collision occurrence        |
| **Use Cases**      | Networks requiring deterministic access (e.g., industrial control ne<br>tworks) | General-purpose LAN and wireless networks                    |

---

### **Examples of Controlled Access Protocols in Use**:
- **[[Computer Networks Token Ring|Token Ring]]** and **[[Computer Networks Token Bus|Token Bus]]** are classic examples of controlled access protocols used in LANs. While not as commonly used today, these protocols were popular in certain types of networks, particularly where deterministic access was required.
- **[[Computer Networks Polling|Polling]]** is used in systems like **[[Computer Networks USB|USB]]**, where the host periodically checks connected devices to see if they have data to send or receive.

---

### **Conclusion**:
Controlled Access Protocols provide a reliable way to manage access to a shared communication medium, especially in networks where high traffic makes collisions costly. By ensuring that only one device can transmit at a time, controlled access protocols avoid the inefficiencies and unpredictability of **[[Computer Networks Random Access Protocol|random access protocols]]**, making them ideal for **[[Computer Networks High Traffic Networks|high-traffic]]** or **[[Computer Networks Deterministic Networks|deterministic]]** network environments.

---

# References

###### Information
- date: 2024.10.07
- time: 06:58

---

This version includes your requested structure and formatting, with appropriate linking and display text. Let me know if there’s anything else you'd like to adjust!