---
Title: "Power Distribution in a drone"
Status: 
marker: 
tags: 
Date: "2025.10.06"
Time: "05:54"
---
## **Power Distribution in a Drone**
The **Power Distribution System (PDS)** in a drone ensures that electrical power from the **battery** is distributed evenly and efficiently to all components such as **motors**, **ESCs**, **flight controller**, **camera**, and **LEDs**.
This is primarily managed by a **Power Distribution Board (PDB)** or an integrated **power management system**.

---

### **Example of Power Distribution**

**Drone Configuration:**

* Battery: **4S LiPo (14.8V)**
* Components: 4 × Motors, 4 × ESCs, Flight Controller, Camera, LEDs

**Distribution Setup:**

* Each **motor** is connected to an **ESC**, and every ESC is connected to the **PDB**.
* The **PDB** distributes full **battery voltage (14.8V)** to each ESC.
* The **Flight Controller** is powered through a **voltage regulator** on the PDB that steps down voltage (e.g., from 14.8V to 5V).
* Additional components (camera, LEDs, telemetry modules) receive voltage through separate **regulated outputs** (5V, 9V, or 12V).

---

### **Equal Power Distribution**

To maintain stable flight and balanced thrust:

* Power must be **equally distributed** across all ESC–motor pairs.
* Voltage drops between lines should be minimized.
* The PDB ensures each motor receives consistent voltage for uniform performance.

---

### **PDB Functions**

| Function                  | Description                                                  |
| ------------------------- | ------------------------------------------------------------ |
| **Centralized Power Hub** | Connects battery to ESCs, flight controller, and accessories |
| **Voltage Regulation**    | Steps down or filters voltage for sensitive electronics      |
| **Simplified Wiring**     | Reduces clutter by combining multiple power lines            |
| **Protection**            | Some boards include fuses or capacitors to prevent spikes    |

---

### **Simplified Layout**

$$ \text{Battery (14.8V)} \rightarrow \text{PDB} \rightarrow \text{ESCs} \rightarrow \text{Motors} $$
and
$$ \text{PDB Regulators} \rightarrow \text{Flight Controller, Camera, LEDs} $$





# References


###### Information
- date: 2025.10.06
- time: 05:54