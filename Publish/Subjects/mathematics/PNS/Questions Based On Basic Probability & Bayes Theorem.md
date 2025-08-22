---
Title: Questions Based On Basic Probability
Status: true
marker:
  - "[[Probability and Statistics (PNS)]]"
  - "[[Basic Probability]]"
  - "[[Baye's Theorem]]"
  - "[[DWM Naive Bayes]]"
  - "[[Theory of Total Probability]]"
tags:
  - BTech
  - Note
Date: 2025.04.24
Time: 10:24
---
# Questions Based On Basic Probability

> [!Based On]
> [[Basic Probability]]

# Probability Problems

## Problem 1: Sum of Dice Equals 7

When rolling two dice, the possible outcomes for each die are {1, 2, 3, 4, 5, 6}.

The total number of possible outcomes when rolling two dice = 6 × 6 = 36

Favorable outcomes where sum equals 7:  
(1,6), (2,5), (3,4), (4,3), (5,2), (6,1) = 6 outcomes

Therefore:  
$P(\text{sum} = 7) = \frac{6}{36} = \frac{1}{6}$

## Problem 2: Coin Toss Experiment

Sample space when tossing a fair coin 4 times:  
$S = {HHHH, HHHT, HHTH, HHTT, HTHH, HTHT, HTTH, HTTT, THHH, THHT, THTH, THTT, TTHH, TTHT, TTTH, TTTT}$

Total outcomes = $2^4 = 16$

a) More heads than tails:  
This occurs when we have 3 or 4 heads.

- 4 heads: ${HHHH}$ (1 outcome)
    
- 3 heads: ${HHHT, HHTH, HTHH, THHH}$ (4 outcomes)
    

Total favorable outcomes = 5  
$P(\text{more heads than tails}) = \frac{5}{16}$

b) Tails on even-numbered tosses:  
This means the 2nd and 4th tosses are tails.  
Favorable outcomes: ${HTHT, TTHT, HTTT, TTTT}$ (4 outcomes)

$P(\text{tails on even tosses}) = \frac{4}{16} = \frac{1}{4}$

## Problem 3: Drawing Balls from a Bowl

We have 6 white and 5 black balls, total 11 balls.  
We need to draw 3 balls with 1 white and 2 black.

By Combinations
Ways to select 1 white ball from 6 white balls = $\binom{6}{1} = 6$  
Ways to select 2 black balls from 5 black balls = $\binom{5}{2} = 10$

Total favorable outcomes = $6 \times 10 = 60$

Total possible outcomes when drawing 3 balls from 11 = $\binom{11}{3} = 165$

$P(\text{1 white and 2 black}) = \frac{60}{165} = \frac{4}{11}$

## Problem 4: Product of Random Numbers

We have 6 positive and 8 negative numbers, and we select 4 numbers.

For the product to be positive, we need an even number of negative numbers (0, 2, or 4).

- Selecting 0 negative numbers: $\binom{8}{0}\binom{6}{4} = 1 \times 15 = 15$
    
- Selecting 2 negative numbers: $\binom{8}{2}\binom{6}{2} = 28 \times 15 = 420$
    
- Selecting 4 negative numbers: $\binom{8}{4}\binom{6}{0} = 70 \times 1 = 70$
    

Total favorable outcomes = 15 + 420 + 70 = 505

Total possible outcomes = $\binom{14}{4} = 1001$

$P(\text{product is positive}) = \frac{505}{1001}$

# Bayes' Theorem
![[Baye's Theorem#Extended Form]]

## Problem 6: Rahul's Transportation

Given information:
- P(Bus) = 2/7
- P(Car) = 4/7
- P(Metro) = 1/7
- P(Late|Bus) = 3/8
- P(Late|Car) = 1/8
- P(Late|Metro) = 4/8

### Part i: Probability that Rahul reaches late

Using the law of total probability:
$$P(Late) = P(Bus) \cdot P(Late|Bus) + P(Car) \cdot P(Late|Car) + P(Metro) \cdot P(Late|Metro)$$

$$P(Late) = \frac{2}{7} \cdot \frac{3}{8} + \frac{4}{7} \cdot \frac{1}{8} + \frac{1}{7} \cdot \frac{4}{8}$$

$$P(Late) = \frac{6}{56} + \frac{4}{56} + \frac{4}{56} = \frac{14}{56} = \frac{1}{4}$$

### Part ii: Probability that Rahul traveled by car given that he reached late

Using Bayes' theorem:
$$P(Car|Late) = \frac{P(Car) \cdot P(Late|Car)}{P(Late)}$$

$$P(Car|Late) = \frac{\frac{4}{7} \cdot \frac{1}{8}}{\frac{1}{4}} = \frac{\frac{4}{56}}{\frac{14}{56}} = \frac{4}{14} = \frac{2}{7}$$

## Problem 7: Siya's Die Roll

Given information:
- P(Truth) = 3/8
- P(Lie) = 5/8
- Die has 6 faces with equal probability

### Part i: Probability that she reports a 6

Let's define:
- A: Actual roll is 6
- B: Siya reports 6

We know:
- P(A) = 1/6 (probability of rolling a 6)
- P(B|A) = 3/8 (if she rolls 6, she reports 6 with probability of telling truth)
- P(B|not A) = 5/8 × 1/5 = 1/8 (if she doesn't roll 6, she reports 6 with probability of lying and choosing 6 among 5 possible false reports)

Using total probability:
$$P(B) = P(A) \cdot P(B|A) + P(not\ A) \cdot P(B|not\ A)$$

$$P(B) = \frac{1}{6} \cdot \frac{3}{8} + \frac{5}{6} \cdot \frac{1}{8}$$

$$P(B) = \frac{3}{48} + \frac{5}{48} = \frac{8}{48} = \frac{1}{6}$$

### Part ii: If she reports a 6, probability that it is a 6

Using Bayes' theorem:
$$P(A|B) = \frac{P(A) \cdot P(B|A)}{P(B)}$$

$$P(A|B) = \frac{\frac{1}{6} \cdot \frac{3}{8}}{\frac{1}{6}} = \frac{3}{8}$$

---
# Probability Problems on Baye's & Conditional 

> [!info] Note Collection
> These are probability problems covering various concepts including Bayes' theorem, independent events, and conditional probability.

## Example 8: Union of Events

If A, B and C are any 3 events such that:
- P(A) = P(B) = P(C) = 1/4
- P(A ∩ B) = P(B ∩ C) = 0
- P(C ∩ A) = 1/8

To find P(A ∪ B ∪ C), we use the formula:
P(A ∪ B ∪ C) = P(A) + P(B) + P(C) - P(A ∩ B) - P(B ∩ C) - P(C ∩ A) + P(A ∩ B ∩ C)

Since P(A ∩ B) = 0, events A and B are mutually exclusive, meaning they cannot occur simultaneously.
Similarly, P(B ∩ C) = 0 means B and C are mutually exclusive.

Therefore, P(A ∩ B ∩ C) must be 0 (if two events are mutually exclusive, the intersection of all three must be empty).

P(A ∪ B ∪ C) = 1/4 + 1/4 + 1/4 - 0 - 0 - 1/8 + 0
P(A ∪ B ∪ C) = 3/4 - 1/8 = 6/8 - 1/8 = 5/8

## Example 12: Shooting Test

Given:
- P(A hits) = 1/2
- P(B hits) = 2/3
- P(C hits) = 3/4

(i) Probability that none of them hits the target:
P(none hit) = P(A misses) × P(B misses) × P(C misses)
P(none hit) = (1-1/2) × (1-2/3) × (1-3/4)
P(none hit) = 1/2 × 1/3 × 1/4 = 1/24

(ii) Probability that at least one hits the target:
P(at least one hits) = 1 - P(none hit) = 1 - 1/24 = 23/24

## Problem 3: Solving a Problem Independently

Given:
- P(A solves) = 1/2
- P(B solves) = 3/4

The problem is solved if either A or B or both solve it.
P(problem is solved) = P(A solves ∪ B solves)
P(problem is solved) = P(A solves) + P(B solves) - P(A solves ∩ B solves)

Since they work independently:
P(A solves ∩ B solves) = P(A solves) × P(B solves) = 1/2 × 3/4 = 3/8

Therefore:
P(problem is solved) = 1/2 + 3/4 - 3/8 = 4/8 + 6/8 - 3/8 = 7/8

## Problem 4: Divisibility Problem

From numbers 1 to 100:
- Numbers divisible by 6: 6, 12, 18, ..., 96 = 16 numbers
- Numbers divisible by 8: 8, 16, 24, ..., 96 = 12 numbers
- Numbers divisible by both 6 and 8 (LCM = 24): 24, 48, 72, 96 = 4 numbers

(i) & (ii) are the same in this case:
P(divisible by 6 or 8) = P(divisible by 6) + P(divisible by 8) - P(divisible by both)
P(divisible by 6 or 8) = 16/100 + 12/100 - 4/100 = 24/100 = 6/25

## Problem 5: Sum of Two Chips

Given 10 chips numbered 1 through 10, we need to find P(sum = 10).

Total number of ways to draw 2 chips from 10 = $\binom{10}{2} = 45$

Favorable outcomes: (1,9), (2,8), (3,7), (4,6), (5,5) = 5 pairs

P(sum = 10) = 5/45 = 1/9

## Problem 6: Middle Number is 5

When 3 tickets are drawn from 10 tickets and arranged in ascending order:

Total number of ways to draw 3 tickets from 10 = $\binom{10}{3} = 120$

For 5 to be the middle number, we need one number less than 5 and one number greater than 5.
Numbers less than 5: 1, 2, 3, 4 (4 numbers)
Numbers greater than 5: 6, 7, 8, 9, 10 (5 numbers)

Number of favorable outcomes = $\binom{4}{1} \times \binom{5}{1} = 4 \times 5 = 20$

P(middle number is 5) = 20/120 = 1/6

## Problem 7: At Least One Ball of Each Color

Given:
- 4 white, 5 red, and 6 black balls
- 4 balls drawn at random

Total number of ways to draw 4 balls = $\binom{15}{4} = 1365$

For at least one ball of each color, we need to count:
- 1W, 1R, 2B: $\binom{4}{1} \times \binom{5}{1} \times \binom{6}{2} = 4 \times 5 \times 15 = 300$
- 1W, 2R, 1B: $\binom{4}{1} \times \binom{5}{2} \times \binom{6}{1} = 4 \times 10 \times 6 = 240$
- 2W, 1R, 1B: $\binom{4}{2} \times \binom{5}{1} \times \binom{6}{1} = 6 \times 5 \times 6 = 180$

Total favorable outcomes = 300 + 240 + 180 = 720

P(at least one ball of each color) = 720/1365 = 8/15

## Problem 8: Students Solving a Problem

Given:
- P(1st student solves) = 1/2
- P(2nd student solves) = 1/3
- P(3rd student solves) = 1/4

(i) Probability only one student solves the problem:
P(only 1st) = P(1st solves) × P(2nd fails) × P(3rd fails) = 1/2 × 2/3 × 3/4 = 1/4
P(only 2nd) = P(1st fails) × P(2nd solves) × P(3rd fails) = 1/2 × 1/3 × 3/4 = 1/8
P(only 3rd) = P(1st fails) × P(2nd fails) × P(3rd solves) = 1/2 × 2/3 × 1/4 = 1/12

P(only one solves) = 1/4 + 1/8 + 1/12 = 3/12 + 3/24 + 2/24 = 3/12 + 5/24 = 6/24 + 5/24 = 11/24

(ii) Probability the problem is solved:
P(problem is solved) = 1 - P(none solve)
P(none solve) = P(1st fails) × P(2nd fails) × P(3rd fails) = 1/2 × 2/3 × 3/4 = 1/4
P(problem is solved) = 1 - 1/4 = 3/4

## Problem 9: Bayes' Theorem Application

Given:
- P(pass|study) = 0.9
- P(pass|not study) = 0.2
- P(study) = 0.75

Using Bayes' theorem to find P(study|pass):

$$P(study|pass) = \frac{P(study) \times P(pass|study)}{P(pass)}$$

Where P(pass) = P(study) × P(pass|study) + P(not study) × P(pass|not study)
P(pass) = 0.75 × 0.9 + 0.25 × 0.2 = 0.675 + 0.05 = 0.725

Therefore:
P(study|pass) = (0.75 × 0.9)/0.725 = 0.675/0.725 = 27/29 ≈ 0.931

Citations:
[1] https://pplx-res.cloudinary.com/image/private/user_uploads/JJHYrmuIgHFtRkS/image.jpg
[2] https://www.hitbullseye.com/Probability-Examples.php
[3] https://math.stackexchange.com/questions/85849/calculating-the-probability-that-at-least-one-of-a-series-of-events-will-happen
[4] https://testbook.com/question-answer/the-probability-that-a-person-hits-a-target-is-0-5--6316dd72489cc64fdf455e58
[5] https://www.doubtnut.com/qna/2811
[6] https://www.vedantu.com/question-answer/the-probability-of-choosing-at-random-a-number-class-12-maths-cbse-60de78ed8c970336f779ba0e
[7] https://www.geeksforgeeks.org/what-is-the-probability-of-rolling-a-sum-of-10-with-two-dice/
[8] https://www.knowledgeboat.com/question/tickets-numbered-3-5-7-9-29-are-placed-in-a-box-and-mixed--576687008323786800
[9] https://www.cuemath.com/ncert-solutions/i-complete-the-following-table-ii-a-student-argues-that-there-are-11-possible-outcomes-2-3-4-5-6-7-8-9-10-11-and-12/
[10] https://byjus.com/jee/probability-problems/
[11] https://www.teachoo.com/subjects/cbse-maths/class-12th/ch13-12th-probability/
[12] https://byjus.com/maths/probability-questions/
[13] https://askfilo.com/user-question-answers-mathematics/a-box-contains-6-red-4-white-and-5-black-balls-a-person-36303536383838
[14] https://thirdspacelearning.com/us/blog/probability-questions/
[15] https://study.com/academy/lesson/the-at-least-one-rule-for-independent-events.html
[16] https://www.doubtnut.com/qna/621731385
[17] https://www.teachoo.com/12393/3415/Question-15/category/CBSE-Class-12-Sample-Paper-for-2021-Boards/
[18] https://www.vedantu.com/question-answer/an-integer-is-chosen-at-random-from-the-first-class-12-maths-cbse-5f6cb1b0d053ee34ae940d28
[19] https://byjus.com/question-answer/two-different-dice-are-rolled-simultaneously-find-the-probability-that-the-sum-of-the-numbers/
[20] https://math.stackexchange.com/questions/4393706/out-of-2n1-tickets-consecutively-numbered-three-are-drawn-at-random-the-chan
[21] https://www.vedantu.com/question-answer/a-bag-contains-6-r-4-w-and-8-b-balls-if-3-balls-class-12-maths-cbse-5f54e7870bee1f56f4b06baf

> [!note] Related Topics
> [[Basic Probability]] ^ce1a18
> - [[Probability Core Concepts]]
> - [[Baye's Theorem]]
> - [[Theory of Total Probability]]


> [!More questions and answers here]
> - [[Questions Based On Basic Probability & Bayes Theorem]]
> - [[Probability and Statistics Lecture 3]]
> - [[Probability and Statistics Lecture 4]]



# References


###### Information
- date: 2025.04.24
- time: 10:24