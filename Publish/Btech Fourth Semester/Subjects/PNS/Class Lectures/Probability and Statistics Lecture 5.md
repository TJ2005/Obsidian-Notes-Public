---
Title: Probability & Statistics Lecture 5
Status: 
marker: 
tags: 
Date: 2025.01.15
Time: 14:05
---
> [!Continued From]
> [[Probability and Statistics Lecture 4]]
# Probability & Statistics Lecture 5

## Question 1

Rahul travels by:

- Bus with probability $P(B)=\frac{2}{7}$
- Car with probability $P(C)=\frac{4}{7}$
- Motorcycle with probability $P(M)=\frac{1}{7}$

Given the probabilities of being late:

- $P(L|B)=\frac{3}{8}$
- $P(L|C)=\frac{1}{8}$
- $P(L|M)=\frac{4}{8}$

Find the probability of Rahul coming late $P(L)$.

### Answer 1

The probability of Rahul coming late is given by:

$$P(L) = P(B) \cdot P(L|B) + P(C) \cdot P(L|C) + P(M) \cdot P(L|M)$$

Substituting the values:

$$P(L) = \left(\frac{2}{7} \cdot \frac{3}{8}\right) + \left(\frac{4}{7} \cdot \frac{1}{8}\right) + \left(\frac{1}{7} \cdot \frac{4}{8}\right)$$

Simplify:

$$P(L) = \frac{6}{56} + \frac{4}{56} + \frac{4}{56}$$

$$P(L) = \frac{14}{56} = \frac{1}{4}$$

Thus, the probability of Rahul coming late is $\frac{1}{4}$.

---
## Question 2
## Question 2

Siya speaks either the truth or lies:

- Probability of truth: $P(T) = \frac{3}{8}$
- Probability of lying: $P(L) = \frac{5}{8}$

### Part 1: Probability of her saying "6"

Let $P(6|T)$ be the probability of her saying "6" if she's truthful (which is $\frac{1}{6}$ for a fair die), and $P(6|L)$ be the probability of her saying "6" if she's lying (assumed as $1$ since she can fabricate it).

The total probability $P(6)$ is:

$$P(6) = P(T) \cdot P(6|T) + P(L) \cdot P(6|L)$$

Substituting the values:

$$P(6) = \left(\frac{3}{8} \cdot \frac{1}{6}\right) + \left(\frac{5}{8} \cdot 1\right)$$

$$P(6) = \frac{3}{48} + \frac{40}{48} = \frac{43}{48}$$

Thus, the probability of Siya saying "6" is $\frac{43}{48}$.

### Part 2: Probability of truth given she says "6"

We use Bayes' theorem:

$$P(T|6) = \frac{P(T) \cdot P(6|T)}{P(6)}$$

Substituting the values:

$$P(T|6) = \frac{\frac{3}{8} \cdot \frac{1}{6}}{\frac{43}{48}}$$

$$P(T|6) = \frac{\frac{3}{48}}{\frac{43}{48}} = \frac{3}{43}$$

Thus, the probability of Siya telling the truth while saying "6" is $\frac{3}{43}$.

---

## Question 3

There are always 50% spam mails:

- $P(S) = 0.5$, $P(\neg S) = 0.5$
- Spam filter detects 99% of spam: $P(D|S) = 0.99$
- False positive rate: 5% of non-spam: $P(D|\neg S) = 0.05$

Find the probability of a non-spam mail being falsely detected as spam ($P(\neg S|D)$).

We use Bayes' theorem:

$$P(\neg S|D) = \frac{P(\neg S) \cdot P(D|\neg S)}{P(D)}$$

Where $P(D)$ is the total probability of detection:

$$P(D) = P(S) \cdot P(D|S) + P(\neg S) \cdot P(D|\neg S)$$

Substitute the values:

$$P(D) = (0.5 \cdot 0.99) + (0.5 \cdot 0.05)$$
$$P(D) = 0.495 + 0.025 = 0.52$$

Now, calculate $P(\neg S|D)$:

$$P(\neg S|D) = \frac{0.5 \cdot 0.05}{0.52}$$
$$P(\neg S|D) = \frac{0.025}{0.52} \approx 0.0481$$

Thus, the probability of a non-spam mail being falsely detected as spam is approximately $0.0481$ or $4.81\%$.

### References

> [!Continued to]
> [[Probability and Statistics Lecture 6]]


N/A

###### Information

- Date: 2025.01.15
- Time: 14:05