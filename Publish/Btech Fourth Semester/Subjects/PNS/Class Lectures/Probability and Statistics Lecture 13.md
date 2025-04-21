---
Title: Probability and Statistics Lecture 13
Status: false
marker:
  - "[[Probability and Statistics (PNS)]]"
tags:
  - "#BTech"
Date: 2025.02.11
Time: 15:11
---
> [!Continued From]
> [[Probability and Statistics Lecture 12]]
> 
> **Prerequisites**
> - [[Binomial Distribution]]

Purely solved questions this class
# Questions

## Question 1
There are $5$ Defective items and $20$ good Items. Find the probability Distribution of the defective items if 4 items are drawn from the lot.
### Answer 1
Number of items = $25$

## Question 0 
Two Unbiased Die rolled 3 times find prob that sum 9 is obtained once and twice

## Question 3
Suppose theres 2000 computer chips in a batch and there is a 2% prob that any one chip is faulty. Find the probability that 5 of them are faulty


## Question 4
Precision Bombing attack there is a 50% chance that any 1 bomb will strike the target. two direct hits are required to destroy the target completely how many bomb must be dropped at least 99% chance of destroying the bomb.w

## Question 5
The probability that an archer strikes a target is 1/3 
If he fires five times whats the probability of hitting 2 times.
This is a **binomial probability problem**, where we use the **binomial distribution formula**:

$$
P(X = k) = \binom{n}{k} p^k (1 - p)^{n-k}
$$

where:
- $n = 5$ (number of trials)
- $k = 2$ (number of successes)
- $p = \frac{1}{3}$ (probability of hitting the target)
- $1 - p = \frac{2}{3}$ (probability of missing)

### Step 1: Compute the Binomial Coefficient

$$
\binom{5}{2} = \frac{5!}{2!(5-2)!} = \frac{5!}{2!3!} = \frac{5 \times 4}{2 \times 1} = 10.
$$

### Step 2: Compute the Probability Terms

$p^k = \left(\frac{1}{3}\right)^2 = \frac{1}{9}$

$(1 - p)^{n-k} = \left(\frac{2}{3}\right)^{3} = \frac{8}{27}$

### Step 3: Compute the Final Probability

$$
P(X = 2) = 10 \times \frac{1}{9} \times \frac{8}{27}
$$

$$
= 10 \times \frac{8}{243}
$$

$$
= \frac{80}{243}
$$

Approximating:

$\frac{80}{243} \approx 0.3296$

### Final Answer:

$$
P(X = 2) \approx 0.33 \text{ (or } \frac{80}{243} \text{ exactly)}
$$

# References

> [!Continued to]
> [[Probability and Statistics Lecture 14]]



###### Information
- date: 2025.02.11
- time: 15:11