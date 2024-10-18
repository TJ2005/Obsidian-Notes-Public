---
Title: Signals & System Lecture 14
Status: 
marker:
  - "[[Fourier Transform]]"
  - "[[Signals & Systems]]"
tags:
  - BTech
Date: 2024.09.28
Time: 10:50
---
# Signals & System Lecture 14

---

### **Fourier Transform Overview**
- **Objective:** In this chapter, we analyze continuous time signals to obtain their frequency spectrum.
  - The spectrum consists of two graphs:
    1. Magnitude Response
    2. Phase Response

### **Key Definitions**
1. **Fourier Transform:**
   - For a given function $x(t)$, the Fourier Transform is given by:
     $$
     F\{x(t)\} = X(j\omega) = \int_{-\infty}^{\infty} x(t) e^{-j\omega t} dt
     $$
     - There is **no need for the Region of Convergence (ROC)** in this case.

2. **Inverse Fourier Transform:**
   - For a given function $X(\omega)$, the inverse Fourier Transform is defined as:
     $$
     x(t) = \frac{1}{2\pi} \int_{-\infty}^{\infty} X(\omega) e^{j\omega t} d\omega
     $$
     - Again, there is **no need for ROC** here.

---

### **Examples of Fourier Transforms**

1. **Case 1:**
   - Given $x(t) = e^{-at} u(t)$, where $u(t)$ is the unit step function:
     $$
     \int_{-\infty}^{\infty} e^{-at} u(t) dt = \int_{0}^{\infty} e^{-at} dt = \frac{1}{a}
     $$
     - Fourier Transform of $x(t)$ is given by:
       $$
       X(j\omega) = \frac{1}{a + j\omega}
       $$

2. **Case 2:**
   - Given $x(t) = e^{at} u(-t)$, where $u(-t)$ is the reverse unit step function:
     $$
     \int_{-\infty}^{\infty} e^{at} u(-t) e^{-j\omega t} dt = \frac{1}{a - j\omega}
     $$

---

### **Combining the Two Cases**
- For $x(t) = u(t)e^{-at} + e^{at}u(-t)$, the Fourier Transform is found by adding the results of the above two cases:
  $$
  X(j\omega) = \frac{1}{a + j\omega} + \frac{1}{a - j\omega}
  $$
  Simplifying, we get:
  $$
  X(j\omega) = \frac{2a}{a^2 + \omega^2}
  $$

---

### **Frequency Response**
- For a given signal $x(t) = e^{-at} u(t)$, the frequency response is obtained as follows:
  $$
  X(\omega) = \frac{1}{a + j\omega}
  $$
  - **Magnitude Response:**
    $$
    |X(\omega)| = \frac{1}{\sqrt{a^2 + \omega^2}}
    $$
  - **Phase Response:**
    $$
    \angle X(\omega) = -\tan^{-1}\left(\frac{\omega}{a}\right)
    $$

---

### **Phase and Magnitude Response of $X(\omega)$**

- **Phase Response:** The phase response is antisymmetric.
- **Magnitude Response:** The magnitude response is symmetric.

#### **Phase and Magnitude Calculations:**
For the signal $X(\omega) = \frac{1}{a + j\omega}$, we calculate the magnitude and phase for specific values of $\omega$.

| $\omega$ |          $A$           |          $X(\omega)$           | $   | $\angle X(\omega)$ |
| :------: | :--------------------: | :----------------------------: | --- | ------------------ |
|   $0$    |     $\frac{1}{a}$      |    $\tan^{-1}(0) = 0^\circ$    |     |                    |
|   $a$    | $\frac{1}{\sqrt{2a}}$  |   $\tan^{-1}(1) = 45^\circ$    |     |                    |
|   $2a$   | $\frac{1}{\sqrt{5a}}$  |  $\tan^{-1}(2) = 63.43^\circ$  |     |                    |
|   $3a$   | $\frac{1}{\sqrt{10a}}$ |  $\tan^{-1}(3) = 71.56^\circ$  |     |                    |
| $\infty$ |          $0$           | $\tan^{-1}(\infty) = 90^\circ$ |     |                    |

#### **Graphical Representation:**
- **Magnitude Response**: $|X(\omega)|$
  - The graph illustrates how the magnitude decreases as $\omega$ increases.
  - It starts at $\frac{1}{a}$ for $\omega = 0$ and gradually decreases towards 0 as $\omega \to \infty$.
  - Key points on the graph:
    - At $\omega = a$: $|X(\omega)| = \frac{1}{\sqrt{2a}}$
    - At $\omega = 2a$: $|X(\omega)| = \frac{1}{\sqrt{5a}}$

- **Phase Response**: $\angle X(\omega)$
  - The phase angle $\angle X(\omega)$ shifts gradually from $0^\circ$ at $\omega = 0$ to $-90^\circ$ as $\omega \to \infty$.

---

### **Constant Signal Fourier Transform**
- The Fourier transform of a constant signal $x(t) = A$ over all time $-\infty < t < \infty$:
  $$
  X(\omega) = 2\pi A \delta(\omega)
  $$
  - This represents an impulse function at $\omega = 0$, indicating that a constant signal has all its frequency concentrated at zero frequency.

---

### **Fourier Transform of the Delta Function**

- **Non-Integrable Nature of the Delta Function:**
  Since the delta function, $\delta(\omega)$, is not integrable in the conventional sense, we apply the Fourier Transform properties. The Fourier Transform of $\delta(\omega)$ is given as:
  $$
  F\{\delta(\omega)\} = \frac{1}{2\pi} \int_{-\infty}^{\infty} \delta(\omega) e^{j\omega t} d\omega
  $$
  - At $\omega = 0$, the exponential term becomes $e^0 = 1$.

- Therefore, we have:
  $$
  F\{\delta(\omega)\} = \frac{1}{2\pi} \cdot 1
  $$

- **Inverse Fourier Transform of $\delta(\omega)$:**
  $$
  F^{-1}\{\delta(\omega)\} = \frac{1}{2\pi}
  $$
  This property shows that the inverse Fourier Transform of the delta function is a constant factor of $\frac{1}{2\pi}$.

- **Multiplying by $2\pi$ on Both Sides:**
  $$
  2\pi \cdot F^{-1}\{\delta(\omega)\} = 1
  $$

- **Fourier Transform of a Constant Signal:**
  Taking the Fourier Transform of both sides for a constant $A$:
  $$
  2\pi F\{A\} = F\{1\}
  $$
  - The result gives us:
  $$
  F\{A\} = 2\pi A \delta(\omega)
  $$

This shows that the Fourier Transform of a constant signal results in a scaled delta function in the frequency domain.

---

These notes are now ready for use in Obsidian with LaTeX formatting for the math elements. Let me know if you need further adjustments!

