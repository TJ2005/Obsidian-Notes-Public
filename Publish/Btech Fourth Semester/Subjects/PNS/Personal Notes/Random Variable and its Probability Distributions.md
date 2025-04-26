---
Title: Random Variable and its Probability Mass Function
Status: 
marker: 
tags: 
Date: 2025.03.13
Time: 07:50
---
# Random Variables

Imagine we are taking into account the values that a die can give us. One can call the random variable as $X$ and the possible values it can take as $x$.
- $X$ can take on the values $1, 2, 3, 4, 5, 6$. 
- It can be represented as $X = x$ for $x \in {1, 2, 3, 4, 5, 6}$.
$X$ here is the **random variable**
#### Definition

A **random variable** is a function that assigns a numerical value to each **sample point** in a **sample set** (sample space) of a random phenomenon. It can be classified as:

1. **Discrete Random Variables**: Take on a finite or countable set of values (e.g., number of defective items in a batch).
2. **Continuous Random Variables**: Take on an infinite set of values within a range (e.g., the time it takes for a radioactive particle to decay).

### Example: Two Coins Tossed

|**Outcome (S)**|**HH**|**TH**|**HT**|**TT**|
|---|---|---|---|---|
|**X (Values)**|2|1|1|0|

- **Sample Space (S)**: The set of all possible outcomes.
- **Sample Point**: An individual outcome in the sample space.

---
## Probability Distribution
In the above example we had $X$ taking on values $1, 2, 3, 4, 5, 6$. We can assign probabilities to these values with factual information. This is what a probability distribution does. 
So for each value of $x$ on $X$ we have a probability $P(X=x)$. This is called the **probability mass function (PMF)**.

### Definition
A **probability distribution** describes how probabilities are assigned to possible values of a random variable. It determines the likelihood of events.

### Types:
1. **For Discrete Random Variables**:
    - Represented by a **probability mass function (PMF)**.
    - Example: Rolling a die has $P(X=x)=16$
    - $P(X = x) = \frac{1}{6}$
    - $for x∈{1,2,3,4,5,6}$
2. **For Continuous Random Variables**: ^dfe7dd
    - Represented by a **probability density function (PDF)**.
	    - Meaning there is a function $f(X=x)$ such that for any value x it has a defined output.
    - Probabilities are calculated as areas under the curve of the PDF.

---
## Random Variable Types
- **Discrete Random Variable**: Has finite or countable values.
	- Example : Number of telephone calls received per unit time in a telephone exchange.
	- Example : Number of second year students who have got about 90% marks
	- Example : Number of alpha particles by a radioactive substance.
- **Continuous Random Variable**: Has infinite values. Its Uncountable
---

## Need for This Method
This method helps calculate probabilities in situations such as tossing a coin until a head appears or analysing decay time in nuclear processes.

---

## Example in Nuclear Problems
Random variables can describe phenomena such as:
1. **Decay Time**: Time taken for a radioactive atom to decay (continuous random variable).
2. **Number of Neutrons Released**: In a nuclear reaction (discrete random variable).
Steps:
3. Assign a real number to the decay time of each atom (a random sample point).
4. Analyse the probability distribution of decay times to predict the system’s behavior.



---

> [!Questions Related to Random Variable and its Probability Distributions]
> - To solve questions one can refer to
> 	- [[Probability and Statistics Lecture 7]] - 
> - R studio
> 	- [[Probability and Statistics Lab 4 Part 1]] 
> 	- [[Probability and Statistics Lab 4 Part 2]].


# References
- Probability and Statistics Lectures at MPSTME
###### Information
- date: 2025.03.13
- time: 07:50
- Continued to 