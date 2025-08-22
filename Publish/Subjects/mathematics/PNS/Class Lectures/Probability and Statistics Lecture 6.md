---
Title: Probability & Statistics Lecture 6
Status: 
marker: 
tags: 
Date: 2025.01.17
Time: 13:09
---
Continued from [[Probability and Statistics Lecture 5]]
# Notes on Probability and Random Variables

## Example 1: Probability Density Function (PDF)

A continuous random variable $X$ has the following probability law:
$$
f(x) =
\begin{cases}
kx^2, & 0 \leq x \leq 2 \\
0, & \text{otherwise}
\end{cases}
$$

To determine $k$, we use the property of PDFs:
$$ \int_{-\infty}^\infty f(x) dx = 1 $$
$$ \int_{0}^2 kx^2 dx = 1 $$
$$ k \left[\frac{x^3}{3}\right]_0^2 = 1 $$
$$ k \frac{8}{3} = 1 \implies k = \frac{3}{8} $$

### Probability Calculations:
1. $P(0.1 \leq X \leq 0.4)$:
   $$ \int_{0.1}^{0.4} \frac{3}{8}x^2 dx = \frac{1}{8} \left[ (0.4)^3 - (0.1)^3 \right] = 0.007875 $$

2. $P(0.2 \leq X \leq 3)$:
   $$ \int_{0.2}^{2} \frac{3}{8}x^2 dx = \frac{1}{8} \left[ 2^3 - (0.2)^3 \right] = 0.999 $$

---

## Example 2: Exponential PDF

Suppose a continuous random variable $X$ has the PDF:
$$
f(x) =
\begin{cases}
\frac{k}{4} e^{-x/4}, & x > 0 \\
0, & \text{otherwise}
\end{cases}
$$

To determine $k$, ensure the total probability equals 1:
$$ \int_0^\infty \frac{k}{4} e^{-x/4} dx = 1 $$
Using the integral $\int e^{ax} dx = \frac{e^{ax}}{a}$:
$$ \frac{k}{4} \left[-4e^{-x/4}\right]_0^\infty = 1 $$
$$ k = 1 $$

---

## Example 3: Rainfall Distribution

The daily rainfall $X$ (in inches) is a continuous random variable with PDF:
$$
f(x) =
\begin{cases}
\frac{3}{4}(2x - x^2), & 0 < x < 2 \\
0, & \text{otherwise}
\end{cases}
$$

### Probability Calculations:
1. $P(X \leq 1)$:
   $$ \int_0^1 \frac{3}{4}(2x - x^2) dx = \frac{1}{2} $$

2. $P(X > 1.5)$:
   $$ \int_{1.5}^2 \frac{3}{4}(2x - x^2) dx = 0.15625 $$

3. $P(1 < X \leq 1.5)$:
   $$ \int_1^{1.5} \frac{3}{4}(2x - x^2) dx = 0.34375 $$

---

## Example 4: PMF of $Y$

Let $X$ be a random variable taking values $1, 2, 3, \ldots$ with $P(X = n) = \left(\frac{1}{2}\right)^n$.

Define $Y$:
- $Y = 1$ if $X$ is even.
- $Y = -1$ if $X$ is odd.

The PMF of $Y$:
- $P(Y = 1) = P(X = 2) + P(X = 4) + \ldots$
  $$ = \left(\frac{1}{2}\right)^2 + \left(\frac{1}{2}\right)^4 + \ldots $$
  $$ = \frac{\left(\frac{1}{2}\right)^2}{1 - \left(\frac{1}{2}\right)^2} = \frac{1}{3} $$

- $P(Y = -1) = 1 - P(Y = 1) = \frac{2}{3}$

---

## Example 5: Symmetric PDF

Given PDF:
$$
f(x) =
\begin{cases}
kx(1 - x), & 0 < x < 1 \\
0, & \text{otherwise}
\end{cases}
$$

1. Find $k$:
   $$ \int_0^1 kx(1-x) dx = 1 $$
   $$ k \left[\frac{x^2}{2} - \frac{x^3}{3}\right]_0^1 = 1 \implies k = 6 $$

2. Find $b$ such that $P(X \leq b) = P(X > b)$:
   $$ \int_0^b 6x(1-x) dx = \int_b^1 6x(1-x) dx $$
   Solving the cubic equation yields $b = \frac{1}{2}$.

## References
- Continued to [[Probability and Statistics Lecture 7]]