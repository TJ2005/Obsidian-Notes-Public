---
Title: Probability & Statistics Lecture 1
Status: true
marker:
  - "[[mathematics]]"
  - "[[Probability and Statistics (PNS)]]"
  - "[[Probability]]"
tags: 
Date: 2025.02.03
Time: 11:23
---
# Basic Probability
![[Basic Probability#Basic Probability]]

**Example 1**: If two dice are rolled, what is the probability that the sum of the upturned faces will equal 7?
**Solution**: 
Let $n(S) = 36$.
Let $A$ be the event that the sum is 7, so 
$A = \{ (1, 6), (6, 1), (3, 4), (4, 3), (2, 5), (5, 2) \}$.
Therefore, $n(A) = 6$.
Thus, 
$$ P(A) = \frac{n(A)}{n(S)} = \frac{6}{36} = \frac{1}{6}. $$

---

**Example 2**: A fair coin is tossed 4 times. Define the sample space corresponding to this random experiment. Also, give the subsets corresponding to the following events and find the respective probabilities:

**Solution**:
Let $S$ be the sample space:
$$ S = \{ HHHH, HHTH, HHHT, HHTT, HTTH, HTTT, THHH, THTH, THTT, TTHH, TTHT, TTTT \} $$

(a) More heads than tails are obtained:

Let $A = \{ HHHH, HHTH, HHHT, HHTT \}$.

Thus, 
$$ P(\text{more heads than tails}) = \frac{5}{16}. $$

(b) Tails occur on all even-numbered tosses:

Let $B = \{ HTHT, HTHT, TTHH, TTTT \}$.

Thus, 
$$ P(B) = \frac{4}{16} = \frac{1}{4}. $$

---

**Example 3**: If 3 balls are randomly drawn from a bowl containing 6 white and 5 black balls, what is the probability that one of the balls is white and the other two are black?

**Solution**:
The total number of balls is 11. Therefore, 
$$ n(S) = \binom{11}{3}. $$

We want to select 1 white ball and 2 black balls. The number of favorable outcomes is 
$$ \binom{6}{1} \times \binom{5}{2}. $$

Thus, the probability is 
$$ P(A) = \frac{\binom{6}{1} \times \binom{5}{2}}{\binom{11}{3}} = \frac{4}{11}. $$

---

**Example 4**: From 6 positive and 8 negative numbers, 4 numbers are chosen at random and multiplied. What is the probability that the product is positive?

**Solution**:
We can select 4 numbers in the following cases:
- Case 1: All are positive.
- Case 2: Two positive and two negative.
- Case 3: All are negative.

The total number of ways to select 4 numbers is 
$$ n(S) = \binom{14}{4}. $$

The number of ways the product is positive is 
$$ 6C4 + 6C2 \cdot 8C2 + 8C4. $$

Thus, the probability is 
$$ P(A) = \frac{6C4 + 6C2 \cdot 8C2 + 8C4}{n(S)} = \frac{505}{1001}. $$ 


---

# References
- Lectures
- Teams Notes

> [!Continued to]
> [[Probability and Statistics Lecture 2]]

###### Information
- date: 2025.02.03
- time: 11:23