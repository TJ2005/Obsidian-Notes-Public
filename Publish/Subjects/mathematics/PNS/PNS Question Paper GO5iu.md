---
Title: "PNS Question Paper GO5iu"
Status: 
marker: 
tags: 
Date: "2025.04.22"
Time: "16:52"
---
# PNS Question Paper GO5iu
# Question 1
## Question a
There are 3 true coins and 1 false coin with head on both sides. A coin is chosen at random and tossed 4 times. If head occurs all the 4 times, compute the probability that the false coin has been chosen and used.

### Formula & Concept used

This problem requires the application of Bayes' theorem, which allows us to find the conditional probability of an event given that another event has occurred.

Bayes' theorem states that:
$$P(A|B) = \frac{P(A) \times P(B|A)}{P(B)}$$

Where:
- $P(A|B)$ is the probability of event A given that event B has occurred
- $P(A)$ is the prior probability of event A
- $P(B|A)$ is the probability of event B given that event A has occurred
- $P(B)$ is the prior probability of event B

For this problem:
- Let A be the event that the false coin is chosen
- Let B be the event that heads occur all 4 times

### Solution

Step 1: Find the probability of choosing each type of coin.
- Probability of choosing the false coin: $P(A) = \frac{1}{4}$
- Probability of choosing a true coin: $P(A^c) = \frac{3}{4}$

Step 2: Find the probability of getting 4 heads given the type of coin chosen.
- If the false coin is chosen (which has heads on both sides), the probability of getting 4 heads is:
  $P(B|A) = 1 \times 1 \times 1 \times 1 = 1$

- If a true (fair) coin is chosen, the probability of getting 4 heads is:
  $P(B|A^c) = \frac{1}{2} \times \frac{1}{2} \times \frac{1}{2} \times \frac{1}{2} = \frac{1}{16}$

Step 3: Find the total probability of getting 4 heads.
$P(B) = P(A) \times P(B|A) + P(A^c) \times P(B|A^c)$
$P(B) = \frac{1}{4} \times 1 + \frac{3}{4} \times \frac{1}{16}$
$P(B) = \frac{1}{4} + \frac{3}{64}$
$P(B) = \frac{16}{64} + \frac{3}{64} = \frac{19}{64}$

Step 4: Apply Bayes' theorem to find the probability that the false coin was chosen given that 4 heads occurred.
$P(A|B) = \frac{P(A) \times P(B|A)}{P(B)}$
$P(A|B) = \frac{\frac{1}{4} \times 1}{\frac{19}{64}}$
$P(A|B) = \frac{\frac{1}{4}}{\frac{19}{64}} = \frac{1}{4} \times \frac{64}{19} = \frac{16}{19}$

Therefore, the probability that the false coin has been chosen and used, given that heads occurred all 4 times, is $\frac{16}{19}$ or approximately 0.842.

## Question B

A random variable X has the following probability function:

|X|0|1|2|3|4|5|6|7|
|---|---|---|---|---|---|---|---|---|
|P(X)|0|$k$|$2k$|$2k$|$3k$|$k^2$|$2k^2$|$7k^2+k$|

Find $k$ and $P(X < 6)$.

## Formula & Concept used

For a valid probability function, we need to apply two fundamental properties:

1. Each probability value must be non-negative: $P(X = x) \geq 0$ for all $x$
    
2. The sum of all probabilities must equal 1: $\sum P(X = x) = 1$
    

## Solution

Step 1: Find the value of $k$ using the fact that the sum of all probabilities must equal 1.

$\sum_{x=0}^{7} P(X = x) = 1$

$0 + k + 2k + 2k + 3k + k^2 + 2k^2 + (7k^2+k) = 1$

$8k + 10k^2 = 1$

$10k^2 + 8k - 1 = 0$

This is a quadratic equation in the form $ax^2 + bx + c = 0$ with $a = 10$, $b = 8$, and $c = -1$.

Using the quadratic formula:  
$k = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$

$k = \frac{-8 \pm \sqrt{64 + 40}}{20}$

$k = \frac{-8 \pm \sqrt{104}}{20}$

$k = \frac{-8 \pm 10.2}{20}$

This gives us two values:  
$k = \frac{-8 + 10.2}{20} \approx 0.11$  
$k = \frac{-8 - 10.2}{20} \approx -0.91$

Since probabilities must be non-negative, $k$ cannot be negative. Therefore, $k \approx 0.11$.

For more precision, we can express $\sqrt{104}$ as $2\sqrt{26}$:

$k = \frac{-8 + 2\sqrt{26}}{20} = \frac{-4 + \sqrt{26}}{10}$

Step 2: Calculate $P(X < 6)$.

$P(X < 6) = P(X = 0) + P(X = 1) + P(X = 2) + P(X = 3) + P(X = 4) + P(X = 5)$

$P(X < 6) = 0 + k + 2k + 2k + 3k + k^2$

$P(X < 6) = 8k + k^2$

Substituting $k = \frac{-4 + \sqrt{26}}{10}$:

$P(X < 6) = 8 \cdot \frac{-4 + \sqrt{26}}{10} + \left(\frac{-4 + \sqrt{26}}{10}\right)^2$

$P(X < 6) = \frac{8(-4 + \sqrt{26})}{10} + \frac{(-4 + \sqrt{26})^2}{100}$

$P(X < 6) = \frac{-32 + 8\sqrt{26}}{10} + \frac{16 - 8\sqrt{26} + 26}{100}$

$P(X < 6) = \frac{-32 + 8\sqrt{26}}{10} + \frac{42 - 8\sqrt{26}}{100}$

$P(X < 6) = \frac{-320 + 80\sqrt{26}}{100} + \frac{42 - 8\sqrt{26}}{100}$

$P(X < 6) = \frac{-320 + 80\sqrt{26} + 42 - 8\sqrt{26}}{100}$

$P(X < 6) = \frac{-278 + 72\sqrt{26}}{100}$

Therefore, $k = \frac{-4 + \sqrt{26}}{10}$ and $P(X < 6) = \frac{-278 + 72\sqrt{26}}{100}$.

We can verify our answer by checking that the sum of all probabilities equals 1 and that each probability is non-negative.

### Citations:

1. [https://pplx-res.cloudinary.com/image/private/user_uploads/HBWXPFqzEpSERAy/image.jpg](https://pplx-res.cloudinary.com/image/private/user_uploads/HBWXPFqzEpSERAy/image.jpg)

---

Answer from Perplexity: [pplx.ai/share](https://www.perplexity.ai/search/pplx.ai/share)
# References


###### Information
- date: 2025.04.22
- time: 16:52