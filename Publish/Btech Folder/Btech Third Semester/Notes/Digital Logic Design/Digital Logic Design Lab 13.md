---
Title: Digital Logic Design Lab 7
Status: 
marker: 
tags: 
Date: 2024.10.01
Time: 10:19
---
# Experiment 7  
## Name: Tejas Sahoo  
## Roll No: K057  
## B-Tech CSE (Cyber Security) Batch K2  
## Date: 1/10/24  

---

### **Aim**  
To verify the truth table and timing diagram of RS, JK, T, and D flip-flops using NAND and NOR gate ICs, and to analyze the circuit of RS, JK, T, and D flip-flops with the help of LED displays.

---

### **Theory**

#### **Introduction**  
A flip-flop is an electronic circuit with two stable states used to store binary data. The stored data can be altered by applying varying inputs. Flip-flops are essential building blocks in digital electronics systems, widely used in computers, communication systems, and other applications.

**Types of Flip-Flops**:  
1. **RS Flip-Flop**  
2. **D Flip-Flop**  
3. **JK Flip-Flop**  
4. **T Flip-Flop**  

---

#### **1. RS Flip-Flop**  
The RS (Reset-Set) flip-flop stores data and provides feedback from its outputs to its inputs. It has three inputs: Set, Reset, and Clock.  

**Figure-1**: RS Flip-Flop Circuit Diagram  
**Figure-2**: Characteristics Table of RS Flip-Flop  

---

#### **2. D Flip-Flop**  
The D (Data) flip-flop is derived from the RS flip-flop by complementing the R input and directly connecting the S input to the data input. It ensures no unpredictable states when both inputs are high.  

**Figure-3**: D Flip-Flop Circuit Diagram  
**Figure-4**: Characteristics Table of D Flip-Flop  

---

#### **3. JK Flip-Flop**  
The JK flip-flop resolves the indeterminate state of the RS flip-flop when both inputs are high. When J and K are 1, the outputs toggle.  

**Figure-5**: JK Flip-Flop Circuit Diagram  
**Figure-6**: Characteristics Table of JK Flip-Flop  

---

#### **4. T Flip-Flop**  
The T (Toggle) flip-flop is a modified JK flip-flop, with both inputs held at logic 1. The output toggles between states with each clock pulse.  

**Figure-7**: T Flip-Flop Circuit Diagram  
**Figure-8**: Characteristics Table of T Flip-Flop  

---

### **Procedure**  

#### **1. RS Flip-Flop Simulation**  
1. Connect the supply (+5V) to the circuit.  
2. Press "ADD" to add the initial output state in the table.  
3. Set the inputs "S" and "R," then apply the clock pulse.  
4. Press "ADD" to record inputs and outputs in the table and graph.  
5. Repeat steps 3 and 4 for the next input states.  
6. Press "Print" to save the simulation results.
![[Pasted image 20241118174511.png]]
---

#### **2. D Flip-Flop Simulation**  
1. Connect the supply (+5V) to the circuit.  
2. Press "ADD" to add the initial output state in the table.  
3. Set the inputs "D" and "Clock."  
4. Press "ADD" to record inputs and outputs in the table and graph.  
5. Repeat steps 3 and 4 for the next input states.  
6. Press "Print" to save the simulation results.

![[Pasted image 20241118174521.png]]

---

#### **3. JK Flip-Flop Simulation**  
1. Connect the supply (+5V) to the circuit.  
2. Press "ADD" to add the initial output state in the table.  
3. Set the inputs "J" and "K," then apply the clock pulse.  
4. Press "ADD" to record inputs and outputs in the table and graph.  
5. Repeat steps 3 and 4 for the next input states.  
6. Press "Print" to save the simulation results.
![[Pasted image 20241118174532.png]]

---

#### **4. T Flip-Flop Simulation**  
1. Connect the supply (+5V) to the circuit.  
2. Press "ADD" to add the initial output state in the table.  
3. Set the input "T," then apply the clock pulse.  
4. Press "ADD" to record inputs and outputs in the table and graph.  
5. Press "Print" to save the simulation results.
![[Pasted image 20241118174543.png]]

---

### **Conclusion**  
Using the IIT Roorkee Virtual Lab, we successfully simulated and verified the truth tables and timing diagrams of RS, D, JK, and T flip-flops.
