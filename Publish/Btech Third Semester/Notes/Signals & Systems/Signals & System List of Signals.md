---
Title: Signals & System List of Signals
Status: 
marker:
  - "[[revision]]"
  - "[[Signals & System]]"
tags:
  - BTech
Date: 2024.09.28
Time: 10:51
---
# Signals & System List of Signals


Signals and systems can be classified into several categories based on various properties. Here’s a breakdown of the most common types:

### 1. Causal vs Non-Causal Systems:
- **Causal System**: The output of the system at any time depends only on present and past inputs, not future inputs.  
  Example: $y(t) = x(t) + x(t-1)$
- **Non-Causal System**: The output of the system depends on future inputs as well.  
  Example: $y(t) = x(t+1) + x(t)$

### 2. Static vs Dynamic Systems:
- **Static (Memoryless) System**: The output at any time depends only on the input at that exact time.  
  Example: $y(t) = 2x(t)$
- **Dynamic System**: The output at any time depends on past or future inputs, i.e., the system has memory.  
  Example: $y(t) = x(t) + x(t-1)$

### 3. Linear vs Non-Linear Systems:
- **Linear System**: The system obeys the principles of superposition (additivity and homogeneity). Mathematically, a system is linear if:
  $$y(ax_1 + bx_2) = ay(x_1) + by(x_2)$$
- **Non-Linear System**: The system does not satisfy superposition. Non-linear systems may exhibit complex behaviors like chaos or harmonics.  
  Example: $y(t) = x^2(t)$

### 4. Time-Invariant vs Time-Variant Systems:
- **Time-Invariant System**: The behavior of the system does not change over time. If you shift the input, the output shifts accordingly.  
  Example: $y(t) = x(t-1)$
- **Time-Variant System**: The system’s properties change over time. Shifting the input may result in a different output.  
  Example: $y(t) = t \cdot x(t)$

### 5. Deterministic vs Stochastic (Random) Signals:
- **Deterministic Signal**: The signal can be exactly described by a mathematical function, and its future values are completely predictable.  
  Example: $x(t) = \cos(2\pi f t)$
- **Stochastic (Random) Signal**: The signal cannot be predicted exactly due to inherent randomness. It is often described using statistical properties like mean and variance.  
  Example: White noise

### 6. Continuous-Time vs Discrete-Time Signals:
- **Continuous-Time Signal**: The signal is defined for every time instant, and time is considered a continuous variable.  
  Example: $x(t) = e^{-t}$
- **Discrete-Time Signal**: The signal is defined only at specific time instants (usually integer values), meaning time is considered a discrete variable.  
  Example: $x[n] = \sin(2\pi f n)$

### 7. Periodic vs Aperiodic Signals:
- **Periodic Signal**: The signal repeats itself after a fixed interval of time (period $T$).  
  Example: $x(t) = \sin(2\pi f t)$, where $T = \frac{1}{f}$
- **Aperiodic Signal**: The signal does not exhibit periodic behavior.  
  Example: A single pulse or decaying exponential $x(t) = e^{-t}$

### 8. Even vs Odd Signals:
- **Even Signal**: A signal is even if it is symmetric about the vertical axis, meaning $x(t) = x(-t)$.  
  Example: $x(t) = \cos(t)$
- **Odd Signal**: A signal is odd if it is anti-symmetric about the vertical axis, meaning $x(t) = -x(-t)$.  
  Example: $x(t) = \sin(t)$

### 9. Energy vs Power Signals:
- **Energy Signal**: A signal is an energy signal if it has finite energy, meaning:
  $$\int_{-\infty}^{\infty} |x(t)|^2 dt < \infty$$
  Example: A decaying exponential signal
- **Power Signal**: A signal is a power signal if it has finite average power but infinite energy.
  $$P = \lim_{T \to \infty} \frac{1}{2T} \int_{-T}^{T} |x(t)|^2 dt$$
  Example: A periodic signal like $x(t) = \sin(2\pi f t)$

### 10. Stable vs Unstable Systems:
- **Stable System**: A system is stable if bounded inputs always result in bounded outputs (BIBO stability).  
  Example: $y(t) = e^{-t}x(t)$
- **Unstable System**: A system is unstable if bounded inputs can lead to unbounded outputs.  
  Example: $y(t) = e^{t}x(t)$

### 11. Causal vs Non-Causal Signals:
- **Causal Signal**: A signal is causal if it is zero for all $t < 0$.  
  Example: $x(t) = u(t)$, where $u(t)$ is the unit step function.
- **Non-Causal Signal**: A signal that has non-zero values for times before $t = 0$.  
  Example: $x(t) = e^{t}$

### 12. Analog vs Digital Signals:
- **Analog Signal**: A signal with continuously varying amplitude over time.  
  Example: An audio signal from a microphone
- **Digital Signal**: A signal that takes discrete values in both time and amplitude.  
  Example: A binary signal representing a sequence of 0s and 1s

### 13. Symmetric vs Anti-Symmetric Systems:
- **Symmetric System**: The system behaves the same when input is reversed in time.
- **Anti-Symmetric System**: The output reverses sign when the input is reversed in time.

### 14. Bounded vs Unbounded Signals:
- **Bounded Signal**: The amplitude of the signal does not exceed a certain finite value.  
  Example: $x(t) = \cos(2\pi f t)$
- **Unbounded Signal**: The amplitude of the signal grows without bound.  
  Example: $x(t) = t^2$

---

Yes, a **signal** can be classified as either **causal** or **non-causal** based on when it exists in time.

### 1. **Causal Signal**:
A signal is said to be causal if it is **zero** for all time before a specific point, typically before $t = 0$. In other words, the signal only exists or starts after time $t = 0$. This is relevant in systems where the future input doesn't affect the current output.

$$
x(t) = 0 \quad \text{for all} \quad t < 0
$$

#### Example:
The unit step function $u(t)$ is a causal signal because it is zero for $t < 0$ and 1 for $t \geq 0$:

$$
u(t) = \begin{cases}
0, & t < 0 \\
1, & t \geq 0
\end{cases}
$$

### 2. **Non-Causal Signal**:
A signal is non-causal if it has non-zero values for times before the present (before $t = 0$), meaning it can exist in the past, present, or even future. This implies that the signal may be defined for negative time as well.

$$
x(t) \neq 0 \quad \text{for some} \quad t < 0
$$

#### Example:
A signal like $x(t) = e^t$ for all $t$ is non-causal because it is non-zero for $t < 0$.

### Summary:
- **Causal Signal**: Exists or has non-zero values only for $t \geq 0$.
- **Non-Causal Signal**: Can have non-zero values for $t < 0$.

---

