### **Flow Control in Data Link Layer**

---
![[IMG-20241016141309636.png]]
**Flow control** is one of the key responsibilities of the **Data Link Layer** in the OSI model. It ensures that data is transferred efficiently between nodes (e.g., between routers or computers) without overwhelming the receiver. This is crucial because the sender and receiver may have different data processing speeds.

### **Data Link Layer Services**

The Data Link Layer is responsible for transferring data **frames** from one node to another over a network. To ensure proper transmission, it provides the following services:

1. **Framing**: Encapsulating the data into frames.
2. **Error Control**: Ensuring reliable transmission by detecting and correcting errors.
3. **Flow Control**: Managing the rate of data transmission between sender and receiver.
4. **Physical Addressing**: Using MAC addresses to identify the source and destination.
5. **Access Control**: Managing the use of the physical link in shared networks.

---

### **Flow Control Mechanism**

**Flow control** refers to the process of managing the rate at which the sender transmits data to ensure that the receiver can handle the data without becoming overwhelmed. There are several important aspects of flow control:

1. **Coordination**: It coordinates the amount of data that can be sent before receiving an acknowledgment from the receiver.
   
2. **Speed Matching**: It involves matching the speed of data transmission between sender and receiver, ensuring that the sender does not overwhelm the receiver with more data than it can process.
   
3. **Set of Procedures**: Flow control is a set of procedures that tells the sender how much data it can transmit before it must wait for an acknowledgment from the receiver.

4. **Receiver Limitations**: The receiver has a limited speed at which it can process incoming data and a limited amount of memory to store incoming packets. For example, the receiver's buffer space might be limited, and if it's filled up, the receiver can't accept more data until some data is processed.
   
5. **Feedback from Receiver**: The receiver must inform the sender when its capacity is reaching its limit. This request may ask the sender to slow down or stop transmitting for a temporary period.

---

### **Protocols in Flow Control**

The protocols used for flow control can be divided into two categories:

1. **Noiseless Channels**:
   - **Stop-and-Wait**: The sender sends one frame and waits for an acknowledgment before sending the next one. It is simple but inefficient for long-distance communication because the sender has to wait for each acknowledgment.
   - **Simplest Protocol**: This is a basic mechanism where the sender waits for an acknowledgment after every frame, ensuring that the receiver is ready for the next frame.

2. **Noisy Channels**:
   - **Stop-and-Wait ARQ**: Similar to Stop-and-Wait, but includes error detection and retransmission. If the frame or acknowledgment is lost, the sender resends the frame.
   - **Go-Back-N ARQ**: The sender can send several frames without waiting for an acknowledgment, but if an error is detected, it goes back to the last acknowledged frame and retransmits from there.
   - **Selective Repeat ARQ**: This protocol allows the sender to send multiple frames and only retransmits those that were lost or corrupted, rather than going back to the last acknowledged frame.

---

### **Diagram: Data Flow Between Two Routers**

The diagram depicts data flow between two routers:
- The routers are connected through data links, and flow control ensures that data sent from **Router 1** does not overwhelm **Router 2**.
- The receiver (Router 2) communicates with the sender (Router 1) about its capacity, adjusting the transmission speed and allowing smooth data transfer.

---

### **Summary**

- **Flow control** is a critical function in the Data Link Layer to ensure efficient and reliable communication.
- The sender is responsible for transmitting data frames, and flow control helps prevent the receiver from being overwhelmed by too much data at once.
- Protocols such as **Stop-and-Wait ARQ**, **Go-Back-N ARQ**, and **Selective Repeat ARQ** provide mechanisms to ensure error-free and controlled data transmission, especially in noisy channels.

This note covers the basics of flow control in the Data Link Layer, including the mechanisms and protocols used to manage the rate of data transmission effectively.