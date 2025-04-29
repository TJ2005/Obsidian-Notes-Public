
### **Z-Transform**

The Z-transform of a discrete-time signal $x[n]$ is defined as:

$$
X(z) = \mathcal{Z}\{x[n]\} = \sum_{n=-\infty}^{\infty} x[n] z^{-n}
$$

### **Fourier Transform**

The Fourier transform of a continuous-time signal $x(t)$ is defined as:

$$
X(f) = \mathcal{F}\{x(t)\} = \int_{-\infty}^{\infty} x(t) e^{-j2\pi ft} \, dt
$$

### **Laplace Transform**

The Laplace transform of a continuous-time signal $x(t)$ is defined as:

$$
X(s) = \mathcal{L}\{x(t)\} = \int_{0}^{\infty} x(t) e^{-st} \, dt
$$

### **Initial and Final Value Theorems**

#### Initial Value Theorem

For a Laplace transform $X(s)$, the initial value of $x(t)$ at $t = 0^+$ is given by:

$$
x(0^+) = \lim_{s \to \infty} sX(s)
$$

#### Final Value Theorem

For a Laplace transform $X(s)$, the final value of $x(t)$ as $t \to \infty$ is given by:

$$
\lim_{t \to \infty} x(t) = \lim_{s \to 0} sX(s)
$$

### **Impulse Response from Transfer Function**

The impulse response $h(t)$ of a system with transfer function $H(s)$ is given by the inverse Laplace transform:

$$
h(t) = \mathcal{L}^{-1}\{H(s)\}
$$

### **Properties of Fourier Transform**

| **Property**                                                                 | **Time Domain**                                                                 | **Frequency Domain**                                                                 |
|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|
| Linearity                                                                    | $a x_1(t) + b x_2(t)$                                                         | $a X_1(f) + b X_2(f)$                                                               |
| Time Shifting                                                                | $x(t - t_0)$                                                                  | $X(f) e^{-j2\pi ft_0}$                                                             |
| Frequency Shifting (Modulation)                                              | $x(t) e^{j2\pi f_0 t}$                                                        | $X(f - f_0)$                                                                       |
| Time Scaling                                                                 | $x(at)$                                                                       | $\frac{1}{|a|} X\left(\frac{f}{a}\right)$                                          |
| Convolution                                                                  | $(x_1 * x_2)(t) = \int_{-\infty}^{\infty} x_1(\tau) x_2(t - \tau) \, d\tau$ | $X_1(f) X_2(f)$                                                                     |
| Duality                                                                      | $X(t)$                                                                        | $x(-f)$                                                                            |
| Differentiation in Time                                                      | $\frac{d}{dt} x(t)$                                                            | $j2\pi f X(f)$                                                                      |
| Differentiation in Frequency                                                 | $-jt x(t)$                                                                    | $\frac{d}{df} X(f)$                                                                 |
| Parseval's Theorem                                                           | $\int_{-\infty}^{\infty} |x(t)|^2 \, dt$                                                    | $\int_{-\infty}^{\infty} |X(f)|^2 \, df$                                                    |

---

These formulae and properties are fundamental in signal processing and systems analysis, providing the tools necessary to analyze and design systems in both the time and frequency domains.
### **Common Laplace Transforms**


| $f(t)$                                                                 | $F(s)$                                                                 |
|-----------------------------------------------------------------------|-----------------------------------------------------------------------|
| $e^{at}$                                                              | $\frac{1}{s - a}$, where $\Re(s) > a$                                 |
| $e^{-at}$                                                             | $\frac{1}{s + a}$, where $\Re(s) > -a$                                |
| $u(t)$                                                                | $\frac{1}{s}$, where $\Re(s) > 0$                                     |
| $u(t - t_0)$                                                         | $\frac{e^{-t_0 s}}{s}$, where $\Re(s) > 0$                            |
| $\sin(at)$                                                            | $\frac{a}{s^2 + a^2}$                                                 |
| $\cos(at)$                                                            | $\frac{s}{s^2 + a^2}$                                                 |
| $\sin(at) u(t)$                                                       | $\frac{a}{s^2 + a^2}$, where $\Re(s) > 0$                             |
| $\cos(at) u(t)$                                                       | $\frac{s}{s^2 + a^2}$, where $\Re(s) > 0$                             |
| $t^n$                                                                | $\frac{n!}{s^{n+1}}$, where $\Re(s) > 0$                              |
| $\delta(t)$                                                          | $1$                                                                   |
| $t u(t)$                                                             | $\frac{1}{s^2}$                                                       |
| $e^{at} u(t)$                                                        | $\frac{1}{s - a}$, where $\Re(s) > a$                                 |

---

### **Common Fourier Transforms**

| $f(t)$                                                                 | $F(\omega)$                                                                 |
|-----------------------------------------------------------------------|-----------------------------------------------------------------------|
| $e^{j \omega_0 t}$                                                    | $2\pi \delta(\omega - \omega_0)$                                     |
| $e^{-j \omega_0 t}$                                                   | $2\pi \delta(\omega + \omega_0)$                                     |
| $u(t)$                                                                | $\frac{1}{j\omega} + \pi \delta(\omega)$                             |
| $\sin(\omega_0 t)$                                                    | $\pi \left[ \delta(\omega - \omega_0) - \delta(\omega + \omega_0) \right]$ |
| $\cos(\omega_0 t)$                                                    | $\pi \left[ \delta(\omega - \omega_0) + \delta(\omega + \omega_0) \right]$ |
| $\text{rect}(t/T)$                                                    | $T \cdot \text{sinc}(\omega T)$                                       |
| $e^{-at^2}$                                                          | $\sqrt{\frac{\pi}{a}} e^{-\frac{\omega^2}{4a}}$                       |
| $\delta(t)$                                                          | $1$                                                                   |

---

### **Common Z-Transforms**

| $x[n]$                                                                 | $X(z)$                                                                 |
|-----------------------------------------------------------------------|-----------------------------------------------------------------------|
| $a^n u[n]$                                                            | $\frac{1}{1 - az^{-1}}$, for $|z| > |a|$                               |
| $u[n]$                                                                | $\frac{1}{1 - z^{-1}}$, for $|z| > 1$                                  |
| $n^k u[n]$                                                            | $\frac{k!}{(1 - z^{-1})^{k+1}}$, for $|z| > 1$                         |
| $\delta[n]$                                                          | $1$                                                                   |
| $\sin(\omega_0 n) u[n]$                                               | $\frac{\sin(\omega_0)}{1 - 2z^{-1} \cos(\omega_0) + z^{-2}}$, for $|z| > 1$ |
| $\cos(\omega_0 n) u[n]$                                               | $\frac{1 - z^{-1} \cos(\omega_0)}{1 - 2z^{-1} \cos(\omega_0) + z^{-2}}$, for $|z| > 1$ |
| $r^n u[n]$                                                           | $\frac{1}{1 - rz^{-1}}$, for $|z| > |r|$                               |
| $e^{-a n} u[n]$                                                      | $\frac{1}{1 - ae^{-1}z^{-1}}$, for $|z| > a$                           |
| $n u[n]$                                                             | $\frac{z}{(z - 1)^2}$, for $|z| > 1$                                  |

---

### **Conclusion**

Here are the **tables** for common transforms:

1. **Laplace Transforms**: These are used primarily for analyzing continuous-time signals and systems, and they have many common forms like exponential functions, sinusoids, and step functions.

2. **Fourier Transforms**: Used for converting signals from the time domain to the frequency domain, particularly helpful in analyzing frequency content. The transforms of sinusoidal signals, step functions, and impulses are frequently used.

3. **Z-Transforms**: Primarily used in discrete-time signal processing, Z-transforms are useful for analyzing discrete-time signals, especially when dealing with difference equations.

These tables and methods are the foundation for analyzing and solving problems in signal processing and systems theory.

![[Signals and System List of Signals]]