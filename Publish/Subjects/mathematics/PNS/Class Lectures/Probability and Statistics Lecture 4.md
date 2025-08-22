---
Title: Probability & Statistics Lecture 4
Status: 
marker:
  - "[[mathematics]]"
tags: 
Date: 2025.01.10
Time: 11:07
---
> [!Continued From]
>  [[Probability and Statistics Lecture 3]]

# Probability & Statistics Lecture 4

## Theorem of Total Probability
If there are ore than 1 Events that are contributing to one event we can talk about the inter-dependence of these events

### Example question
Lets say there are 3 doors E1 E2 E3 and there's a zombie apocalypse at your college. We are calculating the probability of escaping from E1,E2,E3 to save ourselves.

We will look into this question later

with the theorem of Total Probability we can say that the probability of escaping is
$P(E_{1}) * P(E/E_{1})$ + $P(E_{2})P(E/E_{2})$  + $P(E_{3})P(E/E_{3})$ 

Theorem of total probability: 
IF $B_1,B_2,...,B_n$ be a set of mutually exclusive and exhaustive events where $P(B_i)>0, \forall i$ and $A$ be any Event then
$P(A)=\sum_{i=1}^{n}P(B_i)P({A}/{B_i})$ 


## Example question Trick
![[IMG-20250730000529160.png]]
Now in this we have a complex query. After escaping what is the probability that the person has escaped from door 2.
We use the baye's theorem we have learnt in previous lecture 
![[Probability and Statistics Lecture 3#Baye's Theorem]]

# Questions
## Question1
There are Three true coins and one false coin. The false coin has heads on both sides. A coin is selected at  random and tossed 4 times. What is the probability that head occurs all four times?
### Answer 1
So there are 3 True coins and 1 False coin where the false coin has heads on both the sides.
We have total 4 coins
Let the true coin be $P(T)=3/4$
Let the false coin be $P(F)=1/4$

Probability of getting heads while having false coin is $P(H/F)=1$
Probability of getting heads while having false coin is $P(H/T)=1/2$

By theory of total probability 


$$
P(H)=P(F)\times P(H/F)+P(T)\times P(H/T)
$$


Total Probability = Probability of a false coin X Probability of getting heads while having a false coin + Probability of having a true coin X Probability of getting heads while having a true coin

$$
P(H)=1/4\times 1 + 3/4 \times (1/2)^4
$$
since the coin is tossed 4 times

Probability of it being the false coin when we know we got all heads 
$$
P(H|F)=\frac{P(F|H).P(H)}{P(F)}
$$
# References

> [!Continued to]
> [[Probability and Statistics Lecture 5]]

###### Information
- date: 2025.01.10
- time: 11:07