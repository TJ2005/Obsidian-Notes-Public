---
Title: Signals & Systems Lecture 4
Status: 
marker: 
tags: 
Date: 2024.07.25
Time: "{time:HH:mm}}"
---
# Signals & Systems Lecture 4

## Index

1. [Even and Odd Part of the Signal](#even-and-odd-part-of-the-signal)
    - [Question 1](#question-1)
        - [Answer](#question-1-answer)
    - [Question 2](#question-2)
        - [Answer](#question-2-answer)
    - [Question 3](#question-3)
2. [Explain Standard Continuous Time Signal](#explain-standard-continuous-time-signal)
    - [Impulsing](#impulsing)
    - [Step Signal](#step-signal)
    - [Ramping](#ramping)
    - [Exponential](#exponential)
3. [Explain Standard Discrete Time Signal](#explain-standard-discrete-time-signal)
    - [Impulsing](#discrete-impulsing)
    - [Step Signal](#discrete-step-signal)
    - [Ramping](#discrete-ramping)
    - [Exponential](#discrete-exponential)

# Main note

## Even And Odd Part of the signal
#### Question 1
$x(t)=e^t$
##### Answer
$x(-t)=e^{-t}$
###### Even
The even part of a signal \( x(t) \), denoted as \( X_e(t) \), is given by:
$X_e(t) = \frac{1}{2} [x(t) + x(-t)]$
$X_e(t) = \frac{1}{2} [e^t + e^{-t}]$
###### Odd
For an odd signal it will be
$X_e(t) = \frac{1}{2} [x(t) - x(-t)]$
$X_e(t) = \frac{1}{2} [e^{t} - e^{-t}]$

#### Question 2
$x(t)=3+2t+5t^2$
##### Answer
$x(-t)=3+2(-t)+5(-t^2)$
$x(-t)=3-2t+5t^2$

###### Even
The even part of a signal \( x(t) \), denoted as \( X_e(t) \), is given by:
$X_e(t) = \frac{1}{2} [x(t) + x(-t)]$
$X_e(t) = \frac{1}{2} [~3+2t+5t^2~+~3-2t+5t^2]$
$X_e(t) = \frac{1}{2} [~6+10t^2]$
$X_e(t) = ~2+5t^2$

###### Odd
For an odd signal it will be
$X_e(t) = \frac{1}{2} [x(t) - x(-t)]$

$X_o(t) = \frac{1}{2} [(3 + 2t + 5t^2) - (3 - 2t + 5t^2)]$
$X_o(t) = \frac{1}{2} [x(t) - x(-t)]$
$X_o(t) = \frac{1}{2} [3 + 2t + 5t^2 - 3 + 2t - 5t^2]$
$X_o(t) = \frac{1}{2} [2t + 2t]$
$X_o(t) = \frac{1}{2} [4t]$
$X_o(t) = 2t$

### Question 3

### Explain Standard Continuous Time Signal
#### Impulsing
It is a [[signal]] with infinite magnitude with zero duration But with an area of A.
![[SNS 1.excalidraw]]

$\delta (t) = \infty; ~~~t=0$
$\delta (t) = 0; ~~~t\neq0$
$\int_{-\infty}^{\infty} d(t) \, dt = a$

### Step Signal
$$x(t)=A~;~t\geq0$$
$$x(t)=0~;~t<0$$

![[SNS 3.excalidraw]]

### Ramping
$$x(t) = At~;~t\geq0$$
$$x(t) = 0~;~t>0$$
![[Drawing 2024-07-25 09.47.41.excalidraw]]

### Exponential
$$ x(t)=Ae^{bt}~;~t\geq0$$
$$ x(t)=0~;~t>0$$
When b is positive then it is exponentially increasing and when b is negative it is exponentially decaying.
![[SNS 6.excalidraw]]

## Explain Standard Discrete Time Signal

### Impulsing

##### Equation
$$ \delta(n)=1; n = 0$$
$$ \delta(n)=0; n\neq0$$
##### Graphical Representation

![[SNS 2.excalidraw]]

### Step Signal
##### Equation
$$ x(n)=A;~n\geq0$$
$$ x(n)=0;~n<0$$
##### Graphical Representation

![[SNS3.excalidraw]]

### Ramping
##### Equation
$$ x(n) = An;~n\geq0$$
$$ x(n) = 0;~n<0$$

##### Graphical Representation
![[SNS 5.excalidraw]]

### Exponential
##### Equation
$$ x(n) = A e^{bn};~n\geq0$$
$$ x(n) = 0;~n<0$$
##### Graphical Representation
![[SNS 7.excalidraw]]
# References


###### Information
- date:: 2024.07.25
- time:: 09:07