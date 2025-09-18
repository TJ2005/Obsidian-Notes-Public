---
Title: "Drone Technlogy Sensors"
Status: 
marker: 
tags: 
Date: "2025.09.15"
Time: "16:18"
---
# Drone Technlogy Sensors
### **ADXL335: Quick Reference Note**

#### **1. Key Pins**
| Pin | Function |
|-----|----------|
| **VCC** | Power (1.8V–3.6V) |
| **GND** | Ground |
| **X, Y, Z** | Analog outputs (0V–3.6V) |
| **ST** | Self-Test (connect to VCC to enable) |
| **VS** | Optional: Supply for ratiometric operation |

 

#### **2. Self-Calibration**
- **Zero-G Offset**:
  - Place sensor flat (Z-axis = 1g, X/Y = 0g).
  - Measure X, Y, Z outputs.
  - Adjust readings to match expected values (e.g., X/Y ≈ 1.5V, Z ≈ 1.8V for 3.3V VCC).
- **Sensitivity Check**:
  - Tilt sensor 90° (e.g., X-axis = 1g, Y/Z = 0g).
  - Verify output change (~300mV/g for 3.3V VCC).

 

#### **3. Important Factors**
- **Sensitivity**: ~300mV/g @ 3.3V VCC.
- **Bandwidth**: 0.5Hz–1.6kHz (adjust with external capacitors).
- **Noise**: Low-pass filter recommended for stable readings.
- **Mounting**: Secure firmly; avoid mechanical stress.
- **Power**: Use stable voltage; noise affects accuracy.

 
**Tip**: Always verify with datasheet for precise specs.


---
### **Gyroscope: Quick Reference Note**

---

#### **1. Key Pins (Generic MEMS Gyro, e.g., MPU6050)**
| Pin       | Function                     |
|-----------|------------------------------|
| **VCC**   | Power (3.3V/5V)              |
| **GND**   | Ground                       |
| **SCL**   | I2C Clock (for digital gyros)|
| **SDA**   | I2C Data (for digital gyros)|
| **X, Y, Z**| Analog/Digital Outputs       |
| **INT**   | Interrupt (for events)       |

---

#### **2. How It Works: Angular Momentum & Rotation**
- **Principle**: Gyroscopes measure **angular momentum** (conservation of rotational motion).
- **MEMS Gyro**: Uses **Coriolis effect**—vibrating masses detect rotation by sensing force perpendicular to motion.
- **Output**: Voltage/frequency change proportional to **angular velocity** (degrees/second or rad/s).
  - **Faster rotation → Higher output signal** (directly correlates with angular momentum change).
- **3-Axis Measurement**: Detects rotation around X (roll), Y (pitch), Z (yaw) axes.

---

#### **3. Relevance for Drones**
- **Stabilization**: Measures drift/tilt in real-time; adjusts motors to maintain balance.
- **Navigation**: Combines with accelerometer (IMU) for precise orientation (e.g., auto-leveling, GPS-free flight).
- **Wind/Spin Detection**:
  - Detects sudden angular changes (e.g., gusts causing roll/pitch).
  - Enables **auto-correction** (e.g., counter-rotating props to stabilize yaw).
- **Flight Modes**:
  - **Acro Mode**: Uses raw gyro data for aggressive maneuvers.
  - **GPS Hold**: Gyro + compass for position locking.

---
#### **4. Key Factors**
- **Sensitivity**: $mV/(°/s)$ or $LSB/(°/s)$ (check datasheet).
- **Drift**: Calibrate at startup; temperature affects accuracy.
- **Noise**: Use low-pass filters for smooth data.
- **Sampling Rate**: Higher = better for fast movements (e.g., 1kHz for racing drones).
- **Calibration**: Zero-rate offset adjustment (place on flat surface, record bias).

---
#### **5. Extra Context**
- **Complementary Filter**: Fuses gyro + accelerometer data to reduce drift.
- **Gimbal Control**: Gyros stabilize cameras in drones/photography.
- **Crash Prevention**: Detects uncontrolled spins (e.g., "turtle mode" in drones).

### **Magnetometer & Barometer (BMP388)**

---

**Magnetometer**
- **Purpose**: Measures Earth’s magnetic field for **heading/compass direction**.
- **How It Works**: Detects magnetic field strength/angle using **Hall-effect sensors** or **magnetoresistive elements**.
- **Key Pins**: I2C/SPI (SDA, SCL, CS), VCC, GND.
- **Drone Use**:
  - Compass for **yaw stabilization** (prevents drifting in GPS-denied areas).
  - Calibration needed to avoid interference (e.g., motors, metal frames).
- **Limitations**: Affected by electromagnetic noise; needs soft/hard iron calibration.

**Barometer (BMP388)**
- **Purpose**: Measures **air pressure** to estimate **altitude**.
- **How It Works**: Pressure changes with altitude (higher = lower pressure). BMP388 converts pressure to **meters above sea level** using built-in algorithms.
- **Key Pins**: I2C/SPI, VCC, GND.
- **Drone Use**:
  - **Altitude Hold**: Maintains height without GPS.
  - **Weather Prediction**: Detects pressure drops (e.g., storms).
- **Accuracy**: ±0.5m with temperature compensation.

---

### **GPS & Trilateration**
- **How GPS Works**: Uses **trilateration**—measures time delay from 4+ satellites to calculate 3D position (lat/long/altitude).
- **Key Pins**: UART/I2C (TX, RX), VCC, GND, antenna.
- **Drone Use**:
  - **Position Lock**: Hover, waypoint navigation.
  - **Return-to-Home (RTH)**: Failsafe if signal lost.
- **Limitations**: Needs clear sky; multipath errors in cities/forests.

---

### **Ultrasonic Sensor (HC-SR04)**
- **Purpose**: Imitates **bat echolocation**—measures distance via sound waves.
- **How It Works**:
  - **Transmitter**: Sends 40kHz pulse (piezoelectric crystal vibrates).
  - **Receiver**: Listens for echo; calculates distance using time delay.
- **Key Pins**: Trigger, Echo, VCC, GND.
- **Drone Use**:
  - **Low-Light Navigation**: Works in darkness (unlike optical sensors).
  - **Obstacle Avoidance**: Detects ground/walls (e.g., landing assist).
- **Limitations**:
  - **Low-End**: Inaccurate (>1cm error), affected by soft surfaces/air turbulence.
  - **Range**: ~2–400cm; useless in fog/rain (sound absorbs).
- **Piezoelectric Crystals**: Convert electrical pulses to ultrasound and vice versa.

---
**Why Use HC-SR04?**
- Cheap, lightweight, no light dependency (unlike LiDAR/cameras).
- **Alternative**: LiDAR for precision, but costs more.
# References


###### Information
- date: 2025.09.15
- time: 16:18