---
Title: Signals & System Lecture 12
Status: 
marker:
  - "[[btech]]"
  - "[[Signals & System]]"
tags:
  - BTech
Date: 2024.09.09
Time: 10:35
---
# Signals & System Lecture 12

# Notes from 5-9-2024

## 1. Time Shifting Properties

- If $x(t) \xrightarrow{LT} X(s)$, ROC:
  - **Delay**: $$ x(t - K) \xrightarrow{LT} e^{-Ks} X(s) $$, same ROC
  - **Advance**: $$ x(t + K) \xrightarrow{LT} e^{+Ks} X(s) $$, same ROC

## 2. Multiplication

- If $x(t) \xrightarrow{LT} X(s)$, ROC:
  - $$ t \cdot x(t) \xrightarrow{LT} - \frac{d}{ds} X(s) $$, same ROC

  Always draw ROC whether mentioned or not.

## 3. Multiplication by Exponential Property

- If $x(t) \xrightarrow{LT} X(s)$, ROC:
  - $$ e^{at} \cdot x(t) \xrightarrow{LT} X(s - a) $$, ROC may change
  - $$ e^{-at} \cdot x(t) \xrightarrow{LT} X(s + a) $$, new ROC

## 4. Scaling in Time Domain

- If $x(at) \xrightarrow{LT} \frac{1}{|a|} X\left(\frac{s}{a}\right)$, ROC:
  - For $a > 1$, ROC is scaled by a factor of $a$
  - For $a < 1$, ROC is compressed

## 5. Time Differentiation

- If $\frac{d}{dt} x(t) \xrightarrow{LT} s X(s)$, ROC:
  - The ROC remains unchanged, provided the system is causal.

## 6. Time Integration

- If $\int_{-\infty}^{t} x(\tau) d\tau \xrightarrow{LT} \frac{X(s)}{s}$, ROC:
  - ROC might change based on the behavior of the integrand.


# References


###### Information
- date: 2024.09.09
- time: 10:35