---
Title: Computer Networks Lecture 13
Status: 
marker:
  - "[[CSMA]]"
  - "[[Computer Networks]]"
tags:
  - BTech
Date: 2024.09.28
Time: 10:58
---
# Computer Networks Lecture 13

**CSMA (Carrier Sense Multiple Access)** is a network protocol used in communication systems to manage access to a shared transmission medium (such as a wired or wireless network). It is designed to minimize the chances of data collisions by allowing each device (or "station") to sense whether the channel is free before sending data. This method helps prevent data packets from colliding in the transmission medium.

### Why Learn CSMA?

Understanding **CSMA** is essential because it forms the backbone of many communication technologies, especially in **Ethernet** and **Wi-Fi (IEEE 802.11)** networks. Learning CSMA can help you understand:
- **How data transmission works** in shared communication mediums.
- **How to manage and reduce collisions** in a network, improving efficiency and throughput.
- The underlying principles of several widely used **network protocols**.

It’s also valuable for understanding how wireless networks function, how traffic is controlled in busy networks, and how congestion is managed to provide more stable communication channels.

### Applications of CSMA:

CSMA is commonly used in:
- **Ethernet (IEEE 802.3)**: Early Ethernet networks (now upgraded) used CSMA to avoid collisions when multiple stations tried to communicate over the same wired channel.
- **Wi-Fi (IEEE 802.11)**: In Wi-Fi networks, CSMA/CA (Collision Avoidance) is used to avoid collisions in wireless transmission.
- **IoT (Internet of Things)**: CSMA is used in IoT devices where multiple sensors or devices share a single communication channel.
- **Wireless Sensor Networks**: In scenarios like home automation, smart agriculture, or industrial monitoring, CSMA helps avoid interference in the communication channel.
- **Satellite and Radio Communications**: CSMA is also used in satellite and radio communication systems where multiple stations access the same frequency channel.

### Example of What Happens in CSMA:

1. **Channel Sensing**: Device A wants to transmit data, but it first listens to the channel to see if it’s idle or if another device is transmitting.
   
2. **Idle Channel**: If the channel is idle, Device A starts transmitting its data immediately.

3. **Busy Channel**: If the channel is busy because Device B is transmitting, Device A will wait and continue sensing the channel until it becomes idle. This reduces the chances of both devices transmitting at the same time and causing a collision.

4. **Collision**: In some versions, like CSMA/CD (Collision Detection), if two devices (say Device A and Device C) happen to transmit data at exactly the same moment, a collision occurs. Both devices will detect the collision and stop transmitting, wait for a random amount of time (called backoff), and then try to retransmit.

### Example Scenario:

Imagine multiple computers in a local office network sharing the same Ethernet cable to communicate with a server. Here’s what happens:
- Each computer waits until no one else is using the cable.
- If the cable is free, the computer sends its data packet.
- If two computers try to send data at the same time, both detect the collision, stop sending data, and wait for a random time before trying again.

In this way, CSMA helps multiple devices share a communication channel without overwhelming it with simultaneous transmissions, improving the overall data transmission efficiency.

---

Let me know if you need further examples or have more questions!

The image provides an explanation of **1-persistent CSMA (Carrier Sense Multiple Access)**, summarized as follows:

1. **Listening to the Channel**: Before transmitting data, the station listens to the channel to check if anyone else is transmitting at that moment.
2. **Channel is Idle**: If the channel is idle, the station immediately transmits a frame.
3. **Channel is Busy**: If the channel is busy, the station continuously senses the transmission medium until it becomes idle.
4. **Probability of 1**: Since the station transmits the frame with a probability of 1 when the channel becomes idle, this scheme is referred to as **1-persistent CSMA**.
---

**1-persistent CSMA:**

1) **Channel Listening**: Before sending data, the station first listens to the channel to check if anyone else is transmitting at that moment.

2) **Transmission on Idle Channel**: If the channel is idle, the station immediately transmits a frame.

3) **Handling Busy Channel**: If the channel is busy, the station continuously senses the transmission medium until it becomes idle.

4) **Guaranteed Transmission**: Since the station transmits the frame with a probability of 1 as soon as the channel becomes idle, this method is called **1-persistent CSMA**.

---
This captures the essence of the original content in a more structured way.
