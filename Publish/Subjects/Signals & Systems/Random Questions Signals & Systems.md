---
Title: Random Questions Signals & Systems
Status: 
marker:
  - "[[Signals and System]]"
  - "[[Question Bank[[]]"
tags: 
Date: 2024.11.25
Time: 20:36
---
# Random Questions Signals & Systems

# Fourier Transform
## Fourier Transform 1
To compute the Fourier Transform of the given signal:

The signal is:

$x(t)=δ(t+2)+δ(t−2)+5δ(t+1)−5δ(t−1)x(t)$
$= \delta(t+2) + \delta(t-2) + 5\delta(t+1) - 5\delta(t-1)$

### Fourier Transform of Dirac Delta Functions

The Fourier Transform of $\delta(t-a)$ is given by:
$\mathcal{F}\{\delta(t-a)\} = e^{-j\omega a}$

where $a$ is the shift in time.

### Fourier Transform of $x(t)$

Using the linearity property of the Fourier Transform, we compute the Fourier Transform of each term:

1. $\mathcal{F}{\delta(t+2)} = e^{j2\omega}$
2. $\mathcal{F}{\delta(t-2)} = e^{-j2\omega}$
3. $\mathcal{F}{5\delta(t+1)} = 5e^{j\omega}$
4. $\mathcal{F}{-5\delta(t-1)} = -5e^{-j\omega}$

Adding these together, the Fourier Transform of $x(t)$ is:

$X(ω)=ej2ω+e−j2ω+5ejω−5e−jωX(\omega) = e^{j2\omega} + e^{-j2\omega} + 5e^{j\omega} - 5e^{-j\omega}$

### Simplifying Using Euler's Formula

Using Euler's formula:

$=ejθ+e−jθ$
$=2cos⁡(θ)e^{j\theta} + e^{-j\theta}$
$= 2\cos(\theta) ejθ−e−jθ$
$=2jsin⁡(θ)e^{j\theta} - e^{-j\theta}$
$= 2j\sin(\theta)$

We simplify:

1. $e^{j2\omega} + e^{-j2\omega} = 2\cos(2\omega)$
2. $5e^{j\omega} - 5e^{-j\omega} = 10j\sin(\omega)$

Thus, the Fourier Transform is:

$X(ω)=2cos⁡(2ω)+10jsin⁡(ω)X(\omega) = 2\cos(2\omega) + 10j\sin(\omega)$

This is the final expression for the Fourier Transform of $x(t)$.


## Fourier Transform 2
Here is the solution written in **Obsidian-friendly format**:

---

### Solution

The given signal is:

x(t)={e−at,t>0−eat,t<0x(t) = \begin{cases} e^{-at}, & t > 0 \\ -e^{at}, & t < 0 \end{cases}

where $a > 0$.

---

### Fourier Transform Definition

The Fourier Transform is given by:

X(jω)=∫−∞∞x(t)e−jωtdtX(j\omega) = \int_{-\infty}^\infty x(t) e^{-j\omega t} dt

---

### Splitting the Signal

Split the Fourier Transform into two parts based on the given signal:

X(jω)=∫−∞0−eate−jωtdt+∫0∞e−ate−jωtdtX(j\omega) = \int_{-\infty}^0 -e^{at} e^{-j\omega t} dt + \int_{0}^\infty e^{-at} e^{-j\omega t} dt

---

### Step 1: Solve for $t > 0$

For $t > 0$, $x(t) = e^{-at}$:

∫0∞e−ate−jωtdt=∫0∞e−(a+jω)tdt\int_{0}^\infty e^{-at} e^{-j\omega t} dt = \int_{0}^\infty e^{-(a + j\omega)t} dt

Using the formula $\int_{0}^\infty e^{-kt} dt = \frac{1}{k}$ for $\text{Re}(k) > 0$:

∫0∞e−(a+jω)tdt=1a+jω\int_{0}^\infty e^{-(a + j\omega)t} dt = \frac{1}{a + j\omega}

---

### Step 2: Solve for $t < 0$

For $t < 0$, $x(t) = -e^{at}$:

∫−∞0−eate−jωtdt=−∫−∞0e(a−jω)tdt\int_{-\infty}^0 -e^{at} e^{-j\omega t} dt = -\int_{-\infty}^0 e^{(a - j\omega)t} dt

Substitute $t \to -t$ to handle the bounds:

−∫−∞0e(a−jω)tdt=∫0∞e−(a−jω)tdt-\int_{-\infty}^0 e^{(a - j\omega)t} dt = \int_{0}^\infty e^{-(a - j\omega)t} dt

Using the same formula:

∫0∞e−(a−jω)tdt=1a−jω\int_{0}^\infty e^{-(a - j\omega)t} dt = \frac{1}{a - j\omega}

---

### Step 3: Combine the Results

Combine the results for $t > 0$ and $t < 0$:

X(jω)=1a+jω+1a−jωX(j\omega) = \frac{1}{a + j\omega} + \frac{1}{a - j\omega}

Simplify:

X(jω)=a−jω+a+jω(a+jω)(a−jω)X(j\omega) = \frac{a - j\omega + a + j\omega}{(a + j\omega)(a - j\omega)} X(jω)=2aa2+ω2X(j\omega) = \frac{2a}{a^2 + \omega^2}

---

### Magnitude Spectrum

The magnitude of $X(j\omega)$ is:

∣X(jω)∣=2aa2+ω2|X(j\omega)| = \frac{2a}{a^2 + \omega^2}

---

### Phase Spectrum

The phase of $X(j\omega)$ is:

∠X(jω)=0,since the signal is real and even.\angle X(j\omega) = 0, \quad \text{since the signal is real and even.}

---

### Final Answer

1. **Fourier Transform**:

X(jω)=2aa2+ω2X(j\omega) = \frac{2a}{a^2 + \omega^2}

2. **Magnitude Spectrum**:

∣X(jω)∣=2aa2+ω2|X(j\omega)| = \frac{2a}{a^2 + \omega^2}

3. **Phase Spectrum**:

∠X(jω)=0\angle X(j\omega) = 0

---

The **magnitude spectrum** is a Lorentzian curve centered at $\omega = 0$ with a peak value of $\frac{2}{a}$. The **phase spectrum** is constant at $0$. Let me know if you'd like additional visualizations!
h
# Z Transform
## Question 1
### Question:
Compute the Z-transform and sketch the ROC for \( x[n] = \{5, 4, -3, -1, 0, 4, -3, 2\} \), where \( n = -3, -2, -1, 0, 1, 2, 3, 4 \).

---

### Solution:

1. **Z-transform**:
   $$
   X(z) = 5z^3 + 4z^2 - 3z - 1 + \frac{4}{z^2} - \frac{3}{z^3} + \frac{2}{z^4}
   $$

2. **Region of Convergence (ROC)**:
   $$
   \text{ROC: All values of } z, \text{ except } z = 0.
   $$


## Question 2
### Question:
Calculate the Z-transform of the following discrete-time signals and also sketch the ROC:

1. $x[n] = \left(\frac{1}{4}\right)^n u[n] + \left(\frac{1}{5}\right)^n u[-n-1]$
2. $x[n] = \sin(\omega_0 n) u[n]$

---

### Solution:

#### (i) $x[n] = \left(\frac{1}{4}\right)^n u[n] + \left(\frac{1}{5}\right)^n u[-n-1]$

1. **For $\left(\frac{1}{4}\right)^n u[n]$:**

   The Z-transform is:
   $$
   X_1(z) = \sum_{n=0}^\infty \left(\frac{1}{4}\right)^n z^{-n}
   $$

   This is a geometric series with the first term $1$ and the common ratio $\frac{1}{4z}$:
   $$
   X_1(z) = \frac{1}{1 - \frac{1}{4}z^{-1}} = \frac{z}{z - \frac{1}{4}}.
	   $$

   **ROC**: $|z| > \frac{1}{4}$.

2. **For $\left(\frac{1}{5}\right)^n u[-n-1]$:**

   Rewrite the summation as $n = -k$, where $k \geq 1$, giving:
   $$
   X_2(z) = \sum_{k=1}^\infty \left(\frac{1}{5}\right)^k z^{-k}.
   $$

   This is a geometric series with the first term $\frac{1}{5z}$ and the common ratio $\frac{1}{5z}$:
   $$
   X_2(z) = \frac{\frac{1}{5z}}{1 - \frac{1}{5z}} = \frac{\frac{1}{5}}{z - \frac{1}{5}}.
   $$

   **ROC**: $|z| < \frac{1}{5}$.

3. **Total Z-transform**:
   $$
   X(z) = X_1(z) + X_2(z) = \frac{z}{z - \frac{1}{4}} + \frac{\frac{1}{5}}{z - \frac{1}{5}}.
   $$

   **Total ROC**: No overlap in ROCs, so the Z-transform is valid only in disjoint regions:
   - $|z| > \frac{1}{4}$ for $X_1(z)$.
   - $|z| < \frac{1}{5}$ for $X_2(z)$.

---

#### (ii) $x[n] = \sin(\omega_0 n) u[n]$

1. Rewrite $\sin(\omega_0 n)$ using Euler's formula:
   $$
   \sin(\omega_0 n) = \frac{e^{j\omega_0 n} - e^{-j\omega_0 n}}{2j}.
   $$

   The signal becomes:
   $$
   x[n] = \frac{1}{2j} \left(e^{j\omega_0 n} - e^{-j\omega_0 n}\right) u[n].
   $$

2. Compute the Z-transform for each term separately:
   - For $e^{j\omega_0 n} u[n]$:
     $$
     X_1(z) = \sum_{n=0}^\infty e^{j\omega_0 n} z^{-n} = \frac{1}{1 - e^{j\omega_0} z^{-1}}.
     $$

   - For $e^{-j\omega_0 n} u[n]$:
     $$
     X_2(z) = \sum_{n=0}^\infty e^{-j\omega_0 n} z^{-n} = \frac{1}{1 - e^{-j\omega_0} z^{-1}}.
     $$

3. Combine terms:
   $$
   X(z) = \frac{1}{2j} \left(\frac{1}{1 - e^{j\omega_0} z^{-1}} - \frac{1}{1 - e^{-j\omega_0} z^{-1}}\right).
   $$

4. Simplify:
   $$
   X(z) = \frac{z^{-1} \sin(\omega_0)}{1 - 2\cos(\omega_0)z^{-1} + z^{-2}}.
   $$

   **ROC**: $|z| > 1$ (signal is causal).

---

### Final Answers:
1. **For $x[n] = \left(\frac{1}{4}\right)^n u[n] + \left(\frac{1}{5}\right)^n u[-n-1]$:**
   - $X(z) = \frac{z}{z - \frac{1}{4}} + \frac{\frac{1}{5}}{z - \frac{1}{5}}$
   - ROC: Disjoint regions, $|z| > \frac{1}{4}$ and $|z| < \frac{1}{5}$.

2. **For $x[n] = \sin(\omega_0 n) u[n]$:**
   - $X(z) = \frac{z^{-1} \sin(\omega_0)}{1 - 2\cos(\omega_0)z^{-1} + z^{-2}}$
   - ROC: $|z| > 1$.

##
# Time Period
## Question 1 
### Question:
Compute the fundamental time period and frequency of the following signals:

1. $x(t) = 5 \sin(24\pi t) + 7 \sin(36\pi t)$
2. $x(t) = 5 \cos(\pi t) \sin(3\pi t)$

---

### Solution:

#### (i) $x(t) = 5 \sin(24\pi t) + 7 \sin(36\pi t)$

1. The angular frequency of $\sin(24\pi t)$ is $\omega_1 = 24\pi$, and the period is:
   $$
   T_1 = \frac{2\pi}{\omega_1} = \frac{2\pi}{24\pi} = \frac{1}{12}.
   $$

2. The angular frequency of $\sin(36\pi t)$ is $\omega_2 = 36\pi$, and the period is:
   $$
   T_2 = \frac{2\pi}{\omega_2} = \frac{2\pi}{36\pi} = \frac{1}{18}.
   $$

3. The fundamental time period $T$ is the **least common multiple (LCM)** of $T_1$ and $T_2$:
   $$
   T = \text{LCM}\left(\frac{1}{12}, \frac{1}{18}\right) = \frac{1}{6}.
   $$

4. The fundamental frequency $f$ is:
   $$
   f = \frac{1}{T} = 6 \, \text{Hz}.
   $$

---

#### (ii) $x(t) = 5 \cos(\pi t) \sin(3\pi t)$

1. Using the trigonometric identity:
   $$
   \cos(A) \sin(B) = \frac{1}{2} \left[\sin(A+B) - \sin(A-B)\right],
   $$
   the signal becomes:
   $$
   x(t) = \frac{5}{2} \left[\sin(4\pi t) - \sin(2\pi t)\right].
   $$

2. The angular frequencies are:
   - For $\sin(4\pi t)$, $\omega_1 = 4\pi$, and $T_1 = \frac{1}{2}.$
   - For $\sin(2\pi t)$, $\omega_2 = 2\pi$, and $T_2 = 1.$

3. The fundamental time period $T$ is the **LCM** of $T_1$ and $T_2$:
   $$
   T = \text{LCM}\left(\frac{1}{2}, 1\right) = 1.
   $$

4. The fundamental frequency $f$ is:
   $$
   f = \frac{1}{T} = 1 \, \text{Hz}.
   $$

---

### Final Answers:
1. **For $x(t) = 5 \sin(24\pi t) + 7 \sin(36\pi t)$:**
   - Fundamental Time Period: $T = \frac{1}{6} \, \text{s}$
   - Frequency: $f = 6 \, \text{Hz}$

2. **For $x(t) = 5 \cos(\pi t) \sin(3\pi t)$:**
   - Fundamental Time Period: $T = 1 \, \text{s}$
   - Frequency: $f = 1 \, \text{Hz}$

## Question 2

# Convolution
### Question:
Compute the convolution of the given two signals:
- $x(t) = u(t) - u(t-4)$
- $h(t) = u(t) - u(t-1)$

using the graphical method.

---

### Solution:

#### 1. Signals Description:
1. $x(t) = u(t) - u(t-4)$: This represents a rectangular pulse starting at $t = 0$ and ending at $t = 4$.
2. $h(t) = u(t) - u(t-1)$: This represents a rectangular pulse starting at $t = 0$ and ending at $t = 1$.

#### 2. Convolution Formula:
The convolution of two signals $x(t)$ and $h(t)$ is given by:
$$
y(t) = (x * h)(t) = \int_{-\infty}^\infty x(\tau) h(t-\tau) \, d\tau
$$

#### 3. Graphical Method Steps:
1. **Flip $h(t)$ to obtain $h(-\tau)$**:
   - $h(-\tau)$ is a pulse of width 1 (from $\tau = -1$ to $\tau = 0$).

2. **Shift $h(-\tau)$ to $h(t-\tau)$**:
   - As $t$ varies, $h(t-\tau)$ shifts across $t$.

3. **Multiply $x(\tau)$ and $h(t-\tau)$**:
   - For each value of $t$, calculate the overlap between $x(\tau)$ (a rectangular pulse from $0$ to $4$) and $h(t-\tau)$ (a rectangular pulse shifted to $t$).

4. **Integrate the product**:
   - The integral computes the area of overlap between the two pulses.

---

#### 4. Piecewise Convolution Results:
We evaluate the convolution $y(t)$ in **different time intervals** based on the overlap of $x(\tau)$ and $h(t-\tau)$:

1. **For $t < 0$:**
   - No overlap between $x(\tau)$ and $h(t-\tau)$.
   - $y(t) = 0$.

2. **For $0 \leq t < 1$:**
   - $h(t-\tau)$ starts to overlap with $x(\tau)$ from $\tau = 0$ to $\tau = t$.
   - Overlap area = width of $h(t-\tau)$ = $t$.
   - $y(t) = t$.

3. **For $1 \leq t < 4$:**
   - Full overlap between $h(t-\tau)$ and $x(\tau)$ from $\tau = 0$ to $\tau = 1$.
   - Overlap area = width of $h(t-\tau)$ = $1$.
   - $y(t) = 1$.

4. **For $4 \leq t < 5$:**
   - $h(t-\tau)$ overlaps partially with $x(\tau)$ from $\tau = t-4$ to $\tau = 1$.
   - Overlap area = width = $5 - t$.
   - $y(t) = 5 - t$.

5. **For $t \geq 5$:**
   - No overlap between $x(\tau)$ and $h(t-\tau)$.
   - $y(t) = 0$.

---

#### 5. Final Expression for $y(t)$:
The result of the convolution is:
$$
y(t) =
\begin{cases}
0, & t < 0 \\
t, & 0 \leq t < 1 \\
1, & 1 \leq t < 4 \\
5 - t, & 4 \leq t < 5 \\
0, & t \geq 5
\end{cases}
$$

---

### Graphical Representation:
1. The convolution $y(t)$ is piecewise linear and can be plotted:
   - Rising linearly from $0$ to $1$ in the interval $[0, 1]$.
   - Constant at $1$ in the interval $[1, 4]$.
   - Falling linearly from $1$ to $0$ in the interval $[4, 5]$.

---

Let me know if you would like me to plot the graph for this! You can copy-paste this explanation into Obsidian.

# Energy Power Signal
## Question 1 
### Question:
Classify the following signals as energy signal, power signal, or neither. Also, determine the energy and power.

1. $x(t) = e^{3t} u(-t)$
2. $x(t) = e^{-2|t|}$

---

### Solution:

#### **Definitions:**
1. **Energy Signal**:
   A signal is an energy signal if its **total energy** is finite and power is zero:
   $$
   E = \int_{-\infty}^\infty |x(t)|^2 dt < \infty, \quad P = 0.
   $$

2. **Power Signal**:
   A signal is a power signal if its **average power** is finite and energy is infinite:
   $$
   P = \lim_{T \to \infty} \frac{1}{2T} \int_{-T}^T |x(t)|^2 dt < \infty, \quad E = \infty.
   $$

3. **Neither**:
   If neither condition is satisfied, the signal is classified as "neither."

---

#### **(i) $x(t) = e^{3t} u(-t)$**

1. **Signal Analysis**:
   - The term $u(-t)$ ensures that $x(t)$ is nonzero only for $t \leq 0$.
   - For $t \leq 0$, $x(t) = e^{3t}$.

2. **Energy Calculation**:
   $$
   E = \int_{-\infty}^\infty |x(t)|^2 dt = \int_{-\infty}^0 \left(e^{3t}\right)^2 dt = \int_{-\infty}^0 e^{6t} dt.
   $$
   Solve the integral:
   $$
   E = \left[\frac{e^{6t}}{6}\right]_{-\infty}^0 = \frac{1}{6} \left(e^{0} - \lim_{t \to -\infty} e^{6t}\right) = \frac{1}{6}.
   $$

   - The energy is finite: $E = \frac{1}{6}$.

3. **Power Calculation**:
   The power is zero since the signal exists only for $t \leq 0$ (non-periodic and finite energy).

4. **Classification**:
   - **Energy Signal**.

---

#### **(ii) $x(t) = e^{-2|t|}$**

1. **Signal Analysis**:
   - $x(t)$ is symmetric around $t = 0$.
   - For $t \geq 0$, $x(t) = e^{-2t}$.
   - For $t < 0$, $x(t) = e^{2t}$.

2. **Energy Calculation**:
   $$
   E = \int_{-\infty}^\infty |x(t)|^2 dt = \int_{-\infty}^0 \left(e^{2t}\right)^2 dt + \int_0^\infty \left(e^{-2t}\right)^2 dt.
   $$
   Solve for each integral:
   - For $t \geq 0$: $\int_0^\infty e^{-4t} dt = \frac{1}{4}$.
   - For $t < 0$: $\int_{-\infty}^0 e^{4t} dt = \frac{1}{4}$.

   Total energy:
   $$
   E = \frac{1}{4} + \frac{1}{4} = \frac{1}{2}.
   $$

   - The energy is finite: $E = \frac{1}{2}$.

3. **Power Calculation**:
   The power is zero since the signal is non-periodic and finite energy.

4. **Classification**:
   - **Energy Signal**.

---

### Final Answers:
1. **For $x(t) = e^{3t} u(-t)$**:
   - **Classification**: Energy Signal.
   - **Energy**: $E = \frac{1}{6}$.
   - **Power**: $P = 0$.

2. **For $x(t) = e^{-2|t|}$**:
   - **Classification**: Energy Signal.
   - **Energy**: $E = \frac{1}{2}$.
   - **Power**: $P = 0$.

# References


###### Information
- date: 2024.11.25
- time: 20:36