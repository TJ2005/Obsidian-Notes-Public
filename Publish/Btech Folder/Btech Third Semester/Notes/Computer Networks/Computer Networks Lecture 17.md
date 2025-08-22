---
Title: Computer Networks Lecture 12
Status: 
marker:
  - "[[Computer Networks]]"
  - "[[Protocols]]"
  - "[[Aloha]]"
tags:
  - BTech
Date: 2024.09.28
Time: 10:58
---
# Computer Networks Lecture 12

Multi-access protocols, also known as **Multiple Access Protocols**, are methods used in network communication that allow multiple devices or stations to share the same communication medium efficiently. These protocols play a critical role in determining how data transmission occurs in environments where many users or systems try to send and receive data over a shared channel. The goal is to minimize collisions and maximize the network’s throughput.

#### Types of Multiple Access Protocols

Multiple access protocols can be broadly classified into three categories:

### 1. **Random Access Protocols**

In **random access protocols**, all stations can transmit data whenever they have data to send. There is no centralized control over who can transmit, and this may lead to data collisions when two or more stations transmit at the same time.

#### a) Pure ALOHA
- **Concept**: Each station transmits data whenever it has data, but collisions are likely.
- **Collision handling**: If a collision occurs, the station waits for a random amount of time before retransmitting.
- **Efficiency**: Pure ALOHA has a low throughput, about 18.4%, due to the high chance of collisions.

#### b) Slotted ALOHA
- **Improvement over Pure ALOHA**: Time is divided into discrete slots, and stations can only transmit at the beginning of these slots.
- **Collision handling**: Similar to Pure ALOHA, but the chance of collisions is reduced because transmissions can only start at specific times.
- **Efficiency**: Slotted ALOHA has a better throughput than Pure ALOHA, approximately 36.8%.

#### c) CSMA (Carrier Sense Multiple Access)
- **Concept**: Stations listen to the channel before transmitting. If the channel is busy, they wait; if the channel is idle, they transmit.
- **Types**:
  - **1-persistent CSMA**: If the channel is idle, the station transmits immediately.
  - **Non-persistent CSMA**: If the channel is busy, the station waits for a random time and tries again.
  - **p-persistent CSMA**: The station transmits with a probability \( p \) if the channel is idle, and defers with probability \( (1 - p) \).

#### d) CSMA/CD (Carrier Sense Multiple Access with Collision Detection)
- **Used in Ethernet networks**: CSMA/CD improves CSMA by detecting collisions during transmission. If a collision is detected, the transmission stops, and the station waits for a random backoff time before trying again.
- **Efficiency**: CSMA/CD is effective for wired networks like Ethernet, but it is less effective for wireless networks due to difficulties in detecting collisions in such environments.

### 2. **Controlled Access Protocols**

In **controlled access protocols**, the stations follow rules that ensure only one station transmits at a time, thereby avoiding collisions altogether.

#### a) Reservation
- **Concept**: Stations make reservations to access the channel. Only those stations with a reservation can transmit.
- **Used in time-division multiple access (TDMA)** systems, where the channel is divided into time slots and each station reserves a slot.

#### b) Polling
- **Concept**: A central controller polls each station in turn to grant permission to transmit.
- **Example**: A master-slave relationship where the master polls each slave device.

#### c) Token Passing
- **Concept**: A token (a small data packet) circulates around the network, and only the station holding the token can transmit.
- **Example**: Token Ring and FDDI (Fiber Distributed Data Interface) networks.

### 3. **Channelization Protocols**

In **channelization protocols**, the communication channel is divided into smaller channels, and each station is assigned a unique channel to avoid collisions.

#### a) FDMA (Frequency Division Multiple Access)
- **Concept**: The frequency spectrum is divided into different frequency bands, and each station is allocated a specific band for communication.
- **Use case**: Typically used in analog communication systems and satellite communication.

#### b) TDMA (Time Division Multiple Access)
- **Concept**: Time is divided into time slots, and each station is allocated a specific time slot for transmission.
- **Use case**: TDMA is widely used in digital cellular networks like GSM.

#### c) CDMA (Code Division Multiple Access)
- **Concept**: Each station is assigned a unique code, and all stations can transmit simultaneously using the same frequency band. The receiver decodes the received signals based on the unique code.
- **Use case**: Used in 3G cellular networks.

### Summary of Different Multi-Access Protocols:

| Protocol               | Concept                                                                                       | Example/Use Case                   | Throughput | Collision Avoidance |
|------------------------|-----------------------------------------------------------------------------------------------|------------------------------------|------------|---------------------|
| **Pure ALOHA**          | Transmit whenever data is available.                                                          | Wireless networks                  | Low (~18%) | No                  |
| **Slotted ALOHA**       | Transmit at the beginning of time slots.                                                      | Wireless networks                  | Medium (~36%) | No                  |
| **CSMA**                | Listen to the channel before transmitting.                                                    | Wired networks                     | High       | Yes (with sensing)  |
| **CSMA/CD**             | Detect collisions during transmission and abort if needed.                                    | Ethernet                           | High       | Yes (collision detection) |
| **Reservation**         | Reserve time slots for transmission.                                                          | TDMA systems                       | Very High  | Yes                 |
| **Polling**             | Central controller polls each station to grant permission to transmit.                        | Master-slave networks              | High       | Yes                 |
| **Token Passing**       | A token is passed around the network, and only the holder can transmit.                       | Token Ring, FDDI                   | High       | Yes                 |
| **FDMA**                | Frequency spectrum is divided into channels, and each station uses a unique frequency.        | Analog systems, satellite          | High       | Yes                 |
| **TDMA**                | Time is divided into slots, and each station is allocated a specific time slot to transmit.    | GSM networks                       | High       | Yes                 |
| **CDMA**                | Each station is assigned a unique code and all stations transmit at the same time.            | 3G cellular networks               | High       | Yes (code-based)    |

---

### Conclusion

Each multi-access protocol is designed with specific advantages and trade-offs. Random access protocols like ALOHA are simple but can suffer from collisions, while controlled access and channelization methods ensure more organized transmissions, minimizing collisions but adding complexity in scheduling and resource allocation. The choice of the protocol depends on the network requirements, such as the number of users, throughput, and reliability.