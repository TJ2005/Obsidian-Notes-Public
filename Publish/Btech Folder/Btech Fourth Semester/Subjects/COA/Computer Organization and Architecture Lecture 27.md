---
Title: Computer Organization and Architecture Lecture 9
Status: 
marker: 
tags: 
Date: 2025.01.24
Time: 13:10
---
Continued from [[Computer Organization and Architecture Lecture 8]]
# Bus Architecture and Master-Slave Communication Model

## Bus Architecture

A **bus** is a shared communication pathway used to transmit data, control signals, and addresses between the various components of a computer system. It acts as a communication backbone, enabling efficient data transfer between the CPU, memory, and I/O devices.

### Representation of Binary Data
- **Binary Signals:** 0's and 1's are represented as electrical signals.
  - 0: Typically assigned a voltage of 0 volts.
  - 1: Typically represented by a voltage (e.g., 2.5 volts).
- These signals form the basis of transmitting addresses, data, and control instructions across the bus.

---

### General Organization of a Bus

#### **Control Lines**
- These lines carry signals for **requests**, **acknowledgements**, and **metadata** related to the communication process.
- Examples:
  - **Memory Read**: Indicates data should be read from memory.
  - **Memory Write**: Signals data should be written to memory.
  - **I/O Read and Write**: Manages data transfer to/from peripherals.
  - **Handshake Ready**: Ensures the receiver is prepared for communication.
  - **Transfer Acknowledgement**: Confirms data transfer completion.
  - **Bus Request and Bus Grant**: Handles access to the bus when multiple devices are connected.
  - **Interrupt Request and Acknowledgement**: Handles interrupts and their resolutions.
  - **Clock Signal**: Synchronizes operations in synchronous communication.
  - **Reset Signal**: Resets the system or bus.

#### **Data Lines**
- Responsible for carrying information between components.
- Types of data carried:
  - Actual **data**.
  - **Addresses** of memory or I/O ports.
  - **Instructions** for processing.
- Typically **bidirectional**, allowing both read and write operations.

---

### Key Features of a Bus

1. **Shared Resource:**
   - The bus is a shared communication medium, requiring protocols to prevent conflicts.
   
2. **Bandwidth:**
   - Determines the amount of data that can be transmitted over the bus within a given time.

3. **Arbitration:**
   - Ensures that only one device communicates over the bus at any given time.
   - Common methods:
     - **Daisy-Chaining:** Priority-based arbitration using a chain of devices.
     - **Polling:** Central controller queries devices sequentially.

4. **Bus Communication:**
   - **Synchronous Bus:** Communication occurs based on a clock signal, ensuring timing consistency.
   - **Asynchronous Bus:** No clock signal; uses handshaking protocols for synchronization.

5. **Cross Talk:**
   - Occurs when two parallel lines in the bus interfere with each other, causing signal distortion and data errors.

---

### Types of Buses

1. **Data Bus:**
   - Transports actual data between components.
   - **Bidirectional**: Data flows in both directions (e.g., CPU <-> Memory).

2. **Address Bus:**
   - Carries the memory or I/O address being accessed.
   - Modern address buses are **bidirectional**, allowing dynamic memory allocation.

3. **Control Bus:**
   - Transmits control signals for operation management.
   - Examples:
     - Memory read/write, I/O read/write.
     - Handshake and transfer acknowledgements.
     - Interrupt handling and arbitration signals.

---

### Examples of Bus Standards

1. **System Bus:** 
   - Connects the CPU, memory, and system components.
   - Examples: PCI, AMBA.

2. **Peripheral Bus:** 
   - Connects external devices and peripherals.
   - Examples: USB, I2C, SPI.

---

## Master-Slave Architecture

### Definition
A hierarchical communication model where one device (master) controls one or more subordinate devices (slaves). It is commonly used in buses to manage data flow effectively.

### Roles in the Architecture

1. **Master:**
   - Initiates communication on the bus.
   - Sends commands and manages data flow.
   
2. **Slave:**
   - Responds to the master's commands.
   - Performs read/write operations as directed.

---

### Key Features

1. **Centralized Control:**
   - The master governs all operations, ensuring deterministic communication.
   
2. **Simplified Slave Devices:**
   - Slaves only execute the commands issued by the master, reducing their complexity.

3. **No Slave Arbitration:**
   - Only the master competes for bus control; slaves operate under its instructions.

---

### Communication Flow

1. The master sends a request specifying the operation, data, and address.
2. The slave acknowledges and performs the requested operation (e.g., read/write).
3. Control returns to the master for further operations.

---

### Examples of Master-Slave Protocols

1. **I2C (Inter-Integrated Circuit):**
   - Single master controls multiple slaves using unique addresses.
   
2. **SPI (Serial Peripheral Interface):**
   - The master selects a slave using chip-select lines for communication.

---

### Comparison: Bus vs. Master-Slave

| Aspect              | Bus Architecture                           | Master-Slave Architecture            |
|---------------------|--------------------------------------------|---------------------------------------|
| **Control**         | Shared communication among devices.        | Centralized control by the master.   |
| **Complexity**      | Requires arbitration for access control.   | Slaves are simpler in design.        |
| **Communication**   | Devices share a common pathway.            | Master initiates all communication.  |
| **Scalability**     | Limited by bus bandwidth.                  | Scales easily with unique slave IDs. |

---

## Advantages of Bus Architecture

1. **Easy Device Addition:**
   - New devices can be added without major architectural changes.
   
2. **Interchangeability:**
   - Peripherals can be moved between systems using the same bus standard.

3. **Cost-Efficiency:**
   - A single set of wires shared among multiple components.

---

## Disadvantages of Bus Architecture

1. **Communication Bottleneck:**
   - Limited bandwidth can reduce overall throughput.

2. **Speed Limitations:**
   - Factors like bus length, connected devices, and device latencies constrain maximum speed.

---

## Timing Diagram
- The timing diagram illustrates how signals flow and interact during a data transaction on the bus.
- Key signals shown: clock, request, acknowledgement, data transfer.

---

## Single Bus vs. Expansion Bus

1. **Single Bus:**
   - A single communication path shared by all devices in the system.

2. **Expansion Bus:**
   - Used to connect additional peripherals (e.g., an extension board).

---

## Advantages of Master-Slave Architecture

1. **Deterministic Communication:**
   - Predictable and controlled data flow.
   
2. **Simplified Slave Design:**
   - Reduces the complexity of individual components.

3. **Flexible Scalability:**
   - Easy to add new slave devices without altering the system architecture.

---

## Disadvantages of Master-Slave Architecture

1. **Single Point of Failure:**
   - If the master fails, the entire system can halt.

2. **Limited Performance:**
   - Communication bottlenecks when a single master controls multiple slaves.

---

### References
- Date: 2025.01.24
- Time: 13:10
Continued to [[Computer Organization & Architecture Lecture 10]]
