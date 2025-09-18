---
Title: Biological Neuron
Status: true
marker:
  - "[[Biology]]"
tags:
  - BTech
Date: 2025.08.26
Time: 14:40
---
> [!Prerequisites to understand a neuron mathematically]
> Basic Linear Algebra
# Biological Neuron
From the perspective of [[Perceptron]]
- Mc Culloch Describes the neuron as such:
	- Its a simple logic gate
		- Multiple Signals appear at the dendrites ( Left ) 
		- The Cell takes all the inputs and adds them up. 
		- If the sum crosses a certain threshold it lights up with either of these.
			- Signal
			- No signal
![[IMG-20250918102721730.png|center]]
## The formal definition of an artificial neuron
The above logic can be put in the terms of a mathematical Equations.
	Let $\sigma(z)$ be a function where $z$ is the net input as we said above.
	$z=w_1x_1+w_2x_2+\dots+w_{m}x_{m}$
We can represent the weights $w$ and input $x$ as a vector in the following way

$$
w = \begin{bmatrix}
w_{1} \\
\vdots \\
w_{m}
\end{bmatrix}, \qquad
x = \begin{bmatrix}
x_{1} \\
\vdots \\
x_{m}
\end{bmatrix}
$$
The output values of the function $\delta(z)$ is very similar to the [[Signals and Systems Unit Impulse and Unit Step Functions#Continuous Unit Impulse & Step|Unit Step Function]]

We will now define the perceptron properly. 
Let $\theta$ be the threshold at which the perceptron is programmed to fire.

then the function can be defined as
$$
\sigma(z)=
\begin{cases} 
1,&z\geq \theta, \\
0,&otherwise
\end{cases}
$$


# References


###### Information
- date: 2025.08.26
- time: 14:40