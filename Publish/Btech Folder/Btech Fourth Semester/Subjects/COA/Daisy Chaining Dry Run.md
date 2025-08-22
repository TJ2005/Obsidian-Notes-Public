[[Computer Organization and Architecture Lecture 11#Daisy Chaining method]]
### Assumptions:
- We have **4 devices**: Device 1, Device 2, Device 3, Device 4, and a **Bus Arbiter**.
- Device 3 is the one requesting bus access, and we’ll see how the arbitration works.
![[IMG-20250730000528765.png]]
### Initial Setup:

- All devices are initially in a **waiting state** for the bus (no device has access yet).
- The Bus Arbiter manages bus access requests.

### Step-by-Step Process:

1. **Device 3 Requests Access (BRQ)**:
    
    - Device 3 needs access to the bus. It sends a **Bus Request (BRQ)** to the Bus Arbiter via the chain.
    - The Bus Request travels through Device 4 → Device 3 → Device 2 → Device 1 → Bus Arbiter.
2. **Bus Arbiter Receives the Request**:
    
    - The **Bus Arbiter** checks the chain and sees that Device 3 is requesting access. It then sends a **Bus Grant (BGT)** signal back to Device 3.
    - Device 3 is granted permission to use the bus.
3. **Bus Grant Propagates Back Through the Chain**:
    
    - The **Bus Grant (BGT)** travels from the Bus Arbiter to Device 1 → Device 2 → Device 3.
    - Now Device 3 is allowed to use the bus. It starts transmitting its data or performing the task it needs on the bus.
4. **Device 3 is Using the Bus**:
    
    - While Device 3 is using the bus, Device 1, Device 2, and Device 4 are **idle**. They cannot use the bus unless the Bus Arbiter grants them access after Device 3 releases it.
5. **Device 3 Finishes Using the Bus and Releases the Bus (SACK)**:
    
    - Once Device 3 is done, it sends a **Bus Acknowledgment (SACK)** signal to the Bus Arbiter indicating it has completed its task.
    - This **releases the bus** for other devices to use.
6. **Next Device Requests the Bus**:
    
    - Let’s say Device 2 is the next one to need the bus. It will now send a **Bus Request (BRQ)** signal.
    - The request is again passed along the chain: Device 4 → Device 3 → Device 2 → Bus Arbiter.
    - The Bus Arbiter sees Device 2's request and sends a **Bus Grant (BGT)** signal, allowing Device 2 to use the bus.
7. **Device 2 Uses the Bus**:
    
    - Device 2 now uses the bus, while Device 1 and Device 3 are idle until their turn.
8. **Cycle Repeats**:
    
    - The process repeats itself for each device in the chain. The device requesting access is granted the bus access, and after finishing, the bus is released.

### Visualizing the Chain (Flow):

- **Device 3 (Request) → Device 4 → Device 2 → Device 1 → Bus Arbiter (Grant) → Device 1 → Device 2 → Device 3 → Device 4 → Device 1 (Access complete)**

This is how the Daisy Chained Bus Arbitration allows multiple devices to take turns accessing the bus without conflict.