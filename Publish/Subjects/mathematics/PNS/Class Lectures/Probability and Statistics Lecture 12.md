---
Title: Probability and Statistics Lecture 12
Status: 
marker: 
tags: 
Date: 2025.02.05
Time: 14:06
---
> 	[!Continued From]
> [[Probability and Statistics Lecture 11]]

> [!info]
> **Moment Generating Function (MGF) Calculation**
> **Prerequisites**
> [[Moment Generating Functions]]

# Questions

### Question1
Find Moment Generating functiona and find first four moments.
### Moment Generating Function (MGF) Calculation

The moment generating function (MGF) is given by:

$$
M_X(t) = E(e^{tX})
$$

Given the probability density function (PDF):

$$
f(x) =
\begin{cases}
2e^{-2x}, & x \geq 0 \\
0, & \text{otherwise}
\end{cases}
$$

We compute \( M_X(t) \) as:

$$
M_X(t) = \int_{0}^{\infty} e^{tx} f(x) \,dx
$$

Substituting \( f(x) \):

$$
M_X(t) = \int_{0}^{\infty} e^{tx} \cdot 2e^{-2x} \,dx
$$

$$
= 2 \int_{0}^{\infty} e^{(t-2)x} \,dx
$$

For convergence, we require \( t < 2 \). Evaluating the integral:

$$
2 \int_{0}^{\infty} e^{(t-2)x} \,dx = 2 \left[ \frac{e^{(t-2)x}}{t-2} \right]_{0}^{\infty}
$$

$$
= 2 \left[ \frac{e^{(t-2) \cdot \infty} - 1}{t-2} \right]
$$

Since \( e^{(t-2) \cdot \infty} \to 0 \) for \( t < 2 \):

$$
M_X(t) = \frac{2}{2-t} = \frac{2}{1 - t}
$$

### Finding the Moments

The moments are given by:

$$
\mu_n = E(X^n) = M_X^{(n)}(0)
$$

#### First Moment (Mean \( $E(X)$ \))

Taking the first derivative:

$$
M'_X(t) = \frac{d}{dt} \left( \frac{2}{1-t} \right)
$$

Using the derivative formula:

$$
\frac{d}{dt} \left( \frac{1}{1-t} \right) = \frac{1}{(1-t)^2}
$$

We get:

$$
M'_X(t) = 2 \cdot \frac{1}{(1-t)^2} = \frac{2}{(1-t)^2}
$$

Evaluating at \( t = 0 \):

$$
E(X) = M'_X(0) = \frac{2}{(1-0)^2} = 2
$$

#### Second Moment \( $E(X^2)$ \)

Taking the second derivative:

$$
M''_X(t) = \frac{d}{dt} \left( \frac{2}{(1-t)^2} \right)
$$

Using the chain rule:

$$
M''_X(t) = 2 \cdot \frac{2}{(1-t)^3} = \frac{4}{(1-t)^3}
$$

Evaluating at \( t = 0 \):

$$
E(X^2) = M''_X(0) = \frac{4}{(1-0)^3} = 4
$$

![[Kurtosis and Skewness]]
# References

#### Random Note snippets
Start with mean which is the first raw moment
Then Variance which is the second central moment
Then the third we use for skewness

Try watching 3Blue1Brown's Convolution video to learn a cool facts about probability distribution.

###### Information
- date: 2025.02.05
- time: 14:06

> [!Continued to]
> [[Probability and Statistics Lecture 13]]

