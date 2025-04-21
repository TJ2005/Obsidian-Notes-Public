---
Title: Signals & Systems lecture 3
Status: true
marker:
  - "[[Memory Register]]"
  - "[[bits]]"
  - "[[bytes]]"
  - "[[nibble]]"
  - "[[Intel]]"
  - "[[AMD]]"
  - "[[ARM]]"
  - "[[Endianness]]"
  - "[[Slab Servers]]"
tags: 
Date: 22-07-2024
Time: 10:22
---
# Computer Networking Lecture 3

## Index
- [Content](#Storage-Algorithm)
  - [How is File Saved in Memory Register](#how-is-file-saved-in-memory-register)
  - [Bits, Bytes, and Nibbles](#bits-bytes-and-nibbles)
  - [LSB, MSB](#lsb-msb)
  - [Intel and AMD](#intel-and-amd)
  - [Motorola Process](#motorola-process)
  - [ARM Processor](#arm-processor)
- [Endianness](##Endianness)
  - [Little Endian](#little-endian)
  - [Big Endian](#big-endian)
  - [Slab Servers](#slab-servers)
  - [Conversion of Little Endian to Big Endian](#conversion-of-little-endian-to-big-endian)
- [References](#references)

# Storage Algorithm
- **Files and Memory Registers:** Files are saved as bytes in memory registers. The operating system and file system manage byte allocation, and data is stored in binary format.

- **Bits, Bytes, and Nibbles:**
  - **Bit:** The smallest data unit, represented as 0 or 1.
  - **Nibble:** 4 bits, representing 16 values (0-15).
  - **Byte:** 8 bits, representing 256 values (0-255).

- **LSB and MSB:**
  - **LSB (Least Significant Bit):** The bit with the lowest value, at the far right.
  - **MSB (Most Significant Bit):** The bit with the highest value, at the far left.
refer [[Storage Algorithm]]


# Endianness
Here are the short pointers for the note on endianness:

- **History:** Endianness derives from *Gulliver’s Travels*, where the terms "big-endians" and "little-endians" refer to which end of an egg people break.

- **How We Stumbled Upon This Creation:** The question of whether to store the most significant byte or the least significant byte first in memory led to the concept of endianness. Endianness reorders bytes, not bits.

- **MSB vs. LSB:**
  - **MSB (Most Significant Byte):** The highest power byte, e.g., `5` in `512` or `01` in `0xa011833d1`.
  - **LSB (Least Significant Byte):** The lowest power byte, e.g., `2` in `512` or `1` in `0xa011833d1`.

- **Why Study Endianness?** It is crucial for debugging and data interpretation across systems with different endian formats. The order of bytes affects memory inspection and data consistency.

- **Little Endian:** The least significant byte is stored first, at the lowest memory address (e.g., `0x12345678` is stored as `78 56 34 12`).

- **Big Endian:** The most significant byte is stored first, at the lowest memory address (e.g., `0x12345678` is stored as `12 34 56 78`).

- **Conversion:** To convert from little-endian to big-endian, reverse the byte order (e.g., `78 56 34 12` becomes `12 34 56 78`).

Refer [[Endianness]]


# Irrelevant to this lecture
### Slab Servers
Slab servers refer to a modular approach to building servers, where individual components (like CPU, memory, and storage) are housed in separate "slabs" or modules. This allows for easier upgrades and maintenance, as well as better cooling and power efficiency.

### [[Intel]] and [[AMD]]
Intel and AMD are two of the largest manufacturers of microprocessors. Both companies produce CPUs that use the x86 architecture, which is widely used in personal computers and servers. Intel processors are known for their performance in single-threaded applications, while AMD processors often offer better multi-threaded performance and value.

### [[ARM]] Processor
[[ARM]] (Advanced RISC Machine) processors are known for their power efficiency and are widely used in mobile devices, embedded systems, and increasingly in servers. ARM architecture supports both little-endian and big-endian formats, but little-[endian](#endianness) is more commonly used.

---

# DNS Resolving
1. **User Request:** A user requests a domain (e.g., `google.com`).

2. **Local Cache Check:** The computer checks its local cache for the domain's IP address.

3. **Query Name Server:** If not cached, the computer queries a name server (e.g., ISP’s DNS server).

4. **Recursive Lookup:** The name server queries other DNS servers if needed to find the authoritative DNS server for the domain.

5. **Receive IP Address:** The authoritative DNS server provides the IP address.

6. **Cache Result:** The IP address is cached by the name server and returned to the user’s computer.

7. **Access Website:** The user’s computer uses the IP address to access the website.

8. **DNS Cache Poisoning:** Attackers might manipulate DNS responses to poison caches with incorrect IP addresses.

This summarizes the DNS resolution process and potential security issue succinctly.

for more read [[DNS Resolving]] ( Diagram Available in the note )



## OSI Layer

The OSI (Open Systems Interconnection) model is a conceptual framework used to understand and implement network communications. It divides the communication process into seven distinct layers, each with specific functions and protocols.

### 1. Application Layer (A)
- **Function:** Provides network services directly to end-user applications.
- **Protocols:** HTTP, FTP, SMTP, POP3, SNMP, DNS.
- **Details:** This layer interacts with software applications to implement a communicating component. It provides various services such as file transfers, email, and network data sharing.

### 2. Presentation Layer (P)
- **Function:** Translates, encrypts, and compresses data.
- **Protocols:** SSL/TLS, JPEG, MPEG.
- **Details:** The presentation layer formats or translates data for the application layer based on the syntax or semantics that the application accepts. It handles data encryption and decryption to ensure privacy and compression to reduce the amount of data that needs to be transmitted.

### 3. Session Layer (S)
- **Function:** Manages sessions between applications.
- **Protocols:** NetBIOS, RPC, SQL.
- **Details:** This layer establishes, manages, and terminates connections between applications. It controls the dialogues (connections) between computers, establishing, managing, and terminating the connections.

### 4. Transport Layer (T)
- **Function:** Ensures end-to-end communication, error checking, and data flow control.
- **Protocols:** TCP, UDP.
- **Details:** The transport layer provides reliable, transparent transfer of data between end systems. It is responsible for error detection and correction, ensuring complete data transfer. It also manages flow control to prevent network congestion.

### 5. Network Layer (N)
- **Function:** Determines the best physical path for data to travel.
- **Protocols:** IP, ICMP, IGMP.
- **Details:** The network layer controls the operation of the subnet, deciding which physical path the data should take based on network conditions, priority of service, and other factors. It routes packets from the source to the destination.

### 6. Data Link Layer (D)
- **Function:** Provides node-to-node data transfer and handles error correction from the physical layer.
- **Protocols:** Ethernet, PPP, Switches, Bridges.
- **Details:** The data link layer establishes and terminates a connection between two physically connected devices. It breaks packets into frames and transmits them, ensuring error-free data transfer. It also manages physical addressing and controls access to the physical medium.

### 7. Physical Layer (P)
- **Function:** Transmits raw bit stream over the physical medium.
- **Protocols:** Ethernet cables, USB, Bluetooth, Fiber optics.
- **Details:** The physical layer is concerned with the transmission and reception of the unstructured raw bit stream over a physical medium. It deals with the physical connection to the network and includes elements like cabling, switches, and network interface cards (NICs).

## TCP IP Layer


## References
- [Operating System Concepts by Abraham Silberschatz](https://www.wiley.com/en-us/Operating+System+Concepts%2C+10th+Edition-p-9781119456339)
- [Computer Organization and Design by David A. Patterson and John L. Hennessy](https://www.elsevier.com/books/computer-organization-and-design-arm-edition/patterson/978-0-12-801733-3)
- [ARM Architecture Reference Manual](https://developer.arm.com/documentation/ddi0100/i/)
- [Intel 64 and IA-32 Architectures Software Developer's Manual](https://software.intel.com/content/www/us/en/develop/articles/intel-sdm.html)
- [AMD Developer Guides, Manuals &

 ISA Documents](https://developer.amd.com/resources/developer-guides-manuals/)
- [IEEE Xplore Digital Library](https://ieeexplore.ieee.org/)
- [RFC 791: Internet Protocol](https://tools.ietf.org/html/rfc791)

Personal References
- [[DNS Resolving]]
- [[Endianness]]

