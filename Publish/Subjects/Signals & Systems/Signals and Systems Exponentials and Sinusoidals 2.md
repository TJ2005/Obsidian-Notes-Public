---
Title: Signals & Systems Exponentials and Sinusoidals
Status: true
marker: 
tags: 
Date: 2024.08.20
Time: 02:49
---
Continued from [[Signals & System Transformation of the independent variable]]

Prerequisites : [[Eulers Formula]]
# Continuous-Time Complex Exponential and Sinusoidal Signals
In this section We introduce several basic continuous-time and discrete-time signals. Not only do these signals occur frequently, but they also serve as basic building blocks from which we can construct many other signals.

The continuous-time complex exponential signal is of the form
$$x(t)\,=\,C e^{a t},$$
where $C$ and $a$ are, in general, complex numbers. Depending upon the values of these parameters, the complex exponential can exhibit several different characteristics.

### Real Exponential Signals
if $C$ and $a$ are **real** *(in which case x(t) is called a real exponential)*, there are basically two types of behavior.

If a is positive, then as t increases x(t) is a growing exponential, a form that is used in describing many different physical processes, including chain reactions in atomic explosions and complex chemical reactions. 

If a is negative, then x(t) is a decaying exponential, a signal that is also used to describe a wide variety of phenomena, including the process of radioactive decay and the responses of RC circuits and damped mechanical systems.
![[IMG-20250212164944797.png]]
## Periodic Complex Exponential and Sinusoidal Signals

### For Continuous
Complex exponentials is obtained by constraining a to be purely imaginary.
$$x(t)\,=\,e^{j\omega_{0}t}.$$
here $\omega_0 = 2\pi*f$, Which is the frequency of the signal ^416752

If this signal was to be periodic referring [[Signals & System Transformation of the independent variable#^50ce01|Periodicity]]
Then it shall follow this rule of [[Signals & System Transformation of the independent variable#Periodic Signals|Periodic Signals]]


$$
e^{j\omega_{0}t}\:=\:e^{j\omega_{0}(t+T)}.
$$

$$
e^{j\omega_{0}t}\,=\,e^{j\omega_{0}t}e^{j\omega_{0}T},
$$
Cancelling out the common terms.
$$
1=e^{j\omega_0T}
$$
it follows that for periodicity, we must have
$$e^{j\omega_{0}T}\,=\,1.$$

thus by simply putting the angular frequency $\omega_0=0$ we can say that $x(t)=1$ which makes this function periodic for any T.

But if $w_0\neq0$ then the fundamental period $T_0$ of $x(t)$ will be given as such
$\because~\omega_0=2\pi f$ and $j$ and $T$ are constant
$\therefore \text{we can say that}$  
$$T_{0}\,=\,\frac{2\pi}{|\omega_{0}|}.$$

This is because 
$\omega_0T = 2 \pi N$ and then we can shift eqn to make the above one.

---
## Sinusodials

A signal closely related to the periodic complex exponential is the sinusoidal signal. ^906ac1

$$x(t)\,=\,A\cos(\omega_{0}t+\phi),$$
This is because of Euler's formulae. ( no need for deep understanding but cool if you can study )

#### Writing One eqn in other forms.
We can write the equation in the [[Signals and Systems Exponentials and Sinusoidals#^416752|Exponential part]] as 
$$
e^{j\omega_{0}t}\,=\,\cos\omega_{0}t\,+\,j\sin\omega_{0}t.
$$
similarly we can write the [[Signals and Systems Exponentials and Sinusoidals#^906ac1|Sinusodial Part]] as an Exponent
$$
{\cal A}\cos(\omega_{0}t+\phi)\,=\,{\frac{\cal A}{2}}e^{j\phi}e^{j\omega_{0}t}\,+\,{\frac{\cal A}{2}}e^{-\,j\phi}e^{-\,j\omega_{0}t}.
$$

Thus we can say that 
$${\cal A}\cos(\omega_{0}t+\phi)\,=\,{\cal A}\Re e\{e^{j(\omega_{0}t+\phi)}\},$$
$${\cal A}\sin(\omega_{0}t+\phi)\,=\,{\cal A}\mathcal{I}m\{e^{j(\omega_{0}t+\phi)}\}.$$
where $\Re e$ means the real part and $\Im m$ as the imaginary part


---
## Fundamental Time Period $T_0$
Just keep in mind that $\omega_0$ is Inversely proportional to $T_0$ this is simply because $\omega_0 = 2 \pi f$   and   $T = 1/f$ . So Changing one affects the otthers

---
## Energy Signals & Periodic signals
Consider the periodic ex- ponential signal of eq. (1.21), and suppose that we calculate the total energy and average power in this signal over one period:

$$E_{\mathrm{period}}\,=\,\int_{0}^{T_{0}}|e^{j\omega_{0}t}|^{2}\,d t$$
$$=\;\int_{0}^{T_{0}}\,1\cdot d t\,=\,T_{0},$$

Thus they are important examples of signals with infinite total energy but finite average power.

---

### Applications
complex exponential signals are also used to describe the characteristics of many physical processes-in particular, physical systems in which energy is conserved. For example, as shown in Problem 2.61, the natural response of an LC circuit is sinusoidal, as is the simple harmonic motion of a mechanical system consisting of a mass connected by a spring to a stationary support. The acoustic pressure variations corresponding to a single musical tone are also sinusoidal.

Periodic complex exponentials will play a central role in much of our treatment of signals and systems, in part because they serve as extremely useful building blocks formany other signals. We will often find it useful to consider sets of harmonically related
complex exponentials—that is, sets of periodic exponentials, all of which are periodic with a common period $T_{o}$. Specifically, a necessary condition for a complex exponential $e^{j\omega T_{0}  }$ to be periodic with period To is that


# Examples
## Example 1.5
Sometimes we write signal eqns as a sum of two complex exponentials as the product of a single complex exponent and a single sinusoid. For example, suppose we wish to plot the magnitude of the signal
$$
x(t)=e^{j2t}+e^{j 3t}
$$
We can use the law of indices to perform this operation

$$
x(t)=e^{2.5}(e^{-0.5jt}+e^{0.5jt})
$$
and with Euler's formulae
$$x(t)\,=\,2e^{j2.5t}\cos(0.5t).$$
To calculate the magnitude we can do for any $z=r.e^{j\theta}$ the magnitude of $|Z|$ is $r$ ( Since Z is a rotating complex vector in complex plane and the coefficient multiplied to it is the magnitude. Imagine graphically. )
$$
|x(t)| = 2|\cos(0.5t)|
$$
![[IMG-20250212164945188.png|center|300]]

---

# General Complex Exponential Signals
The most general case of a complex exponential can be expressed and interpreted in terms of the two cases we have examined so far: the real exponential and the periodic complex exponential. Specifically, consider a complex exponential $Ce^{at}$ where $C$ is expressed in polar form and a in rectangular form. That is,

$$
C=|C|e^{j \theta}
$$
and 
$$
a=r+j\omega_{0} 
$$
Then
$$
C.e^{at}=|C|e^{j\theta}.e^{(r+j \omega _{0})t}
$$
$$
C.e^{at}=|C|e^{j \theta}.e^{rt+j\omega_{0}t}
$$
$$
Ce^{at}=|C| e^{rt}.e^{j(\omega_{0}t+\theta)}
$$
Thus by Euler's Relation we can boil this down to
$$
C.e^{at}=
|C|e^{rt}\cos(w_{o}t+\theta)+j|C|e^{rt}\sin(w_{o}t+\theta)
$$
Thus we can say that for $r=0$ the real and imaginary part of this eqn is sinusoidal. 
For $r>0$ we can say that the sinusoidal is exponentially growing
and For $R<0$ we can say that the sinusoidal is exponentially decaying

The graph depicts these properties.
![[IMG-20250212164945414.png|center|300]]
$$\begin{array}{l}{{F i g u r e\,\,1.23\quad(a)\,\,G r o w i n g\,\,s i n u s o i d a l}}\\ {{\mathrm{\boldmath~\sigma~}|\,\chi(t)\,=\,C e^{r t}\cos{(\omega_{0}t+\,\theta)},}}\\ {{r>0;\,(\mathrm{b})\,\,\mathrm{deca y i n g\,\,s i n u s o i d}\,\,\chi(t)\,=}}\\ {{C e^{r t}\,\cos{(\omega_{0}t+\,\theta)},\,r<0.}}\end{array}$$


---
# Discrete
$$\begin{array}{c}{{{\text{As~in~continuous~time,~an~important~signal~in~discrete~time~is~the~}}c o m p l e x~e x p o n e n t i a l}}\\ {{s i gn a l~\mathrm{or~}s e q u e n c e,\mathrm{~defined~by}}}\\ {{\qquad x[n]\,=\,C\alpha^{n},}}\end{array}\,\,\,\,\,\,\,\,\,\,\,\,\,\,(1.44)$$
$${\mathrm{~where~}}C{\mathrm{~and~}}\alpha{\mathrm{~are,~in~general,~complex~numbers.~This~could~alternatively~be~expressed~in~the~form}}\,$$
$$x[n]\,=\,C e^{\beta n},$$
$Where$
$$\alpha\,=\,e^{\beta}.$$

If $C$ and $\alpha$ are real we can have one of several types of behaviour, as illustrated in. if $|\alpha>1|$ the magnitude of the signal grows exponentially with $n$, while if $|\alpha|<1$ we have a decaying exponential

$${\mathrm{~Note~that~the~fundamental~period~can~also~be~written~as~}}$$


---
### Complex Exponential Equation 
For a discrete based equation the function can be given as.
$$x[n]\,=\,e^{j\omega_{0}n}.$$
Its graphical Representation is as follows


![[IMG-20250212164945567.png|center|300]]
calculate $${\frac{2\pi}{N}}\;=\;{\frac{\omega_{0}}{m}}.$$
we can calculate the value of fundamental time period
$${\cal N}\,=\,m\,\bigg(\frac{2\pi}{\omega_{0}}\bigg).$$

## Complex Sinusoidal 
This eqn is closely related to the $x[n]=e^{j\omega _0n}$ eqn
$$e^{j\omega_{0}n}\,=\,\cos\omega_{0}n+\,j\sin\omega_{0}n$$
and thus we can similar write the eqn as we did with [[Signals and Systems Exponentials and Sinusoidals#Continuous-Time Complex Exponential and Sinusoidal Signals|sinusodial continous]] and then get this 
$${\cal A}\cos(\omega_{0}n+\phi)\,=\,{\frac{\cal A}{2}}e^{j\phi}e^{j\omega_{0}n}\,+\,{\frac{\cal A}{2}}e^{-\,j\phi}e^{-\,j\omega_{0}n}.$$
![[IMG-20250212164945708.png|center|300]]

---

# Periodicity of Complex Exponentials
Consider the following literal $e^{j(\omega _{o}+2\pi)n}$. If we evaluate this expression we get.
$$e^{j(\omega_{0}+2\pi)n}\,=\,e^{j2\pi n}e^{j\omega_{0}n}\,=\,e^{j\omega_{0}n}.$$
Thus we can conclude that every $\omega_{()}\pm2\pi,\,\omega_{()}\pm4\boldsymbol{\pi}\dots$


###### Information
- date: 2024.08.20
- time: 02:49
- Continued to [[Signals and Systems Unit Impulse and Unit Step Functions]]