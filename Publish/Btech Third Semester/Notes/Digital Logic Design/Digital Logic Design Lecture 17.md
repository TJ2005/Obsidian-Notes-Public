---
Title: Digital Logic Design Lecture 17
Status: 
marker: 
tags: 
Date: 2024.10.01
Time: 10:42
---
### Digital Logic Design Lecture 17: Race Around Condition in JK Flip-Flop and Registers

#### Main Notes

**1. JK Flip-Flop Overview:**
- A **JK flip-flop** is a variation of the SR flip-flop with no invalid states. It has two inputs, **J** and **K**, and an output Q. 
- The flip-flop toggles the output based on the clock signal and the combination of inputs (J and K):
  - **J = 0, K = 0:** No change in output (Q remains unchanged).
  - **J = 0, K = 1:** Resets the output to 0 (Q = 0).
  - **J = 1, K = 0:** Sets the output to 1 (Q = 1).
  - **J = 1, K = 1:** Toggles the output (Q = not Q).

**2. Race Around Condition:**
- The **race around condition** occurs in JK flip-flops when **J = K = 1** and the flip-flop is triggered by a clock pulse with a long duration.
- During this time, the output toggles multiple times within the duration of a single clock pulse, leading to **unpredictable results** at the end of the clock pulse. 
- The main issue arises from the feedback loop, which keeps updating the output as long as the clock is active.

**3. Conditions for Race Around:**
   - Occurs in **level-triggered flip-flops** (usually in a positive or negative level clock system).
   - Triggered when **J = K = 1** and the clock pulse width is large enough to allow multiple toggling.

**4. Mitigation of the Race Around Condition:**
   - **Edge-triggered flip-flops:** The problem can be mitigated using **edge-triggered** flip-flops, which only respond to the clock's rising or falling edge, not its level.
   - **Master-Slave Flip-Flop:** One common solution is to use a **Master-Slave JK Flip-Flop**, where the first stage (master) is activated by the clock's leading edge, and the second stage (slave) is activated by the trailing edge, ensuring only one output change per clock pulse.
   - **Reducing Clock Pulse Width:** By reducing the clock pulse width, the race around condition can be prevented, as the pulse ends before the output toggles multiple times.

**5. Registers:**
   - **Registers** are groups of flip-flops used to store multiple bits of data.
   - Each flip-flop in a register stores one bit of data, and registers typically store 8, 16, 32, or 64 bits.
   - Registers can be **parallel in/parallel out (PIPO)**, **serial in/serial out (SISO)**, **serial in/parallel out (SIPO)**, or **parallel in/serial out (PISO)**, depending on how data is inputted or outputted.
   
**6. Use of JK Flip-Flops in Registers:**
   - JK flip-flops are often used in registers due to their versatility and ability to toggle, set, or reset based on input signals.
   - In **shift registers**, JK flip-flops are used in combination to shift data in a serial fashion across a series of clock pulses.
   
**7. Applications of Registers:**
   - **Data storage**: Registers temporarily hold data being processed by the CPU or other digital systems.
   - **Data transfer**: Registers facilitate data transfer between different parts of the system (such as between memory and processors).
   - **Counters**: JK flip-flop-based registers can be used in counters, which count the number of events or clock pulses.

### Operation of Master-Slave JK Flip-Flop

A **Master-Slave JK Flip-Flop** is designed to overcome the **race around condition** seen in level-triggered JK flip-flops. It consists of two JK flip-flops connected in series:

- **Master Flip-Flop** (the first stage): Activated by the **leading edge** of the clock.
- **Slave Flip-Flop** (the second stage): Activated by the **trailing edge** of the clock.

The key feature of this design is that it ensures the output changes only once during a clock cycle, even if the inputs remain unchanged, thus eliminating the race around condition.

#### Working of Master-Slave JK Flip-Flop

1. **Initial State:**
   - The **master flip-flop** is enabled by the clock's **positive edge** (rising edge).
   - The **slave flip-flop** is enabled by the clock's **negative edge** (falling edge).

2. **First Stage (Master Flip-Flop):**
   - When the clock transitions from **low to high** (positive edge), the master flip-flop becomes active.
   - The master takes the inputs **J** and **K** and processes them.
   - However, the output of the master flip-flop is **not passed to the slave** until the clock falls.

3. **Second Stage (Slave Flip-Flop):**
   - When the clock transitions from **high to low** (negative edge), the master flip-flop is disabled, and the slave flip-flop becomes active.
   - The output from the master flip-flop is then transferred to the slave flip-flop.
   - The slave's output (Q) is passed as the final output.

#### Benefits of Master-Slave Design:
- **Elimination of Race Around Condition:** Since the master flip-flop only captures input on the clock’s rising edge, and the slave flip-flop updates the output on the falling edge, the flip-flop toggles only once per clock cycle.
- **Controlled Output Changes:** By using this configuration, even if the inputs change multiple times during the clock pulse, the output remains stable and changes only after a full clock cycle.

---

### Operation of Master-Slave JK Flip-Flop Based on Input States

- **J = 0, K = 0:** No change. The output (Q) remains the same.
- **J = 0, K = 1:** The output is reset to 0.
- **J = 1, K = 0:** The output is set to 1.
- **J = 1, K = 1:** The output toggles (flips to the opposite state).

By using this mechanism, the master-slave JK flip-flop prevents unwanted multiple transitions during a single clock pulse and ensures that the output behaves predictably based on the inputs.

---
#### Summary of Operation

- **Master Flip-Flop:** Captures input based on the clock's rising edge.
- **Slave Flip-Flop:** Updates the output based on the clock's falling edge.
- **Key Advantage:** Eliminates the race around condition by ensuring the output changes only once during a clock cycle.

---

#### References
1. **Morris Mano**, *Digital Design: Principles and Practices*
2. **Tocci & Widmer**, *Digital Systems: Principles and Applications*
3. **John F. Wakerly**, *Digital Design: Principles and Practice*

---

#### Information
- **Date:** 2024.10.01
- **Time:** 10:42