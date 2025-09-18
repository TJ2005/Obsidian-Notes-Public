---
Title: Thrust Dependency on motor speed and
Status: true
marker:
  - "[[Drones]]"
  - "[[Drone Technology Index]]"
tags:
Date: 2025.08.11
Time: 16:15
---
## Thrust Dependency on Properties

### KV Ratings
- **Definition:** KV (RPM per Volt) indicates how fast a motor spins for a given voltage.
- **Thrust Relationship:**
  - Higher KV → Higher RPM → **More thrust at lower torque** (for a given propeller).
  - Lower KV → Lower RPM → **More torque, better for larger propellers**.
- **Mathematical Insight:**
  $$
  \text{RPM} = \text{KV} \times \text{Voltage (V)}
  $$
  - Thrust ($T$) is proportional to RPM$^2$ for a fixed propeller:
  $$
  T \propto (\text{KV} \times V)^2
  $$
  - Higher KV motors require smaller propellers to avoid overloading the ESC/motor.

---

### Propellers

#### Propeller Count
- **More Propellers:**
  - Distributes thrust across multiple motors, reducing load per motor.
  - Increases total thrust but may reduce efficiency due to aerodynamic interference.
- **Fewer Propellers:**
  - Each propeller must generate more thrust, requiring higher KV or larger propellers.

#### Propeller Shape
- **Pitch:**
  - Higher pitch → More thrust per revolution but requires more torque (lower efficiency at low speeds).
  - Thrust ($T$) for a propeller:
  $$
  T \propto (\text{RPM}^2 \times \text{Diameter}^4) \times \text{Pitch}
  $$
- **Diameter:**
  - Larger diameter → More air displaced → **Higher thrust** (but requires more torque).
- **Blade Shape:**
  - **Narrow/Long Blades:** Better for high-speed drones (less drag, more efficient at high RPM).
  - **Wide/Short Blades:** Better for low-speed, high-thrust applications (e.g., lifting heavy payloads).

#### Propeller Material
- **Stiffer Materials (e.g., Carbon Fiber):**
  - Less flex → More efficient thrust generation at high RPM.
- **Flexible Materials (e.g., Plastic):**
  - More flex → Loss of thrust at high RPM but more durable for crashes.

#### Blade Count
- **More Blades:**
  - Smoother thrust, better for stability and lifting heavy payloads.
  - Increases drag and reduces top speed.
- **Fewer Blades:**
  - Less drag → Higher top speed but less stable thrust.

---

### References
- Date: 2025.08.11
- Time: 16:15
- Sources: Aerodynamics principles, drone motor/propeller datasheets, and RC community resources.