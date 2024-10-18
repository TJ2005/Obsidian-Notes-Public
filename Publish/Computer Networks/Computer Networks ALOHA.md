---
Title: Computer Networks ALOHA
Status: 
marker:
  - "[[btech]]"
  - "[[Computer Networks]]"
  - "[[Aloha]]"
  - "[[random access protocols]]"
tags:
  - BTech
Date: 2024.10.06
Time: 20:14
---

---
# **Slotted ALOHA and Pure ALOHA**

**Slotted ALOHA** and **Pure ALOHA** are both types of **[[Computer Network Random Access Protocol|Random Access Protocol]]** used in network communication for sharing a common communication medium. They were among the earliest methods designed to handle multiple devices trying to transmit data simultaneously over the same channel, and they aim to resolve the issue of **collisions** in networks.

---

# **Collisions in Network Communication**

When a **collision** occurs in network communication (such as in **[[Computer Networks CSMA(CD CA)|CSMA/CD]]** or in **[[Computer Networks ALOHA|ALOHA]]** protocols), it refers to a situation where two or more devices attempt to send data simultaneously on the same communication channel. This results in the data being garbled or lost. However, collisions in this context are **electronic signaling events** and do not cause physical harm to the wires or communication medium.

### 1. **Low Voltage and Power**:
   - The electrical signals transmitted over network cables (like **[[Computer Networks Ethernet Cables|Ethernet cables]]**) are very low in voltage and power. A collision simply means that signals from multiple devices interfere with each other, causing the data to become corrupted or unintelligible.
   - Even though two signals may overlap or collide, their combined electrical power is not enough to cause any damage to the wire. The wires are designed to handle these low-power signals easily.

### 2. **Collision Detection Mechanism (CSMA/CD)**:
   - In protocols like **[[Computer Networks CSMA(CD CA)|CSMA/CD]]**, the devices on the network are constantly monitoring the wire. When a collision is detected, the devices stop transmitting immediately to prevent further issues. After detecting a collision, they send out a special signal called a **jam signal** to inform other devices that a collision occurred. Then, the devices wait for a random amount of time (using an algorithm like **exponential backoff**) before attempting to retransmit.
   - This collision detection and backoff mechanism prevents excessive load on the wire, ensuring that the devices don't continuously transmit and overload the system.

### 3. **Current and Data Signals are Very Different from Short Circuits**:
   - The electrical signals used in data communication are **controlled pulses** of voltage and current. These signals are meant to be interpreted by network devices (like computers, routers, or switches) as bits of data. A collision just results in two signals overlapping, which leads to data corruption but no physical damage.
   - By contrast, an electrical **[[short circuit]]** happens when a high-current electrical path is created unintentionally, usually due to exposed wires touching each other or improper connections. This can cause heat buildup and potentially damage the wiring or devices. In network communication, the current involved in data transmission is far too small to cause overheating or physical damage, even in the event of a collision.

### 4. **Wires are Designed for Robustness**:
   - **[[Computer Networks Ethernet Cables|Ethernet cables]]** and other network cables are designed to handle a range of electrical conditions without damage. They use insulated copper wires (in the case of traditional Ethernet cables) that can easily carry the data signals necessary for communication without risk of damage from collisions.
   - The wires are also shielded or twisted in such a way that they minimize **[[electromagnetic interference (EMI)|EMI]]**, further protecting against the risk of damage or loss of signal quality.

### 5. **Collisions are a Logical Event, Not a Physical One**:
   - In network communication, a collision is a **logical event**, meaning it's related to the way data is being transmitted and interpreted, not the physical integrity of the wire. The wire simply carries the electrical signals, and the collision refers to two signals overlapping, not an electrical failure.
   - The result of a collision is usually just **corrupted data**, which leads to a retransmission of the data. Devices on the network are programmed to recognize collisions and handle them appropriately.

### 6. **Built-in Error Detection and Retransmission**:
   - In most network protocols, there's a built-in system for **[[error detection]]**. If data gets corrupted due to a collision, the devices involved will detect this through methods like **checksums** or **[[cyclic redundancy checks (CRC)|CRC]]**. After detecting an error, the devices will simply discard the corrupted data and try to resend it.
   - This process ensures that data integrity is maintained without causing any harm to the physical medium.

---

## **Summary**:
- A **collision** in networking does not involve dangerous electrical surges. Instead, it refers to two or more devices sending data at the same time, leading to a mix of signals. The low voltage and power of the

# References

###### Information
- date: 2024.10.06
- time: 20:14

---

