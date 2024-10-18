---
Title: Signals & System Lecture 13
Status: 
marker:
  - "[[Fourier Transform]]"
  - "[[Signals]]"
tags:
  - BTech
Date: 2024.09.28
Time: 10:50
---
# Signals & System Lecture 13

## Fourier Transform Basics

For continuous-time signals, the Fourier transform of a function \( x(t) \) is defined as:

$$
X(\omega) = \mathcal{F}\{x(t)\} = \int_{-\infty}^{\infty} x(t) e^{-j\omega t} dt
$$

Where:
- \( X(\omega) \) is the Fourier transform of \( x(t) \)
- \( \omega \) is the angular frequency

## Inverse Fourier Transform

The inverse Fourier transform is given by:

$$
x(t) = \mathcal{F}^{-1}\{X(\omega)\} = \frac{1}{2\pi} \int_{-\infty}^{\infty} X(\omega) e^{j\omega t} d\omega
$$

This allows us to recover the time-domain signal from its frequency-domain representation.

### Important Note:
- **No need of ROC (Region of Convergence)**: For Fourier transforms, unlike the Laplace transform, there is no requirement for specifying the ROC.

---

## Example: Fourier Transform of a Given Signal

Find the Fourier transform of the following signal:

### Given Signal:
$$
x(t) = e^{-at} u(t)
$$

Where:
- \( u(t) \) is the unit step function
- \( a > 0 \)

### Solution:

The Fourier transform of $( x(t) = e^{-at} u(t)$ is:

$$
X(\omega) = \int_{0}^{\infty} e^{-at} e^{-j\omega t} dt
$$

We solve this integral:

$$
X(\omega) = \int_{0}^{\infty} e^{-(a + j\omega)t} dt
$$

This is a standard exponential integral:

$$
X(\omega) = \left[ \frac{1}{a + j\omega} \right]_{0}^{\infty}
$$

Evaluating the integral gives:

$$
X(\omega) = \frac{1}{a + j\omega}
$$

Thus, the Fourier transform of \( x(t) = e^{-at} u(t) \) is:

$$
X(\omega) = \frac{1}{a + j\omega}
$$

---

### Summary:
- The Fourier transform of an exponentially decaying signal multiplied by a unit step is $( \frac{1}{a + j\omega})$.
