---
Title: Signals & Systems Exponentials and Sinusodials
Status: 
marker: 
tags: 
Date: 2024.08.20
Time: 02:49
---
Learn Eulers formula
# Continuous-Time Complex Exponential and Sinusoidal Signals
In this section We introduce several basic continuous-time and discrete-time signals. Not only do these signals occur frequently, but they also serve as basic building blocks from which we can construct many other signals.

The continuous-time complex exponential signal is of the form
$$x(t)\,=\,C e^{a t},$$
where $C$ and $a$ are, in general, complex numbers. Depending upon the values of these parameters, the complex exponential can exhibit several different characteristics.

## Real Exponential Signals
if $C$ and $a$ are **real** *(in which case x(t) is called a real exponential)*, there are basically two types of behavior.

If a is positive, then as t increases x(t) is a growing exponential, a form that is used in describing many different physical processes, including chain reactions in atomic explosions and complex chemical reactions. 

If a is negative, then x(t) is a decaying exponential, a signal that is also used to describe a wide variety of phenomena, including the process of radioactive decay and the responses of RC circuits and damped mechanical systems.
![[IMG-20241016143302145.png]]
## Periodic Complex Exponential and Sinusoidal Signals

### For Continuous
Complex exponentials is obtained by constraining a to be purely imaginary.
$$x(t)\,=\,e^{j\omega_{0}t}.$$
here $\omega_0 = 2\pi*f$

If this signal was to be periodic referring [[Signals & System Transformation of the independent variable#^50ce01|Periodicity]]

$$e^{j\omega_{0}t}\:=\:e^{j\omega_{0}(t+T)}.$$
$$e^{j\omega_{0}(t+T)}\,=\,e^{j\omega_{0}t}e^{j\omega_{0}T},$$
On solving this equation like this
$$\frac{e^{j\omega_{0}(t+T)}}{e^{j\omega_{0}(t+T)}}\,=\,\frac{e^{j\omega_{0}t}e^{j\omega_{0}T}}{e^{j\omega_{0}(t+T)}},$$

$$1\,=\,\frac{e^{j\omega_{0}t}e^{j\omega_{0}T}}{e^{j\omega_{0}(t+T)}},$$

$$1\,=\,\frac{e^{j\omega_{0}t}e^{j\omega_{0}T}}{e^{j\omega_{0}(t+T)}},$$

$$1\,=\,\frac{e^{j\omega_{0}t}e^{j\omega_{0}T}}{e^{j\omega_{0}t}*{e^{j\omega_{0}T}}},$$
it follows that for periodicity, we must have
$$e^{j\omega_{0}T}\,=\,1.$$

thus by simply putting the angular frequency $\omega_0=0$ we can say that $x(t)=1$ which makes this function periodic for any T.

But if $w_0\neq0$ then the fundamental period $T_0$ of $x(t)$ will be given as such
$\because~\omega_0=2\pi f$ and $j$ and $T$ are constant
$\therefore \text{we can say that}$  
$$T_{0}\,=\,\frac{2\pi}{|\omega_{0}|}.$$A signal closely related to the periodic complex exponential is the sinusoidal signal
$$x(t)\,=\,A\cos(\omega_{0}t+\phi),$$

#### General Complex Exponential Signals
The most general case of a complex exponential can be expressed and interpreted in terms of the two cases we have examined so far: the real exponential and the periodic complex exponential. Specifically, consider a complex exponential $Ce^{at}$ where $C$ is expressed in polar form and a in rectangular form. That is,
Page 51 study.
$$\begin{array}{c}{{C=|C|e^{j\theta}}}\\ {{\mathrm{~and~}}}\\ {{\mathrm{~\,~}}}\\ {{a=r+j\omega_{0}.}}\\ {{\mathrm{~Then~}}}\\ {{\mathrm{~}}}\\ {{C e^{a t}=|C|e^{j\theta}e^{(r+j\omega_{0})t}=|C|e^{r t}e^{j(\omega_{0}t+\theta)}.}}\\ {{\mathrm{~Using~Euler's~relation,~we~can~expand~this~further~as~}}}\\ {{C e^{a t}=|C|e^{r t}\cos(\omega_{0}t+\theta)+j|C|e^{r t}\sin(\omega_{0}t+\theta).}}\end{array}$$



## Application
complex exponential signals are also used to describe the characteristics of many physical processes-in particular, physical systems in which energy is conserved. For example, as shown in Problem 2.61, the natural response of an LC circuit is sinusoidal, as is the simple harmonic motion of a mechanical system consisting of a mass connected by a spring to a stationary support. The acoustic pressure variations corresponding to a single musical tone are also sinusoidal.

By using Euler's relation the complex exponential in eq. (1.21) can be written in terms of sinusoidal signals with the same fundamental period$$e^{j\omega_{0}t}\,=\,\cos\omega_{0}t\,+\,j\sin\omega_{0}t.$$
Similarly, the sinusoidal signal of eq. (1.25) can be written in terms of periodic complex exponentials, again with the same fundamental period:
$${\cal A}\cos(\omega_{0}t+\phi)\,=\,{\frac{\cal A}{2}}e^{j\phi}e^{j\omega_{0}t}\,+\,{\frac{\cal A}{2}}e^{-\,j\phi}e^{-\,j\omega_{0}t}.$$
periodic complex exponential is inversely proportional to its fundamental frequency.

Explore 1.3.2

### Discrete
$$\begin{array}{c}{{{\text{As~in~continuous~time,~an~important~signal~in~discrete~time~is~the~}}c o m p l e x~e x p o n e n t i a l}}\\ {{s i gn a l~\mathrm{or~}s e q u e n c e,\mathrm{~defined~by}}}\\ {{\qquad x[n]\,=\,C\alpha^{n},}}\end{array}\,\,\,\,\,\,\,\,\,\,\,\,\,\,(1.44)$$
$${\mathrm{~where~}}C{\mathrm{~and~}}\alpha{\mathrm{~are,~in~general,~complex~numbers.~This~could~alternatively~be~expressed~in~the~form}}\,$$
$$x[n]\,=\,C e^{\beta n},$$
$Where$
$$\alpha\,=\,e^{\beta}.$$

If $C$ and $\alpha$ are real we can have one of several types of behavior, as illustrated in. if $|\alpha>1|$ the magnitude of the signal grows exponentially with $n$, while if $|\alpha|<1$ we have a decaying exponential
#### Sinusoidal Signals

Incomplete complete later


# References


###### Information
- date: 2024.08.20
- time: 02:49