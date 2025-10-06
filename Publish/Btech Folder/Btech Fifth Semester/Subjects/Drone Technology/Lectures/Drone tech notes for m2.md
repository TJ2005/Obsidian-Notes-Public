---
Title: "Drone tech notes for m2"
Status: 
marker: 
tags: 
Date: "2025.10.06"
Time: "13:06"
---
# Drone tech notes for m2

## Transmitter
- electronic device
- uses radio waves
	- common frequencies are as follows
		- 27mhz
		- 72mhz
		- 433mhz
		- 900mhz
		- 1.3ghz
		- 2.4ghz
- Translates the pilots commands into electronic signals for multi rotor
- has channeling individual actions sent to aircraft

## Receiver
- Electronic end
- Uses radiow aves
- Other end receiver of transmitter
- **De modulates** the signal to extract baseband command
- converted to digital format


## Process block
- user moves joystick
- transmitter **modulates** and sends a RF Signal 
	- Pulse width modulation
	- Pulse position modulation
- The receivers antenna captures the RF Signal
- receiver **Demodulates** the signal
- signal is converted into digital signal
- Sent to flight controller
- Flight controller processes and controls the motor speed to do different kind of movements.

Example Forward pitch signal is received by the flight controller
- Increases rear speed motor
- Reduces front motors

## Flight controller
- CPU of drone
- **Functions**
	- Stabilization
	- Navigation
	- Command Exec
	- Sensor Integration
	- Telemetry and Comms
- Types of FC
	- Basic
		- Simple manual flight
	- Intermediate
		- GPS Navigations
		- Altitude Hold
		- Return to home
	- Advanced
		- Integrate multiple sensors
		- Integrate Obstruction Detection
	- ![[Pasted image 20251006131754.png|center]]
![[Pasted image 20251006131804.png|center]]


Functions of a flight controller (PX4) • A flight controller is the central processing unit of a drone that regulates its movement, stability, and navigation. 1.Attitude Stabilization (Auto-Leveling & Orientation Control) • Uses gyroscope and accelerometer (IMU) to maintain yaw, pitch, and roll stability. • Automatically adjusts motor speeds to counteract disturbances (e.g., wind). • Ensures smooth and stable flight in manual and autonomous modes. • Essential for hovering, takeoff, and landing precision. Suyog V Pande MPSTME Shirpur Campus Functions of a flight controller (PX4) 2. Motor Control & Throttle Management • Sends PWM signals to Electronic Speed Controllers (ESCs) to adjust motor speeds. • Regulates thrust distribution for different maneuvers (e.g., climbing, turning). • Enables precise altitude hold and directional movement. • Ensures efficient power management for better flight endurance. 3. Sensor Data Processing & Fusion • Collects real-time data from IMU, GPS, barometer, and LiDAR. • Uses sensor fusion algorithms to improve flight accuracy. • Enhances navigation precision, even in GPS-denied environments. • Helps in collision avoidance and terrain-following applications. Suyog V Pande MPSTME Shirpur Campus Functions of a flight controller (PX4) 4. Autonomous Navigation & GPS Integration • Processes GPS waypoints for autonomous missions (e.g., surveying, inspections). • Assists in return-to-home (RTH) and fail-safe operations. • Enables long-range autonomous flights for mapping and monitoring tasks. • Improves flight safety by preventing loss of control. 5. Communication & Telemetry Management • Exchanges real-time data with ground control stations (GCS) via telemetry modules. • Sends live flight parameters like altitude, speed, and battery status. • Allows remote monitoring and control via radio or WiFi links. • Supports mission planning and real-time adjustments for drone


![[Pasted image 20251006131908.png|center]]
![[Pasted image 20251006131920.png|center]]
![[Pasted image 20251006131938.png]]
# References


###### Information
- date: 2025.10.06
- time: 13:06