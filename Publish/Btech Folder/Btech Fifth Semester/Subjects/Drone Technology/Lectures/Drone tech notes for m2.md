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


# References


###### Information
- date: 2025.10.06
- time: 13:06