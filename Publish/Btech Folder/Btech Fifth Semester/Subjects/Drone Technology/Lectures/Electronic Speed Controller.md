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

### **References**
- **Date:** 2025.08.11
- **Time:** 16:24
- **Sources:** Drone community forums, manufacturer datasheets, and hobbyist guides.