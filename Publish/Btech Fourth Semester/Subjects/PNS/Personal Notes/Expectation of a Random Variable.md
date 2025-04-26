---
Title: "Expectation of a Random Variable"
Status: 
marker: 
tags: 
Date: "2025.03.13"
Time: "08:15"
---
# Expectation of Random Variable $X$.

Expectation, also called **expected value**, is a fundamental concept in probability and statistics. It provides the **average or mean value** of a random variable if the experiment were repeated infinitely many time.
### For Discrete Random Variable
$$
\text{X is a discrete r.v, },~~E(X)=\sum x(PX=x)
$$

### For Continuous Random Variable
$$
\text{X is a continuous r.v, },~~E(X)=\int_{-\infty}^{\infty} x(PX=x)
$$
### Properties
- $E(aX+b)=aE(X)+b$    Where   $a,b$    are constant.
- $E(a)=a$
- Let $Y=g(x)$ 
	- $E(Y)=E(g(x))=\sum g(x)\times P(x)$ 
				   $=\int g(x)\times P(x)$
		- $E(X^2)=\sum x^2\times P(x)$

---
# Variance of Random Variable $X$.

### Formula for Variance
$$
V(X) = E(X^2) - [E(X)]^2
$$

### When $X$ is Discrete
$$
V(X) = \sum [X^2 \times P(X)] - [\sum X \times P(X)]^2
$$

### When $X$ is Continuous
$$
V(X) = \int_{-\infty}^{\infty} x^2 f(x) \, dx - \left[\int_{-\infty}^{\infty} x f(x) \, dx \right]^2
$$

### Alternate Formula for Variance
$$
V(X) = E[(X - E(X))^2]
$$

### Properties of Variance
1. $V(a) = 0$ where $a$ is a constant. ^9ca5af
2. $V(aX) = a^2 \cdot V(X)$ where $a$ is a scalar.

---

# Standard Deviation for Random Variable $X$.

[[Variance In RV|Variance]] measures the **spread** or **dispersion** of a random variable's values around its mean. It quantifies how much the values of a dataset or distribution deviate from the expected value (mean).
### Formula for Standard Deviation
The standard deviation ($\sigma_X$) is the square root of the variance:

$$
\sigma_X = \sqrt{V(X)}
$$

### When $X$ is Discrete
$$
\sigma_X = \sqrt{\sum [X^2 \times P(X)] - \left[\sum X \times P(X)\right]^2}
$$

### When $X$ is Continuous
$$
\sigma_X = \sqrt{\int_{-\infty}^{\infty} x^2 f(x) \, dx - \left[\int_{-\infty}^{\infty} x f(x) \, dx \right]^2}
$$

### Alternate Formula for Standard Deviation
$$
\sigma_X = \sqrt{E[(X - E(X))^2]}
$$
---

## Standard $uv$ Rule Application in $E(X^2)$

### Expectation Formula for Continuous Random Variable
The expectation of $X^2$ is given by:
$$
E(X^2) = \int x^2 f(x) \, dx
$$

### Applying the Standard $uv$ Rule
Using integration by parts ($uv$ rule), where $u = x^2$ and $v' = f(x)$:
1. Let $u = x^2$, so $u' = 2x$.
2. Let $v' = f(x)$, so $v = \int f(x) \, dx$.

Applying the integration by parts formula:
$$
\int x^2 f(x) \, dx = x^2 \int f(x) \, dx - \int \left[2x \cdot \int f(x) \, dx \right] dx
$$

### Polynomial Behavior
Since $x^2$ is a polynomial, and differentiation reduces the degree of a polynomial, repeated application of the $uv$ rule will always result in a polynomial that eventually terminates. Therefore, the integration will conclude in a finite number of steps.


# References
- Lectures at MPSTME
- Solve problems at [[Probability and Statistics Lecture 9]]
###### Information
- date: 2025.03.13
- time: 08:15