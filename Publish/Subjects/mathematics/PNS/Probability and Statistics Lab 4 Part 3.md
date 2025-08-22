---
Title: "Probability and Statistics Lab 4 Part 2"
Status: 
marker: 
tags: 
Date: "2025.03.13"
Time: "16:52"
---
> [!Info]
> **Objectives**
> - Understand and apply Binomial and Poisson distributions using R.
>
> **Prerequisites**
> - [[Binomial and Poisson's distribution using R Studio]]
> - [[Probability and Statistics Lab 4 Part 1]]
> - [[Probability and Statistics Lecture 13]]
> - [[IMG-20250730000528784.pdf]]

# Solutions to Probability Problems Using R

## Problem 1: Binomial Distribution

Given:
- Probability of graduating, $p = 0.5$
- Number of students, $n = 10$

We need to find the probability of:
1. None graduating.
2. One graduating.
3. At least one graduating.

```r
# Parameters
n <- 10
p <- 0.5

# i. Probability that none will graduate
prob_none <- dbinom(0, size = n, prob = p)

# ii. Probability that one will graduate
prob_one <- dbinom(1, size = n, prob = p)

# iii. Probability that at least one will graduate
prob_at_least_one <- 1 - prob_none

# Print results
cat("Probability that none will graduate:", prob_none, "\n")
cat("Probability that one will graduate:", prob_one, "\n")
cat("Probability that at least one will graduate:", prob_at_least_one, "\n")
```

## Problem 2: Binomial Distribution with Given Mean and Variance

Given:
- Mean ($\mu$) = 5
- Variance ($\sigma^2$) = $\frac{10}{3}$

We need to find the binomial distribution parameters $n$ and $p$.

Using the formulas:
- $\mu = np$
- $\sigma^2 = np(1-p)$

```r
# Given values
mean_value <- 5
variance_value <- 10/3

# Solve for n and p
p <- 1 - (variance_value / mean_value)
n <- mean_value / p

# Print results
cat("n =", n, "\n")
cat("p =", p, "\n")

# Plot probability distribution and cumulative distribution
x <- 0:n
probabilities <- dbinom(x, size = n, prob = p)
cumulative_probabilities <- pbinom(x, size = n, prob = p)

# Plot probability distribution
barplot(probabilities, names.arg = x, main = "Probability Distribution", xlab = "X", ylab = "P(X)")

# Plot cumulative distribution
plot(x, cumulative_probabilities, type = "s", main = "Cumulative Distribution", xlab = "X", ylab = "F(X)", ylim = c(0, 1))
points(x, cumulative_probabilities, pch = 19)
```

## Problem 3: Poisson Distribution

Given:
- Mean ($\lambda$) = 7.6

We need to find the probability of:
1. Less than three accidents.
2. Exactly three accidents.

```r
# Parameters
lambda <- 7.6

# i. Probability of less than three accidents
prob_less_than_three <- ppois(2, lambda = lambda)

# ii. Probability of exactly three accidents
prob_exactly_three <- dpois(3, lambda = lambda)

# Print results
cat("Probability of less than three accidents:", prob_less_than_three, "\n")
cat("Probability of exactly three accidents:", prob_exactly_three, "\n")
```

## Problem 4: Random Values from Binomial Distribution

Generate 8 random values from a sample of 150 with a probability of 0.4.

```r
# Parameters
sample_size <- 150
probability <- 0.4
num_values <- 8

# Generate random values
random_values <- rbinom(num_values, size = sample_size, prob = probability)

# Print results
cat("Random values:", random_values, "\n")
```

## Problem 5: Binomial Probability for Coin Tosses

Given:
- Number of tosses = 51
- Probability of heads = 0.5

We need to find:
1. The number of heads that will have a probability of 0.25.
2. The probability of getting 26 or fewer heads.

```r
# Parameters
num_tosses <- 51
prob_heads <- 0.5

# i. Number of heads with probability of 0.25
# We need to find k such that P(X = k) is approximately 0.25
probabilities <- dbinom(0:num_tosses, size = num_tosses, prob = prob_heads)
heads_prob_025 <- which(probabilities >= 0.25)

# ii. Probability of getting 26 or fewer heads
prob_26_or_less <- pbinom(26, size = num_tosses, prob = prob_heads)

# Print results
cat("Number of heads with probability of 0.25:", heads_prob_025, "\n")
cat("Probability of getting 26 or fewer heads:", prob_26_or_less, "\n")
```
