---
Title: Probability & Statistics Lecture 9
Status: 
marker:
  - "[[mathematics]]"
  - "[[Probability and Statistics (PNS)]]"
tags: 
Date: 2025.01.24
Time: 11:08
---
> [!Continued From]
>  [[Probability and Statistics Lecture 8]]


![[Expectation of a Random Variable]]
---
# Questions
These questions are based on the expectation of a random variable and PMF.

---
## Example 1
Find $PMF$ of $Y=X^2+1$ and $E(X)$
### Solution
**Given Data:**

| X  | -1  | 0  | 1  |
|----|-----|----|----|
| P(X=x) | $\frac{1}{2}$ | $\frac{1}{4}$ | $\frac{1}{4}$ |

The function given:

$$Y = X^2 + 1$$
**Values of Y:**
- When $X = -1$, $Y = (-1)^2 + 1 = 2$
- When $X = 0$, $Y = (0)^2 + 1 = 1$
- When $X = 1$, $Y = (1)^2 + 1 = 2$

**Probability Calculation:**
$P(Y = 1) = P(X = 0) = \frac{1}{4}$
$P(Y = 2) = P(X = -1) + P(X = 1) = \frac{1}{2} + \frac{1}{4} = \frac{3}{4}$
**Summary Table:**

| Y      | 1             | 2             |
| ------ | ------------- | ------------- |
| P(Y=y) | $\frac{1}{4}$ | $\frac{3}{4}$ |
Solving for expectation
$$
E(x)=\sum x p(x)
$$
$$
=-1\times 1/2 + 0 \times 1/4 ~+1\times1/4
$$
$$
= 3/4
$$
$$
E(X^2)=\sum x^2 \times P(x)
$$
$$
E(X)=3/4
$$


---
## Question 2
### Given Probability Density Function (PDF):

$$
f(x) =
\begin{cases} 
\frac{1}{4} e^{-x/4}, & x > 0 \\
0, & \text{otherwise}
\end{cases}
$$

#### Problem Statement:
Find the mean and variance of $X$.

#### Solution:

The expected value (mean) of $X$ is calculated as:

$$
E(X) = \int_{0}^{\infty} x f(x) \, dx
$$

Substituting the given PDF:

$$
E(X) = \int_{0}^{\infty} x \cdot \frac{1}{4} e^{-x/4} \, dx
$$
Factor out the constant $\frac{1}{4}$:

$$ E(X) = \frac{1}{4} \int_{0}^{\infty} x e^{-x/4} \, dx $$

Use integration by parts with $u = x$ and $dv = e^{-x/4} \, dx$:

$$ du = dx $$
$$ v = -4 e^{-x/4} $$

Apply the integration by parts formula:

$$ \int u \, dv = uv - \int v \, du $$

$$ E(X) = \frac{1}{4} \left( \left. -4x e^{-x/4} \right|_{0}^{\infty} + \int_{0}^{\infty} 4 e^{-x/4} \, dx \right) $$

Evaluate the boundary term:

$$ \left. -4x e^{-x/4} \right|_{0}^{\infty} = 0 $$

Simplify the remaining integral:

$$ E(X) = \frac{1}{4} \int_{0}^{\infty} 4 e^{-x/4} \, dx $$

$$ E(X) = \int_{0}^{\infty} e^{-x/4} \, dx $$

Evaluate the integral:

$$ \int_{0}^{\infty} e^{-x/4} \, dx = 4 $$

Final calculation:

$$ E(X) = 4 $$

Thus, the expected value $E(X)$ is $4$.

#### Steps to Solve:

1. Use integration by parts to solve the integral for $E(X)$.
2. Compute the variance:

$$
\text{Var}(X) = E(X^2) - [E(X)]^2
$$
## Question 3


Solve q10![[IMG-20250730000529169.png]]
# References


###### Information
- date: 2025.01.24
- time: 11:08

> [!Continued to]
>  [[Probability and Statistics Lecture 10]]

