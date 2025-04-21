---
Title: "Cumulative Distribution Function"
Status: 
marker: 
tags: 
Date: "2025.03.13"
Time: "08:10"
---
# Cumulative Distribution Function

## What's CDF?
The Cumulative Distribution Function (CDF) represents the probability that a random variable $X$ takes a value less than or equal to $x$:
$$F(x) = P(X \leq x)$$

### Benefits of the CDF
1. **Probability Calculation**: Easily compute probabilities for intervals:
   $$P(a \leq X \leq b) = F(b) - F(a)$$
2. **Describes Distribution**: Provides a complete picture of the random variable's behavior.
3. **Quantiles & Percentiles**: Solve $F(x) = p$ to find critical values.
4. **Comparison Tool**: Compare distributions visually and analytically.
5. **Applications**:
   - **Risk Management**: Estimate probabilities of extreme losses.
   - **Reliability Engineering**: Determine failure probabilities.
   - **Finance & Machine Learning**: Model distributions and analyze performance.
## For Discrete
If $X$ is a discrete random variable:
$$F(x) = \sum_{t=-\infty}^{x} P(t)~~~\text{where } P(t) \text{ is the p.m.f.}$$

## For Continuous
If $X$ is a continuous random variable:
$$F(x) = \int_{-\infty}^{x} f(t) \, dt~~~\text{where } f(t) \text{ is the p.d.f.}$$

## Properties of CDF
1. $0 \leq F(x) \leq 1$ for all $x$.
2. $F(x)$ is non-decreasing.
3. $\lim_{x \to -\infty} F(x) = 0$ and $\lim_{x \to \infty} F(x) = 1$.
4. If $F(x)$ is continuous and differentiable, then the p.d.f. is the derivative of the CDF:
   $$f(x) = \frac{dF(x)}{dx}$$

## Map
- [[Probability and Statistics Lecture 8]]
# References
- Lectures at MPSTME

###### Information
- date: 2025.03.13
- time: 08:10