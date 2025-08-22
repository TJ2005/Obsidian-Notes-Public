---
Title: Probability & Statistics Lecture 3
Status: 
marker: 
tags: 
Date: 2025.01.10
Time: 11:41
---
> [!Continued From]
> [[Probability and Statistics Lecture 2]]

> [!WARNING]
> I was absent for this lecture. 
# Probability & Statistics Lecture 3
![[Baye's Theorem#Bayes' Theorem]]
# Baye's Theorem
When we are calculating a conditional probability
$$
P(D_n/E)=\frac{P(D_n\cap E)}{P(E)}=P(D_n)* P(E/D_2)
$$
---
# Questions
## Question 1
A box contains 4 bad and 6 good tubes. Two are drawn out from the box at a time. One of them is tested and found to be good. What is the probability that the other one is also good?

### Solution:
Let $A$ = one of the tubes drawn is good and  
$B$ = the other tube is good.

The probability that both tubes drawn are good is:

$$
P(A \cap B) = P(\text{both tubes drawn are good}) = \frac{C\binom{6}{2}}{C\binom{10}{2}} = \frac{1}{3}
$$

Knowing that one tube is good, the conditional probability that the other tube is also good is:

$$
P(B \mid A) = \frac{P(A \cap B)}{P(A)} = \frac{1/3}{8/10} = \frac{5}{9}
$$
---
## Question 2
Q.02 Two fair dice are thrown independently. Three events $A$, $B$, and $C$ are defined as follows:

(i) odd face with the first die,
(ii) odd face with the second die,
(iii) sum of the numbers on the two dice is odd.  
Are the events $A$, $B$, and $C$ mutually independent?

### Solution:
The probabilities are:
$$
P(A) = \frac{3}{6} = \frac{1}{2}, \quad P(B) = \frac{3}{6} = \frac{1}{2}
$$

The outcomes favorable to the event $C$ are:  
$(1,2), (1,4), (1,6), (2,1), (2,3), (2,5), \dots$  
Thus, 
$$
P(C) = \frac{1}{2}
$$

Next, let's find the intersection probabilities:
$$
P(A \cap B) = P(B \cap C) = P(C \cap A) = \frac{1}{4}
$$

Since $P(A \cap B) = P(A) \cdot P(B)$, we know that:
$$
P(B \cap C) = P(B) \cdot P(C)
$$

However, we find:
$$
P(A \cap B \cap C) = 0
$$

Since $P(A \cap B \cap C) \neq P(A) \cdot P(B) \cdot P(C)$, the events $A$, $B$, and $C$ are **pairwise independent** but **not mutually independent**.

---
## Question 3
Q.02 Two fair dice are thrown independently. Three events $A$, $B$, and $C$ are defined as follows:
- (i) Odd face with the first die.
- (ii) Odd face with the second die.
- (iii) The sum of the numbers on the two dice is odd.

Are the events $A$, $B$, and $C$ mutually independent?

### Solution:
The probabilities for each event are:
$$
P(A) = \frac{3}{6} = \frac{1}{2}, \quad P(B) = \frac{3}{6} = \frac{1}{2}
$$

The outcomes favorable to the event $C$ (the sum of the numbers on the two dice is odd) are:
$$(1,2), (1,4), (1,6), (2,1), (2,3), (2,5), \dots$$
Thus, 
$$
P(C) = \frac{18}{36} = \frac{1}{2}
$$

Next, let's find the intersection probabilities:
$$
P(A \cap B) = P(B \cap C) = P(C \cap A) = \frac{1}{4}
$$

Since $P(A \cap B) = P(A) \cdot P(B)$, we know that:
$$
P(B \cap C) = P(B) \cdot P(C)
$$

However, we find:
$$
P(A \cap B \cap C) = 0
$$

Since $P(A \cap B \cap C) \neq P(A) \cdot P(B) \cdot P(C)$, the events $A$, $B$, and $C$ are $\textbf{pairwise independent} but \textbf{not mutually independent}$.

---
## Question
**Q.03** From 6 positive and 8 negative numbers, 4 numbers are chosen at random (without replacement) and multiplied. What is the probability that the product is positive?

### Solution:

To ensure that the product is positive, we need to consider the following possibilities:

- All 4 numbers must be positive.
- All 4 numbers must be negative.
- Two numbers must be positive, and the other two must be negative (since multiplying an even number of negative numbers results in a positive product).

### Step 1: Calculate the Number of Ways for Each Case

1. **All 4 numbers are positive:**

   The number of ways to choose 4 positive numbers from the 6 positive numbers is given by the combination formula:

   $$
   \binom{6}{4} = 15
   $$

2. **All 4 numbers are negative:**

   The number of ways to choose 4 negative numbers from the 8 negative numbers is:

   $$
   \binom{8}{4} = 70
   $$

3. **Two numbers are positive, and two numbers are negative:**

   The number of ways to choose 2 positive and 2 negative numbers is the product of the combinations:

   $$
   \binom{6}{2} \times \binom{8}{2} = 15 \times 28 = 420
   $$

### Step 2: Calculate the Total Number of Ways to Choose 4 Numbers

The total number of ways to choose 4 numbers from the 14 available (6 positive + 8 negative) is:

$$
\binom{14}{4} = 1001
$$

### Step 3: Calculate the Probability

The probability that the product is positive is the ratio of the favorable outcomes (where the product is positive) to the total possible outcomes. Therefore, the probability is:

$$
P(\text{Product is positive}) = \frac{\text{Number of favorable ways}}{\text{Total number of ways}} = \frac{15 + 70 + 420}{1001} = \frac{505}{1001}
$$

Thus, the probability that the product is positive is:

$$
P(\text{Product is positive}) = \frac{505}{1001}
$$
---
## Question
**Q.04** A lot consists of 10 good articles, 4 with minor defects, and 2 with major defects. Two articles are chosen from the lot at random (without replacement). Find the probability that:

1. **Both are good**.
2. **Both have major defects**.
3. **At least 1 is good**.
4. **Almost 1 is good**.
5. **Exactly 1 is good**.

### Solution:

#### 1. Probability that both are good

We need to find the probability that both articles chosen are good. This is the number of ways to choose 2 good articles divided by the total number of ways to choose 2 articles from 16.

The number of ways to choose 2 good articles from 10 is $$\binom{10}{2}$$, and the total number of ways to choose 2 articles from 16 is $$\binom{16}{2}$$. Therefore, the probability is:

$$
P(\text{both are good}) = \frac{\binom{10}{2}}{\binom{16}{2}} = \frac{45}{120} = \frac{3}{8}.
$$

#### 2. Probability that both have major defects

Now, we want to calculate the probability that both articles have major defects. There are 2 articles with major defects, and we need to choose 2 from these 2. The number of ways to choose 2 articles with major defects is $\binom{2}{2}$, and the total number of ways to choose 2 articles from 16 is still $\binom{16}{2}$. Therefore, the probability is:

$$
P(\text{both have major defects}) = \frac{\binom{2}{2}}{\binom{16}{2}} = \frac{1}{120}.
$$

#### 3. Probability that at least 1 is good

For this case, we need to calculate the probability that **at least one article is good**. This can happen in two cases:
- Exactly 1 good article and 1 defective article (either minor or major).
- Both articles are good.

To calculate this, we need the following:
1. The number of ways to choose exactly 1 good article from 10 is $\binom{10}{1}$.
2. The number of ways to choose 1 defective article (from 6 total defective articles) is $\binom{6}{1}$.
3. The number of ways to choose 2 good articles from 10 is $\binom{10}{2}$.

Thus, the total favorable outcomes for "at least 1 good" is:

$$
\binom{10}{1} \times \binom{6}{1} + \binom{10}{2}.
$$

Now, the total number of possible ways to choose 2 articles from 16 is $\binom{16}{2}$. Therefore, the probability that at least one article is good is:

$$
P(\text{at least 1 is good}) = \frac{\binom{10}{1} \times \binom{6}{1} + \binom{10}{2}}{\binom{16}{2}} = \frac{10 \times 6 + 45}{120} = \frac{105}{120} = \frac{7}{8}.
$$

#### 4. Probability that almost 1 is good

"Almost 1 is good" means that either **none are good** or **1 is good and 1 is defective**. 

We already know:
- The number of ways to choose 2 defective articles from 6 is $\binom{6}{2}$.
- The number of ways to choose 1 good and 1 defective article is $\binom{10}{1} \times \binom{6}{1}$.

Therefore, the total favorable outcomes for "almost 1 is good" is:

$$
P(\text{almost 1 is good}) = \frac{\binom{6}{2} + \binom{10}{1} \times \binom{6}{1}}{\binom{16}{2}} = \frac{15 + 60}{120} = \frac{75}{120} = \frac{5}{8}.
$$

#### 5. Probability that exactly 1 is good

To find the probability that exactly 1 article is good and the other is defective, we already know:
- The number of ways to choose 1 good article from 10 is $\binom{10}{1}$.
- The number of ways to choose 1 defective article from 6 is $\binom{6}{1}$.

Thus, the total favorable outcomes for "exactly 1 good" is:

$$
P(\text{exactly 1 is good}) = \frac{\binom{10}{1} \times \binom{6}{1}}{\binom{16}{2}} = \frac{10 \times 6}{120} = \frac{60}{120} = \frac{1}{2}.
$$


# References

> [!Continued to]
>  [[Probability and Statistics Lecture 4]]


###### Information
- date: 2025.01.10
- time: 11:41