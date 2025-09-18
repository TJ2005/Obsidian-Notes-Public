---
Title: Wireless Security
Status: true
marker:
  - "[[Network Security Index]]"
  - "[[Acid Properties]]"
tags:
Date: 2025.09.17
Time: 14:11
---
Here’s the **final, polished, and complete** summary of your class notes, ensuring **no information is lost** while keeping it concise and structured:

---

### **Why Wireless Networks Are Insecure**
- **Radio Waves**: Wireless networks use radio waves, which cannot be physically contained. Anyone within range can intercept the signal.

---

### **How Mobile Communication Works**

#### **1. Frequency Allocation**
- Frequencies are divided for **testing, commercial, private, and military** use.
- Each service provider gets **only 4-5 frequencies** and must accommodate all users within these.

#### **2. Base Station Role**
- Acts as a central hub in a network (e.g., a small town or local network).
- Manages **sending and receiving data** for multiple users/devices (e.g., 20 channels/systems).
- **Limited frequency bands** are available for communication.

#### **3. Time Division & Slot Allocation**
- The base station **creates time frames** with **multiple slots**.
- Users must **occupy/reserve slots** based on their data size.
- **Bidding for slots**: Users compete to reserve slots for their data transmission.

#### **4. Bandwidth & Capacity**
- **Bandwidth = Capacity**: The maximum data a channel can transmit at a time.
- **Example**: If a channel’s bandwidth allows **2 users** to transmit simultaneously, a third user must **wait** until a slot is free.
- If data is too large for a slot, the user must **wait for another slot** or reserve multiple slots.

#### **5. Frequency Usage**
- **One frequency for sending data**, **one frequency for receiving data**.
- **No dedicated frequency**: Users share frequencies dynamically.
- When you dial a number, your phone **requests a slot** in real-time to transmit data.

#### **6. Practical Example**
- **Telephone networks**: Service providers divide their limited frequencies into smaller bands.
- **No dedicated frequency per user**: Frequencies are shared among all users in the network.

---

Here’s a concise, pointer-style version of the notes:

---

### Mobile Telecommunication – Key Points

* Phones use **electromagnetic spectrum** (radio/microwave) for communication.
* Spectrum is **divided into bands**; allocated to operators, telecom, broadcast, Wi-Fi, etc.
* **Limited spectrum → shared among millions of users.**
* Sharing techniques:

  * **FDM (Frequency Division Multiplexing):** split spectrum into sub-bands.
  * **TDM (Time Division Multiplexing):** divide into time slots.
  * Often combined for efficiency.
* **Base station / cell tower**:

  * Manages uplink (send) & downlink (receive).
  * Assigns frequencies/timeslots.
  * Ensures users share limited capacity.
* **Call setup flow**:

  * Phone request → nearest tower → network locates callee → target tower → connection established in seconds.
* **Mobility & roaming**:

  * SIM first registers with a “home” tower/network.
  * Moving between towers updates location in operator’s database.
  * Leaving home network triggers roaming with foreign towers.
* **Databases (HLR/VLR)**:

  * Track registration, location, billing, usage.
  * Enable roaming and call routing.
* **Wireless channel characteristics**:

  * Open medium → no dedicated line per user.
  * Spectrum shared, so scheduling and multiplexing are essential.

---
