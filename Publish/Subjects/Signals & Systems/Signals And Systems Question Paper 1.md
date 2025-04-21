---
Title: Signals And Systems Question Paper 1
Status: 
marker:
  - "[[Question Bank]]"
  - "[[Exam Paper]]"
tags: 
Date: 2025.02.13
Time: 09:28
---
# Signals And Systems Question Paper 1

---

### **Continuous-Time Formulas**

1. **Laplace Transform**:
   The Laplace transform $X(s)$ of a continuous-time signal $x(t)$ is given by:
   $$
   X(s) = \int_{0}^{\infty} x(t) e^{-st} \, dt
   $$
   where $s$ is a complex variable: $s = \sigma + j\omega$.

2. **Inverse Laplace Transform**:
   The inverse Laplace transform is used to find $x(t)$ from $X(s)$ and can be computed using:
   $$
   x(t) = \mathcal{L}^{-1} \{X(s)\}
   $$
   This can be computed using partial fraction expansion or the residue theorem, depending on the problem.

3. **Fourier Transform**:
   The Fourier Transform of a continuous-time signal $x(t)$ is given by:
   $$
   X(f) = \int_{-\infty}^{\infty} x(t) e^{-j2\pi f t} \, dt
   $$
   where $f$ is the frequency variable.

4. **Inverse Fourier Transform**:
   The inverse Fourier Transform is used to recover $x(t)$ from $X(f)$ and is given by:
   $$
   x(t) = \int_{-\infty}^{\infty} X(f) e^{j2\pi f t} \, df
   $$

5. **Convolution of Continuous-Time Signals**:
   The convolution $y(t) = (x * h)(t)$ of two continuous-time signals $x(t)$ and $h(t)$ is defined as:
   $$
   y(t) = \int_{-\infty}^{\infty} x(\tau) h(t - \tau) \, d\tau
   $$

---

### **Discrete-Time Formulas**

6. **Z-Transform**:
   The Z-transform $X(z)$ of a discrete-time signal $x[n]$ is given by:
   $$
   X(z) = \sum_{n=-\infty}^{\infty} x[n] z^{-n}
   $$
   where $z$ is a complex variable.

7. **Inverse Z-Transform**:
   The inverse Z-transform is used to recover $x[n]$ from $X(z)$ and is generally computed using methods like partial fraction expansion or long division.

8. **Fourier Transform (Discrete-Time)**:
   The Discrete-Time Fourier Transform (DTFT) of a discrete-time signal $x[n]$ is given by:
   $$
   X(f) = \sum_{n=-\infty}^{\infty} x[n] e^{-j2\pi f n}
   $$
   where $f$ is the frequency variable.

9. **Inverse Fourier Transform (Discrete-Time)**:
   The inverse DTFT is used to recover $x[n]$ from $X(f)$ and is given by:
   $$
   x[n] = \int_{-\infty}^{\infty} X(f) e^{j2\pi f n} \, df
   $$

10. **Convolution of Discrete-Time Signals**:
   The convolution $y[n] = (x * h)[n]$ of two discrete-time signals $x[n]$ and $h[n]$ is defined as:
   $$
   y[n] = \sum_{m=-\infty}^{\infty} x[m] h[n - m]
   $$

---

### Key Differences Between Continuous and Discrete:

- The **Laplace transform** is for continuous-time signals, while the **Z-transform** is for discrete-time signals.
- For both continuous and discrete signals, there are corresponding Fourier transforms (continuous-time Fourier transform and discrete-time Fourier transform), but the DTFT uses summation over discrete indices, while the CTFT uses integration over continuous time.



# References


###### Information
- date: 2025.02.13
- time: 09:28