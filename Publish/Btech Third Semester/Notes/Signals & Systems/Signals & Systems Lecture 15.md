# ZTransform
# Z-transform

The **Z-transform** is a powerful tool used in signal processing and control theory, primarily for analyzing discrete-time systems. It is a generalization of the discrete-time Fourier transform (DTFT) and allows us to work with discrete signals in the frequency domain.

## Definition

For a discrete-time signal \( x[n] \), the Z-transform \( X(z) \) is defined as:

$$
X(z) = \sum_{n=-\infty}^{\infty} x[n] z^{-n}
$$

where:
- \( x[n] \) is the discrete-time signal (sequence),
- \( z \) is a complex variable.

### Region of Convergence (ROC)
The Z-transform only exists if the sum converges. The set of values of \( z \) for which the Z-transform converges is called the **Region of Convergence (ROC)**.

### Inverse Z-transform
The inverse Z-transform is used to convert back from the Z-domain to the time domain. It is given by:

$$
x[n] = \frac{1}{2\pi j} \oint_{C} X(z) z^{n-1} dz
$$

where \( C \) is a contour in the complex plane that encircles the origin and lies within the ROC.

## Properties of Z-transform

1. **Linearity:**
   $$ Z\{a x_1[n] + b x_2[n]\} = a X_1(z) + b X_2(z) $$

2. **Time Shifting:**
   $$ Z\{x[n-k]\} = z^{-k} X(z) $$

3. **Scaling in the Z-domain:**
   $$ Z\{a^n x[n]\} = X\left(\frac{z}{a}\right) $$

4. **Convolution:**
   $$ Z\{x_1[n] * x_2[n]\} = X_1(z) X_2(z) $$

5. **Differentiation in the Z-domain:**
   $$ Z\{n x[n]\} = -z \frac{dX(z)}{dz} $$

### Applications of Z-transform

- Analysis and design of discrete-time control systems.
- Solving difference equations.
- Digital signal processing (DSP).

# Questions
## Question 1
$$X(N)=u(n)$$
The Z-transform of the unit step function \( $u(n)$ \) is given by:

$$
Z\{u(n)\} = \sum_{n=0}^{\infty} u(n) z^{-n} = \sum_{n=0}^{\infty} z^{-n}
$$

This is a geometric series, and for \( |z| > 1 \), it converges to:

$$
Z\{u(n)\} = \frac{1}{1 - z^{-1}} = \frac{z}{z - 1}
$$

Thus, the Z-transform of \( u(n) \) is:

$$
X(z) = \frac{z}{z - 1}, \quad \text{for} \quad |z| > 1
$$
## Question 2
The given sequence is \( $x(n) = (0.5z^{-1})^n$ \). To find its Z-transform, we use the standard formula for the Z-transform of \( a^n u(n) \), where \( u(n) \) is the unit step function.

For \( $x(n) = (0.5z^{-1})^n = \left( \frac{0.5}{z} \right)^n$ \), the Z-transform is:

$$
Z\{(0.5z^{-1})^n\} = \sum_{n=0}^{\infty} \left( \frac{0.5}{z} \right)^n
$$

This is a geometric series and converges for \( $\left| \frac{0.5}{z} \right| < 1 $\), or \( $|z| > 0.5$ \). The sum of the geometric series is:

$$
X(z) = \frac{1}{1 - \frac{0.5}{z}} = \frac{z}{z - 0.5}
$$

Thus, the Z-transform of \( $(0.5z^{-1})^n$\) is:

$$
X(z) = \frac{z}{z - 0.5}, \quad \text{for} \quad |z| > 0.5
$$

## Question 3
