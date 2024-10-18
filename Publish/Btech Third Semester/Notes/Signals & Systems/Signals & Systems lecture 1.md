---
Title: Signals & Systems lecture 1
Status: 
marker: 
tags: 
Date: 2016-07-16
Time: 10:07
---
# Signals & Systems Lecture 1

**Date**: 16-07-2024

## Index

- [Signal](#signal)
- [System](#system)
- [Types of Signals](#types-of-signals)
  - [Analog](#analog)
  - [Digital Continuous](#digital-continuous)
  - [Explanation of Digital Continuous Signals](#explanation-of-digital-continuous-signals)
  - [Sampling](#sampling)
  - [Nyquist Sampling Theorem](#nyquist-sampling-theorem)
  - [Discrete Signals](#discrete-signals)
  - [Digital](#digital)
- [Classification of Signals](#classification-of-signals)
  - [Periodic Signals](#periodic-signals)
  - [Non-Periodic (Aperiodic) Signals](#non-periodic-aperiodic-signals)
  - [Comparison Table](#comparison-table)
- [Non-Indexed](#non-indexed)
- [References](#references)

---

## Introduction to Signals and Systems

### Learning Outcomes
- How to identify different types of signals.
- Determine which transform is best suited for a given signal.
- Develop a system using signals.

---

## Content

### Signals & Systems

#### Signal
A signal carries information or data. It can take various forms, such as electrical voltage, sound waves, or digital bits.

#### System
A system is an arrangement or combination of different physical components designed to achieve a specific objective or goal. It processes input signals to produce output signals.

### Types of Signals

#### Analog
Analog signals, also called Continuous Time Signals, vary smoothly over time. Examples include sound waves, temperature variations, and sine waves. These signals are represented mathematically as $( x(t) ).$

#### Digital Continuous
Digital continuous signals, also known as Discrete Time Signals, exist at specific intervals of time. They are continuous in nature but sampled at discrete time intervals. These signals are represented as $( x[n] )$.

### Explanation of Digital Continuous Signals
Imagine an electrical switch that turns on every 1 second. Thus, the sine wave will be only on for one second and the signal will have a varying amplitude.

#### Sampling
Sampling converts continuous signals into discrete signals. It involves measuring the signal's amplitude at uniform intervals. The process uses a Sample and Hold Signals circuit to maintain the amplitude until the next sample.

#### Nyquist Sampling Theorem
The theorem states that the sampling frequency $( F_s )$ should be greater than twice the maximum frequency ($( F_{max} ))$ of the signal to accurately reconstruct the original signal.
$[ F_s \geq 2 \cdot F_{max} ]$

#### Discrete Signals
Digital Signals are quantized to fixed amplitude levels, distinguishing them from digital continuous signals. Digital time signals are represented by $( x[n] )$.

#### Digital
Digital and discrete are terms used interchangeably with respect to time. Digital signals are represented as a sequence of numbers, typically in binary form.

### Classification of Signals

#### Periodic Signals
A signal $( x(t) )$ or $( x[n] )$ is periodic if it repeats after a fundamental time period $( T )$ or a fundamental sample period $( N )$. The conditions are:
$$ x(t + T) = x(t) $$ $$ x(n + N) = x(n) $$


#### Non-Periodic (Aperiodic) Signals
A signal $( x(t) ))$ or $( x[n] )$ is non-periodic if it does not repeat after a fundamental time period $( T )$ or a fundamental sample period $( N )$.

### Comparison Table

| Periodic Signal         | Non-Periodic (Aperiodic) Signal |
|-------------------------|---------------------------------|
| Repeats after $( T )$   | Does not repeat                |
| Examples: Sine wave, Cosine wave | Examples: Speech, Music |

### Non-Indexed
- Further topics and examples will be covered in subsequent lectures.

### References
- Textbooks on Signals and Systems.
- Lecture notes and additional resources provided during the course.

---

