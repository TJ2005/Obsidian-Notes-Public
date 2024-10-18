---
Title: Computer Networks CSMA(CD CA)
Status: 
marker:
  - "[[btech]]"
  - "[[Computer Networks]]"
  - "[[CSMA]]"
  - "[[random access protocols]]"
tags: 
Date: 2024.10.06
Time: 20:22
---
# Computer Networks CSMA(CD CA)

### **CSMA (Carrier Sense Multiple Access)**

**CSMA** is a **media access control protocol** used in network communication to manage how devices share a common communication medium, such as Ethernet or wireless networks. It is designed to reduce **collisions** that occur when two or more devices try to send data at the same time on the same channel.

#### How CSMA Works:
- **Carrier Sense**: Before a device sends data, it first listens (or "senses") the channel to check if it is idle or busy. The idea is to only send data when the channel is clear, to reduce the chances of collision.
- **Multiple Access**: Multiple devices share the same communication medium (e.g., Ethernet cable or wireless spectrum).
- **Action on Busy Medium**: If the medium is busy (i.e., another device is already transmitting), the device waits until the medium becomes idle before attempting to transmit. However, even with carrier sensing, collisions can still occur if two devices sense the medium as idle and begin transmitting at the same time.

### **Types of CSMA Protocols:**
There are two primary types of CSMA protocols to handle what happens when a collision occurs:
- **CSMA/CD (Collision Detection)** – Used in **wired** networks.
- **CSMA/CA (Collision Avoidance)** – Used in **wireless** networks.

---

### **CSMA/CD (Carrier Sense Multiple Access with Collision Detection)**

**CSMA/CD** is a refinement of CSMA used primarily in **Ethernet (wired networks)**. It not only senses the carrier but also detects if a **collision** has occurred during data transmission.

#### Key Steps in CSMA/CD:
1. **Carrier Sense**: The device listens to the channel to check if it’s idle or busy.
2. **Transmit**: If the channel is idle, the device begins transmitting data.
3. **Collision Detection**: While transmitting, the device also listens to the medium to detect any collisions (which happen when another device transmits at the same time).
   - A collision is detected if the signal on the wire is different from the expected signal.
4. **Jam Signal**: When a collision is detected, the device sends out a **jam signal** to notify all other devices on the network that a collision has occurred.
5. **Backoff and Retransmit**: After detecting a collision and sending the jam signal, the device stops transmitting and waits for a **random backoff time** before attempting to retransmit the data. The backoff time increases with each successive collision (this is known as **exponential backoff**).

#### Efficiency:
- CSMA/CD is **efficient for wired networks** with low to moderate traffic. However, as the network traffic increases, collisions also increase, reducing overall efficiency.
- **Collision detection** is only possible in wired networks, where devices can monitor the signal on the shared communication medium (like an Ethernet cable).

#### CSMA/CD Use Case:
- Used in **Ethernet (IEEE 802.3)** networks, which were the standard for wired LANs before the introduction of modern switching technology.
- With the advent of **full-duplex Ethernet** (where data can flow in both directions simultaneously without collisions), CSMA/CD is now mostly obsolete.

---

### **CSMA/CA (Carrier Sense Multiple Access with Collision Avoidance)**

**CSMA/CA** is used primarily in **wireless networks**, such as **Wi-Fi (IEEE 802.11)**, where it’s difficult or impossible to detect collisions due to the nature of wireless transmission. Instead of detecting collisions, **CSMA/CA** tries to **avoid collisions** before they happen.

#### Why Collision Detection is Difficult in Wireless Networks:
- Wireless networks often suffer from the **hidden node problem**, where a device cannot hear transmissions from other devices because they are out of range, even though those devices may be communicating with the same router or access point.
- Unlike in wired networks, a device can't listen while transmitting, which makes detecting collisions in real-time difficult or impossible.

#### Key Steps in CSMA/CA:
1. **Carrier Sense**: The device listens to the channel to check if it's idle. If the channel is busy, the device waits for a random backoff period before trying again.
2. **Collision Avoidance Mechanism**:
   - **RTS/CTS (Request to Send / Clear to Send)**: To further reduce the chance of collisions, CSMA/CA may use a handshake mechanism. Before sending data, the sender device sends an **RTS** (Request to Send) signal to the receiver. If the receiver is ready to accept the transmission, it replies with a **CTS** (Clear to Send) signal. Once the sender receives the CTS, it knows that the channel is clear, and it proceeds with the data transmission.
3. **Transmit**: Once the device senses the channel is idle and/or receives the CTS signal, it begins transmitting the data.
4. **Acknowledgment**: After the data is successfully transmitted, the receiver sends an acknowledgment (ACK) to confirm that the data was received correctly.

#### Efficiency:
- CSMA/CA is more **complex** than CSMA/CD due to the added mechanisms like **RTS/CTS** and the acknowledgment process, but it is more suitable for **wireless networks** where collisions are harder to detect.
- It's not as efficient as CSMA/CD for heavy traffic because the RTS/CTS mechanism introduces some overhead, but it significantly reduces the chances of collisions.

#### CSMA/CA Use Case:
- Used in **Wi-Fi (IEEE 802.11)** wireless LANs, which rely on CSMA/CA to manage the sharing of the wireless spectrum and to avoid collisions between wireless devices.

---

### **Comparison: CSMA/CD vs. CSMA/CA**

| Feature              | **CSMA/CD**                                   | **CSMA/CA**                                   |
|----------------------|-----------------------------------------------|-----------------------------------------------|
| **Main Application**  | **Wired networks** (e.g., Ethernet)           | **Wireless networks** (e.g., Wi-Fi)           |
| **Collision Handling**| **Detects collisions** after they happen      | **Avoids collisions** before they happen      |
| **Collision Mechanism**| Monitors the wire for collisions during transmission | Uses RTS/CTS and waiting periods to avoid collisions |
| **Efficiency**        | High in low-traffic, wired networks           | Best suited for wireless, where collisions are hard to detect |
| **RTS/CTS**           | Not used                                      | Optional mechanism to reduce collisions       |
| **Backoff**           | Uses exponential backoff to retransmit data after collisions | Uses random backoff after sensing a busy channel |

---

### **Key Differences:**

1. **Collision Detection vs. Collision Avoidance**:
   - **CSMA/CD** detects collisions and then takes steps to recover from them, while **CSMA/CA** tries to prevent collisions before they occur.
  
2. **Wired vs. Wireless**:
   - **CSMA/CD** is suited for **wired** networks where it is possible to detect collisions by monitoring the wire.
   - **CSMA/CA** is suited for **wireless** networks where detecting collisions is difficult, so avoidance strategies are used.

3. **Performance in Different Environments**:
   - **CSMA/CD** is effective in wired networks with low to moderate traffic, but its efficiency drops as traffic increases due to more frequent collisions.
   - **CSMA/CA** is better for wireless networks, but it introduces more overhead due to the additional mechanisms like **RTS/CTS**.

---

### **Conclusion**:
- **CSMA/CD** is designed for **wired** networks like Ethernet, where collisions can be detected and resolved through retransmission.
- **CSMA/CA** is designed for **wireless** networks like Wi-Fi, where avoiding collisions is critical since detecting them is impractical.
- While CSMA/CD has largely become obsolete with modern full-duplex Ethernet and switching, **CSMA/CA** remains a core protocol in wireless communications.

# References
###### Information
- date: 2024.10.06
- time: 20:22