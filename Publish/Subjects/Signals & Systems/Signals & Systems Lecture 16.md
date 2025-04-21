---
Title: Signals & Systems Lecture 16
Status: 
marker:
  - "[[Signals and System]]"
  - "[[Z Transform]]"
  - "[[Properties]]"
tags: 
Date: 2024.10.22
Time: 10:21
---
# Properties of Z Transform

### 1. **Linearity Property**

$$
a x_1(n) + b x_2(n) \xrightarrow{Z} a X_1(z) + b X_2(z)
$$

Where:
- $a$ and $b$ are constants
- $x_1(n)$ and $x_2(n)$ are signals with Z-Transforms $X_1(z)$ and $X_2(z)$, respectively.

### 2. **Multiplication by $a^n$ Property**

$$
a^n x(n) \xrightarrow{Z} X\left(\frac{z}{a}\right)
$$

### 3. **Time Shifting Property**

For a given signal $x(n)$ with Z-Transform $X(z)$ and region of convergence (ROC), shifting the signal by $k$ units in the time domain results in:

$$
x(n - k) \xrightarrow{Z} z^{-k} X(z)
$$

The ROC remains the same, except for any potential points where $z = 0$ or $z = \infty$ might be included or excluded, depending on the nature of the shift. This property indicates that a time shift by $k$ units results in the multiplication of the Z-Transform by $z^{-k}$ in the frequency domain.

### 4. **Region of Convergence (ROC) Calculations**

The **Region of Convergence (ROC)** defines where the Z-Transform converges. The ROC is determined by the nature of the signal, including its stability and causality.

#### **1. ROC for Finite-Length Signals**
For finite-duration signals, the Z-Transform converges for all $z \neq 0$:

$$
\text{ROC: } z \neq 0
$$

#### **2. ROC for Right-Sided Signals (Causal Signals)**
For causal signals (right-sided sequences), the Z-Transform converges outside a circle of radius $r_0$:

$$
\text{ROC: } |z| > r_0
$$

Where $r_0$ is the magnitude of the largest pole.

#### **3. ROC for Left-Sided Signals (Anti-Causal Signals)**
For anti-causal signals (left-sided sequences), the Z-Transform converges inside a circle of radius $r_1$:

$$
\text{ROC: } |z| < r_1
$$

Where $r_1$ is the magnitude of the smallest pole.

#### **4. ROC for Two-Sided Signals**
For two-sided signals, the ROC is the ring between the poles, defined by $r_1$ and $r_0$:

$$
\text{ROC: } r_1 < |z| < r_0
$$

#### **5. ROC for Exponential Signals**
For a signal of the form $x(n) = a^n u(n)$ (where $u(n)$ is the unit step function), the ROC is:

$$
\text{ROC: } |z| > |a|
$$

#### **6. Special Considerations for ROC**
- **Causal Systems**: The ROC must include $z = \infty$, ensuring system stability.
- **Anti-Causal Systems**: The ROC must include $z = 0$.
- **Stability**: A system is **BIBO stable** if the ROC includes the unit circle $|z| = 1$.

### **Summary of ROC Calculation Process**
1. Identify whether the signal is right-sided, left-sided, or two-sided.
2. Locate the poles of the Z-Transform.
3. Determine the ROC based on the nature of the signal:
   - Right-sided: ROC is outside the largest pole.
   - Left-sided: ROC is inside the smallest pole.
   - Two-sided: ROC is between two poles.

### **Example Calculation of ROC**

For a causal signal $x(n) = 2^n u(n)$, the Z-Transform is:

$$
X(z) = \frac{1}{1 - 2z^{-1}}
$$

The ROC is determined by $|z| > 2$ because the system is right-sided, and convergence occurs for values of $z$ outside the pole at $z = 2$.


---
# Questions & Answers
### Question 1
$$x(n)=u(n+5)$$
Applying Z Transform
$$Z[u(n)]=\frac{z}{z-1}~~;~~~|Z|>1$$
By Time Shifting Property of Z Transform
$$

Z\left[u(n+5)\right] = z^5 \left[\frac{z}{z-1}\right]

$$

# References

- **Date**: 2024.10.22
- **Time**: 10:21