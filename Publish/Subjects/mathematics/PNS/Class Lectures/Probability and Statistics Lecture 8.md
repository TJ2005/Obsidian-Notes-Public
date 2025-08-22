---
Title: Probability & Statistics Lab 6
Status: 
marker: 
tags: 
Date: 2025.01.22
Time: 14:12
---
> [!Continued From]
>  [[Probability and Statistics Lecture 7]]



![[Cumulative Distribution Function]]
# Questions based on Cumulative Distributions
## Question 1

## Example
Suppose $X$ is a discrete random variable with the following probability distribution:

| $X$      | 1   | 2   | 3   |
|----------|------|------|------|
| $P(X=x)$ | 1/4  | 1/2  | 1/4  |

### Problem
Obtain the cumulative distribution function (CDF) of $X$.

### Solution
The distribution function of $X$ is given by:
$$F(x) = P(X \leq x) = \sum_{x_i \leq x} P(x_i) \text{ if } X \text{ is discrete.}$$

Therefore:
$$
F(x) =
\begin{cases} 
0, & x < 1 \\
\frac{1}{4}, & 1 \leq x < 2 \\
\frac{3}{4}, & 2 \leq x < 3 \\
1, & x \geq 3
\end{cases}
$$

## Question 2 
## Example
Suppose $X$ is a continuous random variable with the probability density function (p.d.f.):
$$f(x) = \frac{1}{2}, \quad 0 \leq x \leq 2.$$

### Problem
Obtain the cumulative distribution function (CDF) of $X$.

### Solution
The cumulative distribution function of $X$ is given by:
$$F(x) = P(X \leq x) = \int_{-\infty}^x f(t) \, dt \text{ if } X \text{ is continuous.}$$

For $f(x) = \frac{1}{2}, \, 0 \leq x \leq 2$:
$$
F(x) = \int_0^x \frac{1}{2} \, dt = \frac{1}{2} \Big|_0^x = \frac{1}{2}x
$$

### Final CDF:
$$p
F(x) =
\begin{cases} 
0, & x < 0 \\
\frac{1}{2}x, & 0 \leq x \leq 2 \\
1, & x \geq 2
\end{cases}
$$

## Question 3
## References

> [!Continued to]
>  [[Probability and Statistics Lecture 9]]

