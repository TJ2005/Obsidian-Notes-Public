---
Title: Signals & System Lecture 17
Status: 
marker: 
tags: 
Date: 2024.11.05
Time: 10:21
---
# Signals & System Lecture 17

# Main note
To find the Z-transform of the given signal:

$$
y(n) = 3^n u(n) \cdot (-10)^n u(-n-1)
$$

we need to analyze the components separately and understand their contributions in the Z-domain.

### Step 1: Analyzing the Signal Components

1. **First Term: \(3^n u(n)\)**

   This is a **right-sided sequence** where \(u(n)\) is the unit step function that is 1 for \(n \geq 0\) and 0 otherwise. Thus, \(3^n u(n)\) exists only for \(n \geq 0\).

   The Z-transform of \(3^n u(n)\) is given by:
   $$
   Z\{3^n u(n)\} = \frac{1}{1 - 3z^{-1}}, \quad |z| > 3
   $$

2. **Second Term: \((-10)^n u(-n-1)\)**

   This is a **left-sided sequence** where \(u(-n-1)\) is a step function that is 1 for \(n \leq -1\) and 0 otherwise. Thus, \((-10)^n u(-n-1)\) exists only for \(n \leq -1\).

   The Z-transform of \((-10)^n u(-n-1)\) is:
   $$
   Z\{(-10)^n u(-n-1)\} = \frac{z}{z + 10}, \quad |z| < 10
   $$

### Step 2: Finding the Z-Transform of \(y(n)\)

Since $(y(n) = 3^n u(n) \cdot (-10)^n u(-n-1)$, we notice that:
- $(3^n u(n) is non-zero only for n \geq 0$,
- $(-10)^n u(-n-1)$ is non-zero only for $n \leq -1$.

Thus, their **product** \(y(n)\) is **zero for all \(n\)** (since they do not overlap over any value of \(n\)).

### Conclusion

Since \(y(n) = 0\) for all \(n\), the Z-transform of \(y(n)\) is:

$$
Y(z) = 0
$$

### Initial Value and Final Value Theorem for Z-Transform

1. **Initial Value Theorem**:  
   The initial value theorem provides the value of a discrete-time signal at $n = 0$ directly from its Z-transform.

   $$ x(0) = \lim_{z \to \infty} X(z) $$

   where $X(z)$ is the Z-transform of the signal $x(n)$.

2. **Final Value Theorem**:  
   The final value theorem gives the steady-state (long-term) value of a discrete-time signal, assuming the limit exists.

   $$ \lim_{n \to \infty} x(n) = \lim_{z \to 1} (z - 1) X(z) $$

   The final value theorem is valid only if all poles of $(z - 1) X(z)$ lie inside the unit circle, except for a simple pole at $z = 1$.

---

### Solving $X(z) = \frac{1}{1 - z^2}$

Given:
$$ X(z) = \frac{1}{1 - z^2} $$

#### Step 1: Perform Partial Fraction Expansion

Rewrite $X(z)$ as:
$$ X(z) = \frac{1}{(1 - z)(1 + z)} $$

Using partial fraction decomposition:
$$ X(z) = \frac{A}{1 - z} + \frac{B}{1 + z} $$

Multiplying through by $(1 - z)(1 + z)$:
$$ 1 = A(1 + z) + B(1 - z) $$

Expanding and collecting terms:
$$ 1 = A + Az + B - Bz $$
$$ 1 = (A + B) + (A - B)z $$

Equating coefficients:
1. For the constant term: $A + B = 1$
2. For the $z$ term: $A - B = 0$

Solving these equations:
- From $A - B = 0$, we get $A = B$
- Substitute $A = B$ into $A + B = 1$: $2A = 1 \Rightarrow A = \frac{1}{2}$

Thus, $A = \frac{1}{2}$ and $B = \frac{1}{2}$.

Now, we can rewrite $X(z)$ as:
$$ X(z) = \frac{1}{2} \cdot \frac{1}{1 - z} + \frac{1}{2} \cdot \frac{1}{1 + z} $$

#### Step 2: Find the Inverse Z-Transform

Using standard Z-transform pairs:
- The inverse Z-transform of $\frac{1}{1 - z}$ is $u(n)$
- The inverse Z-transform of $\frac{1}{1 + z}$ is $(-1)^n u(n)$

Therefore:
$$ x(n) = \frac{1}{2} u(n) + \frac{1}{2} (-1)^n u(n) $$

So, the time-domain sequence $x(n)$ is:
$$ x(n) = \frac{1}{2} + \frac{1}{2}(-1)^n $$

---

### Applying Initial and Final Value Theorems

1. **Initial Value**:  
   Using the initial value theorem:
   $$ x(0) = \lim_{z \to \infty} X(z) $$
   Substituting $X(z) = \frac{1}{1 - z^2}$:
   $$ x(0) = \lim_{z \to \infty} \frac{1}{1 - z^2} = 0 $$

2. **Final Value**:  
   Using the final value theorem:
   $$ \lim_{n \to \infty} x(n) = \lim_{z \to 1} (z - 1) X(z) $$
   Substituting $X(z) = \frac{1}{1 - z^2}$:
   $$ \lim_{n \to \infty} x(n) = \lim_{z \to 1} (z - 1) \cdot \frac{1}{1 - z^2} $$
   Simplifying $\frac{1}{1 - z^2}$ as $\frac{1}{(1 - z)(1 + z)}$:
   $$ \lim_{n \to \infty} x(n) = \lim_{z \to 1} \frac{z - 1}{(1 - z)(1 + z)} = \lim_{z \to 1} \frac{1}{1 + z} = \frac{1}{2} $$

---

### Summary of Results

- **Initial Value**: $x(0) = 0$
- **Final Value**: $\lim_{n \to \infty} x(n) = \frac{1}{2}$
- **Time-Domain Expression**: $x(n) = \frac{1}{2} + \frac{1}{2}(-1)^n$

# References


###### Information
- date: 2024.11.05
- time: 10:21