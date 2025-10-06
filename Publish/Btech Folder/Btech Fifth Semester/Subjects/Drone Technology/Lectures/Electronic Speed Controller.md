---
Title: Electronic Speed Controller
Status: 
marker:
  - "[[Drone Technology Index]]"
tags: 
Date: 2025.08.11
Time: 16:24
---
## **Electronic Speed Controller (ESC) in Drone Technology**

### **1. Current Handling**
- **Current Draw:** ESCs must handle the maximum current drawn by the motor, especially during rapid acceleration or heavy loads.
- **Overcurrent Risks:** Exceeding current limits can damage the ESC or motor.
- **Sizing Rule:** ESC should be rated **10–20% higher** than the motor’s maximum current to ensure safety and efficiency.

### **2. Signal Reception**
- **Input Signals:** Receives commands from the flight controller (e.g., PWM, DShot, or CAN bus).
- **Signal Types:** Analog (PWM) or digital (DShot, OneShot) for faster response and lower latency.

### **3. Signal Processing**
- **Microcontroller Role:** Processes input signals to control motor speed and direction.
- **Firmware:** Customizable firmware (e.g., BLHeli, SimonK) for performance tuning.

### **4. Motor Control**
- **Commutation:** Manages the timing of motor phase switching for smooth operation.
- **Brake Function:** Some ESCs support active braking for quicker motor stops.

### **5. Feedback Mechanism**
- **Telemetry:** Advanced ESCs provide real-time data (RPM, voltage, current, temperature) to the flight controller.
- **Sensorless vs. Sensored:** Sensorless ESCs estimate rotor position; sensored ESCs use Hall sensors for precision.

### **6. Protection Systems**
- **Overcurrent Protection:** Cuts power if current exceeds safe limits.
- **Temperature Protection:** Shuts down or throttles if overheating is detected.
- **Low-Voltage Cutoff:** Prevents battery over-discharge.

### **7. ESC Sizing and Weight**
- **Size Variants:** Ranges from micro (5A) to large (100A+) for different drone classes.
- **Weight Impact:** Larger ESCs add weight but are necessary for high-power setups.

### **8. ESC Weight Classes and Uses**
| **Class**       | **Current Rating** | **Typical Use**               |
|------------------|--------------------|-------------------------------|
| Micro (5–20A)    | 5–20A              | Tiny whoops, indoor drones     |
| Mini (20–40A)    | 20–40A             | 250–450mm racing drones        |
| Standard (40–80A)| 40–80A             | 5–7" freestyler/cinematic drones|
| Heavy-Duty (80A+)| 80A+               | Large cinematography/agricultural drones |

### **9. Voltage Regulation**
- **BEC (Battery Eliminator Circuit):** Provides regulated voltage (5V/12V) for flight controllers and accessories.
- **UBEC vs. LBEC:** UBEC (switching) is more efficient; LBEC (linear) is simpler but less efficient.

### **10. Calibration**
- **Throttle Range Calibration:** Ensures the ESC recognizes the full throttle range from the transmitter.
- **Firmware Updates:** Regular updates improve performance and add features.

### **11. Propeller Pitch and ESCs**
- **Pitch Impact:** Higher pitch propellers draw more current; ESC must be sized accordingly.
- **Efficiency:** Matching ESC/motor/propeller combo optimizes thrust and battery life.

### **12. Battery Compatibility**
- **LiPo vs. Li-Ion:** ESCs must support the battery’s voltage range (e.g., 3S–6S LiPo).
- **Voltage Ratings:** Ensure ESC voltage rating matches the battery (e.g., 4S ESC for 14.8V batteries).

### **13. Additional Considerations**
- **Waterproofing:** Some ESCs are coated for outdoor/rainy conditions.
- **Mounting:** Secure mounting reduces vibrations and electrical noise.
- **Cooling:** Heat sinks or active cooling for high-performance setups.

---

## **Electronic Speed Controller (ESC) and Power Distribution Board (PDB)**

---

### **Electronic Speed Controller (ESC)**

The **Electronic Speed Controller (ESC)** is an electronic circuit that **controls the speed, direction, and braking of the drone’s motors**.
It acts as the interface between the **battery, flight controller, and motors**, converting control signals into variable motor speeds.

---

### **Key Parameters of ESC**

#### **1. Current Rating**

* Indicates the **maximum current (in Amps)** the ESC can handle safely.
* If a motor draws more current than the ESC’s rating, the ESC can **overheat or fail**.
* Always choose an ESC rated **10–20% higher** than the motor’s maximum current draw.

$$ I_{\text{ESC}} \geq 1.2 \times I_{\text{motor max}} $$

---

#### **2. Voltage Compatibility**

* The ESC must match the **battery voltage** (number of LiPo cells).
  Example: A 3S LiPo = 11.1V, 4S = 14.8V, 6S = 22.2V
* Using an ESC below its voltage range causes **malfunction**; exceeding it causes **burnout**.

---

#### **3. Propeller Size**

* Larger propellers require **higher torque** → draw **more current**.
* If the propeller is too large for the ESC–motor combination, it can cause **ESC overheating** or **current overload**.

---

### **Working of ESC**

#### **1. Signal Reception**

The **flight controller** sends a **PWM (Pulse Width Modulation)** signal to the ESC corresponding to the throttle command from the transmitter.

#### **2. Signal Processing**

The ESC reads and interprets this PWM signal and converts it into **three-phase AC power** suitable for a brushless motor.

#### **3. Motor Control**

The ESC switches the current using **MOSFETs** in precise sequence to control motor speed and direction.
Higher PWM input → higher RPM output.

#### **4. Feedback Mechanism**

Advanced ESCs monitor **Back Electromotive Force (BEMF)** or use **Hall sensors** to track motor speed and adjust output dynamically for smoother response.

#### **5. Overcurrent and Temperature Protection**

Modern ESCs include protection circuits that shut down or throttle performance if:

* Current exceeds safe limits
* Temperature crosses critical thresholds

This prevents **component damage** and **flight failure**.

![[Pasted image 20251006053925.png|center]]
---

### **How to Choose an ESC for Drones**

When selecting an ESC, consider:

| Factor                           | Description                                                                            |
| -------------------------------- | -------------------------------------------------------------------------------------- |
| **Motor Compatibility**          | Match ESC’s specs with motor’s voltage and current draw                                |
| **Voltage Rating**               | Match the ESC to the drone’s LiPo battery (e.g., 3S, 4S, 6S)                           |
| **Current Rating**               | Choose an ESC rated 10–20% higher than max motor current                               |
| **Onboard BEC**                  | If ESC includes a Battery Eliminator Circuit (BEC), it can power the flight controller |
| **Size and Weight**              | Lightweight ESCs → better response; heavy ESCs → better heat handling                  |
| **Cooling and Heat Dissipation** | Heat sinks improve durability under continuous load                                    |

---

### **ESC Types**

#### **1. Brushed ESC**

Used for **brushed DC motors** (older or toy drones).

* **Working:** Controls voltage using PWM to vary motor speed.
* **Advantages:**

  * Simple and inexpensive
  * Easy to use (two-wire connection)
* **Disadvantages:**

  * Less efficient
  * Prone to wear due to brushes
  * Unsuitable for high-performance drones
* **Applications:** Toy drones, educational kits, prototypes.

---

#### **2. Brushless ESC**

Used with **Brushless DC (BLDC) motors**, which are standard in modern drones.

* **Working:** Converts DC input into 3-phase AC output using MOSFETs.
* **Advantages:**

  * High efficiency
  * Precise control and faster response
  * Low maintenance (no brushes)
* **Disadvantages:**

  * Slightly more complex circuitry
  * Requires correct motor–ESC pairing
* **Applications:** FPV drones, professional quadcopters, heavy-lift drones.

---

#### **3. OPTO ESC**

(OPTO = Optically Isolated)

* **Working:**
  Uses an **optocoupler** to isolate the signal circuit from the power circuit for noise-free operation.
  Does **not** have a built-in **BEC (Battery Eliminator Circuit)**.
* **Advantages:**

  * Prevents electrical noise from interfering with flight controller
  * Ideal for **high-voltage** or **high-power** systems
* **Disadvantages:**

  * Requires an **external 5V supply** to power the flight controller
* **Applications:**
  Large drones, industrial or heavy-duty UAVs.

---

#### **4. BEC ESC (Battery Eliminator Circuit ESC)**

* Includes an internal **voltage regulator** to power flight controllers and receivers (usually 5V or 6V).
* **Advantages:**

  * Simplifies wiring (no separate power module)
  * Lighter overall system weight
* **Disadvantages:**

  * Limited current output (usually 2–3A)
* **Applications:**
  Small to medium drones.


---

#### **5. BLHeli_32 High-Performance Brushless ESC**

A **high-end ESC** running **BLHeli_32 firmware**, based on a **32-bit microcontroller**.

* **Features:**

  * Advanced motor control precision
  * High PWM refresh rates for faster throttle response
  * Smooth motor operation and startup
  * Programmable parameters (timing, braking, direction)
* **Advantages:**

  * Improved performance, reliability, and telemetry support
  * Ideal for **FPV racing** and **cinematic drones**
* **Disadvantages:**

  * Costlier than standard ESCs
  * Requires firmware configuration and tuning
* **Applications:**
  Racing drones, aerial cinematography, professional UAVs.

![[Pasted image 20251006053847.png|center]]

---

### **Power Distribution Board (PDB)**
The **Power Distribution Board (PDB)** distributes electrical power from the battery to all major components — ESCs, flight controller, camera, and other accessories.

#### **Functions:**

1. **Centralized Power Management:**
   Connects battery to all ESCs and electronic systems.
2. **Voltage Regulation:**
   Provides step-down outputs (e.g., 12V, 5V) for different modules.
3. **Simplified Wiring:**
   Reduces cable clutter by serving as a single distribution hub.
4. **Safety:**
   Maintains consistent and equal voltage to all motors for balanced flight.

![[Pasted image 20251006053816.png|center]]

---

### **Steps to Calibrate an ESC**

1. **Turn on the transmitter** and set the throttle stick to **maximum**.
2. **Connect the LiPo battery** to the ESC power module.
3. With throttle still high, **disconnect and reconnect the battery**.
4. Wait for **beeping tones** that indicate throttle calibration mode.
5. When tones stop, **lower throttle to minimum** — ESC stores max and min throttle values.
6. ESCs emit confirmation beeps, indicating **successful calibration**.
7. Power cycle the drone before flight.

![[IMG-20251006053744114.png|center]]

---

### **Mermaid Diagram – ESC System Overview**

```mermaid
graph TD
A[Electronic Speed Controller (ESC)] --> B[Receives PWM Signal from Flight Controller]
A --> C[Converts DC → 3-Phase AC for Motors]
A --> D[Controls Motor Speed and Direction]
A --> E[Provides Protection and Feedback]

B --> B1[Signal Reception]
C --> C1[Signal Processing via MOSFETs]
D --> D1[Motor Control: Adjust RPM]
E --> E1[Feedback: BEMF or Sensors]
E --> E2[Overcurrent & Temperature Protection]

A --> F[ESC Types]
F --> F1[Brushed ESC]
F --> F2[Brushless ESC]
F --> F3[OPTO ESC]
F --> F4[BEC ESC]
F --> F5[BLHeli_32 ESC]

A --> G[Power Distribution Board (PDB)]
G --> G1[Distributes Power to ESCs]
G --> G2[Regulates Voltage for Components]
G --> G3[Ensures Equal Power Flow]
```

---

**Summary:**
The **Electronic Speed Controller** is vital in translating flight commands into motor response.
Choosing the correct **ESC type**, ensuring proper **voltage and current ratings**, and **calibrating** it correctly are essential for safe and stable drone operation.
The **PDB** complements it by efficiently distributing and regulating power to all drone subsystems.

### **References**
- **Date:** 2025.08.11
- **Time:** 16:24
- **Sources:** Drone community forums, manufacturer datasheets, and hobbyist guides.