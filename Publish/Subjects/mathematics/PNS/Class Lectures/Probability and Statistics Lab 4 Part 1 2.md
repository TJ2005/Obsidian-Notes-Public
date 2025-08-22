---
Title: Probability and Statistics Lab 4 Part 1
Status: true
marker: 
tags: 
Date: 2025.03.12
Time: 13:29
---
> [!Info]
> **Objectives**
> - Understand and apply discrete probability distributions using R.
>
> **Prerequisites**
> - [[Probability distribution in R studio]]
> - [[Cumulative Distribution Function]]
> - [[Probability and Statistics Lecture 8]]
> - Document [[IMG-20250730000529111.pdf]]

# Handwritten Solutions

### Question 1

|X|1|2|3|4|5|6|7|
|---|---|---|---|---|---|---|---|
|P(X)|k|2k|3k|k²|k² + k|2k²|4k²|

We need to:
1. **Find kk** by ensuring the sum of all probabilities is 1.
2. **Compute $P(X<5)P(X < 5) and P(1≤X≤5)P(1 \leq X \leq 5).$
3. **Write an R program** to plot the probability distribution and cumulative distribution.

---
$$
k + 2k + 3k + k^2 + k^2 + k + 2k^2 + 4k^2 = 1
$$

Let's solve this equation step by step:

Combine like terms:

$$
k + 2k + 3k + k + k^2 + k^2 + 2k^2 + 4k^2 = 1
$$

$$
7k + 8k^2 = 1
$$

Rearrange the equation to standard quadratic form:

$$
8k^2 + 7k - 1 = 0
$$

Now, solve the quadratic equation using the quadratic formula \( k = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a} \):

$$
a = 8, \quad b = 7, \quad c = -1
$$

$$
k = \frac{-7 \pm \sqrt{7^2 - 4 \cdot 8 \cdot (-1)}}{2 \cdot 8}
$$

$$
k = \frac{-7 \pm \sqrt{49 + 32}}{16}
$$

$$
k = \frac{-7 \pm \sqrt{81}}{16}
$$

$$
k = \frac{-7 \pm 9}{16}
$$

So the solutions are:

$$
k = \frac{2}{16} = \frac{1}{8} \quad \text{or} \quad k = \frac{-16}{16} = -1
$$

Since probability cannot be negative, we discard \( k = -1 \).

Thus, the valid solution is:

$$
k = \frac{1}{8}
$$

```r
k %3C- 1/8

# Define the PDF of X
x <- c(1, 2, 3, 4, 5, 6, 7)
P_X <- c(k, 2*k, 3*k, k^2, k^2 + k, 2*k^2, 4*k^2)

# Calculate P(X < 5) and P(X <= 5)
P_X_less_than_5 <- sum(P_X[x < 5])
P_X_less_than_equal_5 <- sum(P_X[x <= 5])

# Print the results
cat("P(X < 5) =", P_X_less_than_5, "\n")
cat("P(X <= 5) =", P_X_less_than_equal_5, "\n")

# Plot the probability distribution
barplot(P_X, names.arg=x, main="Probability Distribution of X", xlab="X", ylab="P(X)")

# Plot the cumulative distribution
cumulative_P_X <- cumsum(P_X)
plot(x, cumulative_P_X, type="s", main="Cumulative Distribution of X", xlab="X", ylab="F(X)", ylim=c(0,1))
points(x, cumulative_P_X, pch=19)
```

```bash
 # Print the results
> cat("P(X < 5) =", P_X_less_than_5, "\n")
P(X < 5) = 0.765625 
> cat("P(X <= 5) =", P_X_less_than_equal_5, "\n")
P(X <= 5) = 0.906252

```

![](https://i.imgur.com/lchNxgI.png)


<div style="display: flex; justify-content: center; align-items: center; height: 100%; overflow: hidden;">
    <img src="https://i.imgur.com/eskK1c3.jpeg" style="width: 40vw; transform: rotate(-90deg);" />
</div>

---

## Question 2
```R


k <- 0.05  # chosen so that all probabilities are positive and sum < 1

# Define the probability values with both fixed values and terms using k
p <- c(0.1, k, 0.2, 2*k, 0.3, k, 0.2, 2*k, 0.3, 3*k)

# Normalize the probabilities to ensure they sum to 1 (very important)
p <- p / sum(p)

# Define the corresponding values of the discrete random variable X
x <- 1:10

# Calculate the cumulative distribution using pdiscrete()
# This returns cumulative probabilities F(x)
pl <- pdiscrete(x, probs = p, values = x)

# Plot the cumulative distribution
plot(pl,
     main = "Cumulative Distribution",
     xlab = "X",
     ylab = "Cumulative Probability",
     col = "red",
     pch = 19,
     type = "o")  # type = "o" means lines + points

```
### Output
![](https://i.imgur.com/w7sDzg0.png)


<div style="display: flex; justify-content: center; align-items: center; height: 100%; overflow: hidden;">
    <img src="https://i.imgur.com/sDe653c.jpeg" style="width: 40vw; transform: rotate(-90deg);" />
</div>

## Question 3
```R

# Define values of the discrete random variable
x <- 1:5

# Define corresponding probabilities
p <- c(1/5, 2/5, 2/15, 1/15, 1/5)

# Confirm that probabilities sum to 1
total_prob <- sum(p)
cat("Sum of probabilities:", total_prob, "\n")  # Should be 1

# Compute PMF and CDF using e1071 functions
pmf <- ddiscrete(x, probs = p, values = x)
cdf <- pdiscrete(x, probs = p, values = x)

# Plot the Probability Mass Function (PMF)
plot(pmf, type = "o", col = "coral",
     main = "Probability Distribution",
     xlab = "X", ylab = "P(X)", pch = 19)

# Plot the Cumulative Distribution Function (CDF)
plot(cdf, type = "o", col = "blue",
     main = "Cumulative Distribution",
     xlab = "X", ylab = "Cumulative Probability", pch = 19)

```
### Output
```bash
Sum of probabilities: 1
```

![](https://i.imgur.com/n3bGxBb.png)
![](https://i.imgur.com/oL2bj6H.png)

<div style="display: flex; justify-content: center; align-items: center; height: 100%; overflow: hidden;">
    <img src="https://i.imgur.com/5gjoOC3.jpeg" style="width: 40vw; transform: rotate(-90deg);" />
</div>
### Question 4
```R
# Define values of the discrete random variable
x <- c(-3, -2, -1, 0, 1, 2)

# Define corresponding probabilities
p_x <- c(0.05, 0.1, 0.2, 0.3, 0.2, 0.15)

# Compute the expected value (mean) of X
mean_x <- sum(x * p_x)
cat("Mean of X:", mean_x, "\n")

# Compute the second moment E[X^2]
Ex2 <- sum((x^2) * p_x)
cat("E[X^2]:", Ex2, "\n")

# Compute variance of X
variance_x <- Ex2 - (mean_x^2)
cat("Variance of X:", variance_x, "\n")

# Plot the Probability Mass Function (PMF)
plot(x, p_x, col = "blue", type = "o",
     main = "Probability Distribution",
     xlab = "X", ylab = "P(X = x)", pch = 19)

# Compute Cumulative Distribution Function (CDF)
cdf <- cumsum(p_x)

# Plot the CDF
plot(x, cdf, type = "o", col = "red",
     main = "Cumulative Distribution Function",
     xlab = "X", ylab = "F(X)", pch = 19)

```

```bash
Mean of X: -0.05
E[X^2]: 1.85
Variance of X: 1.8475
```
![](https://i.imgur.com/QBYgWqn.png)


## Question 5
<div style="display: flex; justify-content: center; align-items: center; height: 100%; overflow: hidden;">
    <img src="https://i.imgur.com/Y2gSHQE.jpeg" style="width: 40vw; transform: rotate(0deg);" />
</div>


# References

