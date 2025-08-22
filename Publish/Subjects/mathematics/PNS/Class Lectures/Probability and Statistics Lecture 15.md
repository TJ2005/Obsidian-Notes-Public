---
Title: Probability and Statistics Lecture 15
Status: 
marker: 
tags: 
Date: 2025.02.14
Time: 13:21
---
> 	[!Continued to]
>  [[Probability and Statistics Lab 14]]
>  **Prerequisites:**
>  - [[Normal Distribution]]

We covered __[[Normal Distribution]]__ in this lecture.
# Homework Questions
### Question 1
**Problem Solution:**

- The probability that the man aged 60 will live to 70 is $0.65$. We need to find the probability that out of 10 such men now at the age of 60, at least 7 will reach up to 70.

Let $X$ be the number of men aged 60 who live up to 70. $X$ follows a binomial distribution with parameters $n = 10$ and $p = 0.65$:

$$
X \sim B(n=10, p=0.65)
$$

The probability mass function for a binomial distribution is given by:

$$
P(X = x) = \binom{n}{x} p^x q^{n-x}, \quad \text{where } q = 1 - p
$$

We need to calculate $P(X \geq 7)$, which is the sum of probabilities for $X = 7, 8, 9, 10$:

$$
P(X \geq 7) = P(X = 7) + P(X = 8) + P(X = 9) + P(X = 10)
$$

Calculating each term:

$$
P(X = 7) = \binom{10}{7} (0.65)^7 (0.35)^3 = 0.25221
$$

$$
P(X = 8) = \binom{10}{8} (0.65)^8 (0.35)^2 = 0.17565
$$

$$
P(X = 9) = \binom{10}{9} (0.65)^9 (0.35)^1 = 0.072491
$$

$$
P(X = 10) = \binom{10}{10} (0.65)^{10} (0.35)^0 = 0.013462
$$

Summing these probabilities:

$$
P(X \geq 7) = 0.25221 + 0.17565 + 0.072491 + 0.013462 = 0.513813
$$

Thus, the probability that at least 7 out of 10 men aged 60 will live to 70 is approximately $0.5138$.

### Question 2
To solve this problem, we need to calculate the probability that the car hire firm will either have no cars used or will have to refuse some demand because the demand exceeds the two cars they have available.
Given:
- The number of demands for cars each day follows a Poisson distribution with a mean (\($\lambda$\)) of 1.5.
- The firm has two cars available each day.

We need to find the probability of the days on which either:
1. Neither car is used (\(X = 0\)).
2. Some demand is refused (\(X > 2\)).

The Poisson probability mass function is given by:

$$
P(X = x) = \frac{e^{-\lambda} \lambda^x}{x!}
$$

We need to calculate:
- \(P(X = 0)\)
- \(P(X > 2)\)

\(P(X > 2)\) can be calculated as:

$$
P(X > 2) = 1 - P(X \leq 2)
$$

Where:

$$
P(X \leq 2) = P(X = 0) + P(X = 1) + P(X = 2)
$$

Let's calculate these probabilities.For a car hire firm with two cars and a Poisson-distributed demand with a mean of 1.5, the probabilities are as follows:

- The probability that no cars are used (i.e., \( $P(X = 0)$ \)) is approximately \(0.223\).
- The probability that some demand is refused (i.e., \( $P(X > 2)$ \)) is approximately \(0.191\).
- The combined probability of either no cars being used or some demand being refused is approximately \($0.414$\).

These calculations help determine the likelihood of days when either no cars are utilized or there is insufficient supply to meet the demand.


# References


###### Information
- date: 2025.02.14
- time: 13:21

> [!Continued to]
>  [[Probability and Statistics Lecture 16]]


