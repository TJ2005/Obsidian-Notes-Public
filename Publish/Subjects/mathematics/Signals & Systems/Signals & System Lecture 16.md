---
Title: Signals & System Lecture 10
Status: 
marker:
  - "[[Laplace Transform]]"
  - "[[Integration]]"
  - "[[Systems]]"
tags:
  - BTech
Date: 2024.08.29
Time: 09:08
---
### Signals & Systems - Lecture 10

#### Laplace Transformation

**Definition:**
The Laplace Transformation is a mathematical technique used to transform a time-domain signal into a complex frequency-domain signal. The transformation variable is denoted by \( s \), where \( s = \sigma + j\omega \). This transformation is particularly useful for analyzing linear time-invariant (LTI) systems and is best suited for continuous signals.

In the Laplace transformation:
- Derivatives in the time domain are multiplied by \( s \).
- Integrations are divided by \( s \).

The Laplace Transform is given by:
$$ L[x(t)] = X(s) = \int_{-\infty}^{\infty} x(t) \cdot e^{-st} \, dt $$

For signals defined for \( t \geq 0 \), the Laplace Transform simplifies to:
$$ L[x(t)] = X(s) = \int_{0}^{\infty} x(t) \cdot e^{-st} \, dt $$

This version, considering all values of \( t \), is known as the bilateral Laplace Transform or the two-sided Laplace Transform.

**Region of Convergence (ROC):**
The Region of Convergence (ROC) is defined as the set of all values of \( s \) for which the Laplace integral converges:
$$ \int_{-\infty}^{\infty} x(t) \cdot e^{-st} \, dt $$
The ROC is crucial for determining the stability and causality of the system.

#### Example: Laplace Transform of the Unit Step Signal

Consider the unit step signal:
$$ x(t) = u(t) $$

By definition, the Laplace Transform is:
$$ X(s) = \int_{-\infty}^{\infty} u(t) \cdot e^{-st} \, dt $$

Since \( u(t) = 0 \) for \( t < 0 \) and \( u(t) = 1 \) for \( t \geq 0 \), the integral limits reduce to:
$$ X(s) = \int_{0}^{\infty} e^{-st} \, dt $$

Integrating, we get:
$$ X(s) = \left[ \frac{e^{-st}}{-s} \right]_{0}^{\infty} $$

Evaluating at the bounds:
$$ X(s) = \left[ \frac{e^{-\infty}}{-s} - \frac{e^{0}}{-s} \right] = \left[ 0 - \frac{1}{-s} \right] $$

Therefore, the Laplace Transform of the unit step signal is:
$$ X(s) = \frac{1}{s}, \quad \text{for } \Re(s) > 0 $$

### Ramp Signal
Certainly! Let's complete the Laplace Transform calculation for the signal \( x(t) = r(t) \), where \( r(t) \) is the ramp function.

---

Given \( x(t) = r(t) \), which is \( r(t) = t \cdot u(t) \), where \( u(t) \) is the unit step function.

By definition of the Laplace Transform:
$$ X(s) = \int_{-\infty}^{\infty} x(t) \cdot e^{-st} \, dt $$

Substituting \( x(t) = t \cdot u(t) \):
$$ X(s) = \int_{-\infty}^{\infty} t \cdot u(t) \cdot e^{-st} \, dt $$

Since \( u(t) = 0 \) for \( t < 0 \) and \( u(t) = 1 \) for \( t \geq 0 \), this reduces to:
$$ X(s) = \int_{0}^{\infty} t \cdot e^{-st} \, dt $$

To solve this integral, we use integration by parts. Let:
- \( u = t \) and \( dv = e^{-st} \, dt \).

Then:
- \( du = dt \) and \( v = \int e^{-st} \, dt = \frac{-e^{-st}}{s} \).

Now, apply integration by parts:
$$ X(s) = \left[ \frac{-t \cdot e^{-st}}{s} \right]_{0}^{\infty} + \frac{1}{s} \int_{0}^{\infty} e^{-st} \, dt $$

Evaluate the first term:
$$ X(s) = \left[ \frac{-t \cdot e^{-st}}{s} \right]_{0}^{\infty} = \left( 0 - \frac{0}{s} \right) = 0 $$

For the second term, integrate:
$$ \frac{1}{s} \int_{0}^{\infty} e^{-st} \, dt = \frac{1}{s} \cdot \left[ \frac{-e^{-st}}{s} \right]_{0}^{\infty} = \frac{1}{s} \cdot \left( 0 - \frac{-1}{s} \right) = \frac{1}{s^2} $$

Thus, the Laplace Transform of the ramp function \( x(t) = r(t) = t \cdot u(t) \) is:
$$ X(s) = \frac{1}{s^2} $$

---

### x(t)=e^at u(t)



#### Complex Frequency

When dealing with higher-order differential equations, transforming these equations into the \( s \)-domain using the Laplace Transform simplifies the analysis by converting differential equations into algebraic equations. This significantly eases the process of solving and analyzing dynamic systems.

#### Example from Classical Mechanics

Consider the differential equation representing a damped harmonic oscillator:
$$ F = Ma + Bv + kx = 0 $$

Here:
- \( kx \) is the spring's restoring force.
- \( Bv \) is the damping force.

Taking the differential equation:
$$ M \frac{d^2x}{dt^2} + B \frac{dx}{dt} + kx = 0 $$

Applying the Laplace Transform, we convert the equation into the \( s \)-domain:
$$ M s^2 X(s) + B s X(s) + k X(s) = 0 $$

This is a second-order algebraic equation in \( X(s) \), which can be easily solved for system behavior analysis.

---

**References:**
- Date: 2024.08.29
- Time: 09:08

---
### Notes on Laplace Transform

#### Definition:
- **Laplace Transform** is used to transform a signal from the time domain to a complex **frequency domain** (s-domain).
- The Laplace Transform helps convert differential equations in the time domain into algebraic equations in the frequency domain, making analysis and problem-solving easier.

#### Application:
- In the **time domain**, higher-order differential equations represent the system dynamics. These can be complex and difficult to solve.
- When transforming into the **s-domain**, the differential equation simplifies to an algebraic form that is easier to manage.

#### Example:
- A second-order system equation such as:
  $$
  m\frac{d^2x}{dt^2} + B\frac{dx}{dt} + Kx = 0
  $$
  is transformed into:
  $$
  M s^2 X(s) + B s X(s) + K X(s) = 0
  $$
  Here, the terms $M s^2$, $B s$, and $K$ are algebraic equivalents in the **s-domain**, making the equation simpler to solve.

#### Formula:
- The **Laplace Transform** of a function $x(t)$ is given by:
  $$
  X(s) = \int_{-\infty}^{\infty} x(t) e^{-st} dt
  $$
  This transformation holds for all values of $t$.

#### Notes:
- It is also called **Bilateral Laplace Transform** (L.T.), as it integrates over all values of time (from $-\infty$ to $+\infty$).

This page provides a concise summary of Laplace Transforms, highlighting their utility in simplifying differential equations and aiding in system analysis in the s-domain.
### Notes on Laplace Transform

#### Unilateral or One-sided Laplace Transform:
For $t \geq 0$:
$$
\mathcal{L} [x(t)] = X(s) = \int_{0}^{\infty} x(t) e^{-st} dt
$$

This is the **unilateral** or **one-sided Laplace Transform**.

#### Define Region of Convergence (ROC):
The **Region of Convergence (ROC)** is the set of values of $s$ for which the Laplace Transform integral:
$$
\int_{-\infty}^{\infty} x(t) e^{-st} dt
$$
converges. The value of $s$ for which this integral converges is called the **ROC**.

#### Example Problem:
**Find the Laplace transform of the following signal and draw its ROC:**

1. **Unit-step signal:**
   - $x(t) = u(t)$
   
   By definition of the Laplace Transform:
   $$
   X(s) = \int_{-\infty}^{\infty} x(t) e^{-st} dt
   $$

This page explains the concept of **unilateral Laplace Transform** and introduces the **Region of Convergence (ROC)**, along with a practical example of calculating the Laplace transform of a unit-step signal.
### Notes on Laplace Transform - Continued

#### Calculation of Laplace Transform for Unit-step Signal:
The Laplace transform of the unit-step signal $x(t) = u(t)$ is given by:
$$
X(s) = \int_{-\infty}^{\infty} u(t) e^{-st} dt
$$
This can be simplified as:
$$
X(s) = \int_{0}^{\infty} e^{-st} dt = \frac{e^{-st}}{-s} \bigg|_{0}^{\infty}
$$
Evaluating the limits:
$$
X(s) = \left[\frac{e^{-\infty}}{-s} - \frac{e^0}{-s}\right] = \frac{0 - 1}{-s} = \frac{1}{s}
$$

Thus, the Laplace transform of a unit-step function is:
$$
X(s) = \frac{1}{s}
$$

#### Region of Convergence (ROC):
For the unit-step function, the ROC is for $s > 0$.

- The shaded region in the $s$-plane indicates the ROC, which lies to the **right** of the pole at $s = 0$.

#### Important Observation:
- If the signal is on the **right side**, the **ROC** will also be on the **right side** of the $s$-plane.

#### General Expression for $s$:
$$
s = \sigma + j\Omega
$$

This page completes the example by providing the full solution for the Laplace transform of a unit-step signal, along with a visual representation of the ROC in the $s$-plane.

```desmos-graph
x = 0
x > 0
\text{Real axis: } \sigma \quad (set \sigma label on x-axis)
\text{Imaginary axis: } j\Omega \quad (set j\Omega label on y-axis)
```
### Complete Notes and Desmos Graph for Laplace Transforms

#### 2. Ramp Signal:
The function is defined as:
$$
x(t) = r(t) = t \cdot u(t)
$$
Taking the Laplace Transform (LT):
$$
\mathcal{L} [x(t)] = \int_{0}^{\infty} t \cdot e^{-st} dt
$$
Solving this integral:
$$
X(s) = \frac{1}{s^2}
$$
The **ROC** for this is $s > 0$, which corresponds to shading the right half of the complex $s$-plane.

#### Desmos Graph for Ramp Signal:

```desmos-graph
x > 0
```

This shades the right side of the $s$-plane where $s > 0$, indicating the **ROC** for the ramp signal.

---

#### 3. Exponential Signal:
The function is defined as:
$$
x(t) = e^{2t} \cdot u(t)
$$
For this example, we take $a = 2$.

Taking the Laplace Transform:
$$
\mathcal{L} [x(t)] = \int_{0}^{\infty} e^{(2-s)t} dt = \frac{1}{s - 2}
$$
The **ROC** for this signal is $s > 2$, meaning the region of convergence lies to the right of the line $x = 2$ on the complex plane.

#### Desmos Graph for Exponential Signal (with $a = 2$):

```desmos-graph
x > 2
```

This will shade the right side of the $s$-plane where $s > 2$, indicating the **ROC** for the exponential signal with $a = 2$.

### 4. Anti-causal Unit Step Signal

#### Definition and Signal:
For an **anti-causal unit step signal**, the function is defined as:
$$
x(t) = u(-t)
$$
This signal is non-zero for negative values of $t$, and it is represented by a step at $t = 0$ with values of 1 for $t < 0$.

#### Laplace Transform:
By the definition of the **Laplace Transform**:
$$
X(s) = \int_{-\infty}^{\infty} x(t) e^{-st} dt
$$
Substituting $x(t) = u(-t)$:
$$
X(s) = \int_{-\infty}^{0} e^{-st} dt = \left[\frac{e^{-st}}{-s}\right]_{-\infty}^{0}
$$
Evaluating the limits:
$$
X(s) = \frac{1}{-s} \left[e^{0} - e^{-\infty}\right] = \frac{1}{-s} \cdot [1 - 0] = -\frac{1}{s}
$$

Thus, the Laplace transform for the anti-causal unit step signal is:
$$
X(s) = -\frac{1}{s}, \quad \text{for} \, \sigma < 0
$$

#### Region of Convergence (ROC):
The **ROC** for this anti-causal signal is for $s < 0$, as the signal is only non-zero in the negative time domain.

### Important Note:
- **Magic Point**: If a signal is anti-causal, the ROC will be left-sided, meaning the ROC includes the negative half of the $s$-plane.
  
This example demonstrates how the Laplace Transform of an anti-causal signal differs from the causal case, and how the ROC covers the left side of the complex $s$-plane.

```desmos-graph
x < 0
```

### Summary and Desmos Graphs for Laplace Transformations

#### 2. Exponential Signal with Negative Shift
The function is:
$$
x(t) = e^{-3t} u(-t)
$$
Taking the Laplace transform:
$$
\mathcal{L}[x(t)] = \int_{-\infty}^{0} e^{(-3-s)t} dt
$$
After solving:
$$
X(s) = \frac{1}{s+3}
$$
The **ROC** is for $\sigma < -3$.

##### Desmos Graph:
```desmos-graph
x < -3
```

This shades the left side of the $s$-plane where $\sigma < -3$, indicating the region of convergence (ROC).

---

#### 3. Exponential Signal with Positive Shift
The function is:
$$
x(t) = e^{bt} u(t)
$$
Taking the Laplace transform:
$$
\mathcal{L}[x(t)] = \int_{0}^{\infty} e^{(b-s)t} dt
$$
After solving:
$$
X(s) = \frac{1}{s-b}
$$
The **ROC** is for $\sigma > b$.

##### Desmos Graph:
For $b = 5$ as an example:
```desmos-graph
x > 5
```

This shades the right side of the $s$-plane where $\sigma > 5$, indicating the ROC.

---

#### 4. Exponential Signal with a Positive and Negative Shift
The function is:
$$
x(t) = e^{2t} u(-t)
$$
Taking the Laplace transform:
$$
\mathcal{L}[x(t)] = \int_{-\infty}^{0} e^{(2-s)t} dt
$$
After solving:
$$
X(s) = \frac{1}{s-2}
$$
The **ROC** is for $\sigma < 2$.

##### Desmos Graph:
```desmos-graph
x < 2
```

This shades the left side of the $s$-plane where $\sigma < 2$, indicating the ROC for this signal.

---

These graphs and summaries provide a visual representation of the Laplace transform and the region of convergence (ROC) for various signals, both causal and anti-causal.

