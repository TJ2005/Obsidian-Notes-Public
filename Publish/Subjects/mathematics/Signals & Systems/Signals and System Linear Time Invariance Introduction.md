---
Title: Signals & System Linear Time Invariance
Status: 
marker:
  - "[[Linear Time Invariance]]"
  - "[[Signals & System Basic System Properties]]"
tags: 
Date: 2024.10.08
Time: 01:35
---

Continued from [[Signals & System Basic System Properties]]

---

# **Introducing Time Invariance**
m
## **Linear Time Invariance (LTI) and Linearity**

Linear Time Invariance (LTI) plays a fundamental role in signal and system analysis for two major reasons:

1. **Many physical processes possess the property of LTI.**
2. **LTI systems can be analysed using mathematical tools**, which provide a structured approach to understanding system behaviour.

---

## **Mathematical Tools for LTI Analysis**

LTI systems can be studied using various mathematical tools, including:
### **1. Convolution**
- **When Needed:** Used to compute the output of an LTI system given an input and its impulse response
### **2. Fourier Transform**
- **When Needed:** Essential for frequency domain analysis, stability, and system response characterization.
### **3. Laplace Transform**
- **When Needed:** Helps analyse continuous-time LTI systems and their stability. It is also useful for solving differential equations.
### **4. Eigenfunction Analysis**
- **When Needed:** Used to simplify LTI system response calculations by leveraging the fact that exponentials remain exponentials after system transformation.

We will explore these tools in detail in further sections.

---

## **Superposition Property in LTI Systems**

- If an input signal is expressed as a combination of simpler signals, the system’s response can be computed using the responses to those basic signals.
- This enables **modular analysis** by breaking complex signals into simpler parts, making analysis easier.

---


## **References** & Extras
## **LTI Systems in Real-World Applications**

LTI systems are widely used in practical applications, such as:

### **1. Electrical Circuits (RL, RC, RLC Circuits in an Audio Processor)**

- **Tools Used:**
    - **Differential Equations:** To model circuit response.
    - **Laplace Transform:** To analyse frequency response and transient behavior.
    - **Impulse Response & Convolution Integral:** To determine output for any given input.

### **2. Audio Signal Processing (Equalizers, Noise Reduction)**

- **Example:** A **graphic equalizer** that boosts or attenuates certain frequencies in an audio signal.
- **Why LTI?** The filter applies the same effect regardless of when the sound was played.
- **Tools Used:**
    - **Fourier Transform:** To analyse how different frequencies are affected.
    - **Convolution:** To compute the output signal from impulse response.


### **Information**

- **Date:** 2024.10.08
- **Time:** 01:35
- Continued to [[Signals and System Convolution Sum]]

---

