---
Title: Computer Networks Lecture 5
Status: 
marker: 
tags: 
Date: 2024.07.29
Time: 10:54
---
# Computer Networks Lecture 5

# Index

- [DXD and RXD](#dxd-and-rxd)
- [Media Cable](#media-cable)
- [Ethernet](#ethernet)
- [RJ45](#rj45)
- [HUBS and Switches](#hubs-and-switches)
- [How to Get More than Hub Count](#how-to-get-more-than-hub-count)
- [Cable, Node, Switch, Hub](#cable-node-switch-hub)
- [Why Layering is Required in Networking](#why-layering-is-required-in-networking)
- [Homework](#homework)
- [References](#references)

## Main Topics

### [DXD and RXD](#dxd-and-rxd)
- **DXD (Data Exchange Driver)**: Typically refers to components responsible for handling data exchange between devices or systems, such as USB communications and serial ports.
- **RXD (Receive Data)**: The line used to receive data in serial communication, part of the RS-232 standard, working alongside the TXD (Transmit Data) line.

### [Media Cable](#media-cable)
- **Media Cable**: The physical medium used for data transfer between devices. Examples include:
  - **Twisted Pair Cable**: Commonly used in Ethernet networks (e.g., Cat5, Cat5e, Cat6).
  - **Coaxial Cable**: Used in older Ethernet networks and for cable internet.
  - **Fiber Optic Cable**: Uses light to transmit data, enabling high-speed transfers over long distances.

### [Ethernet](#ethernet)
- **Ethernet**: A set of networking technologies used in local area networks (LANs), defined by the IEEE 802.3 standard.
  - Operates at the Data Link Layer (Layer 2) of the OSI model.
  - Utilizes MAC addresses for hardware identification.

	### [RJ45](#rj45)
- **RJ45 (Registered Jack 45)**: A standardized network interface for connecting Ethernet cables.
  - **Diagram of 8 Pins**:
    - **Pin 1**: Transmit Data+ (TD+)
    - **Pin 2**: Transmit Data- (TD-)
    - **Pin 3**: Receive Data+ (RD+)
    - **Pin 4**: Unused (often used for Power over Ethernet)
    - **Pin 5**: Unused (often used for Power over Ethernet)
    - **Pin 6**: Receive Data- (RD-)
    - **Pin 7**: Unused
    - **Pin 8**: Unused

### [HUBS and Switches](#hubs-and-switches)
- **HUBS**:
  - Operate at the Physical Layer (Layer 1) of the OSI model.
  - Broadcast data to all ports, leading to potential collisions.
  - **Limitations**: Limited by the number of ports (typically 4 to 24).

- **Switches**:
  - Operate at the Data Link Layer (Layer 2) of the OSI model.
  - Use MAC addresses to forward data only to the intended recipient, reducing collisions and enhancing network performance.
  - **Advantages**: Support more devices and provide better performance compared to hubs.

### [How to Get More than Hub Count](#how-to-get-more-than-hub-count)
- **Daisy Chain Hubs**: Connect multiple hubs in series, though this can lead to increased network collisions and degraded performance.
- **Use Switches**: Replace hubs with switches to connect more devices and improve network performance.

### [Cable, Node, Switch, Hub](#cable-node-switch-hub)
- **Cable**: The physical medium connecting devices in a network.
- **Node**: Any device connected to a network, such as computers, printers, or network storage.
- **Switch**: Connects multiple nodes and uses MAC addresses to forward data to the correct destination.
- **Hub**: A basic networking device connecting multiple nodes but broadcasting all data to all ports.

### [Why Layering is Required in Networking](#why-layering-is-required-in-networking)
1. **Functions Preferred at a Lower Layer May Be Ignored by a Higher Layer**:
   - Allows abstraction and modularity in network design, with each layer functioning independently. Example: TCP handles reliable delivery, while IP handles routing.

2. **Easy to Implement Networking Stack**:
   - Simplifies the development and troubleshooting of network protocols by allowing developers to focus on specific layers.

3. **Technologies Independence Can Be Maintained**:
   - Ensures interoperability between different hardware and software, and allows integration of new technologies without changing the entire network stack. Example: Different physical media (Ethernet, Wi-Fi) can be used without altering higher layers.

## [Homework](#homework)
- **Check TCP/IP Implementation in sys32**:
  - Locate the TCP/IP implementation files in Windows (usually `C:\Windows\System32`).
  - Examine files like `tcpip.sys` to understand TCP/IP stack implementation in Windows.

## [References](#references)
1. **Windows Internals 7th Edition by Mark Russinovich, Microsoft Press**
2. **Linux Network Internals**

---

### Commands and Examples

- **Checking TCP/IP Configuration in Windows**:
  ```bash
  ipconfig /all
  netstat -an
  ```

- **Viewing TCP/IP Implementation Files in Windows**:
  ```powershell
  dir C:\Windows\System32\drivers\tcpip.sys
  ```

- **Analyzing Network Interfaces in Linux**:
  ```bash
  ifconfig -a
  ip addr show
  ```

- **Monitoring Network Connections in Linux**:
  ```bash
  netstat -tuln
  ```

These commands offer insights into network configurations and active connections on both Windows and Linux systems. The homework involves exploring the TCP/IP stack to understand its implementation and functionality.