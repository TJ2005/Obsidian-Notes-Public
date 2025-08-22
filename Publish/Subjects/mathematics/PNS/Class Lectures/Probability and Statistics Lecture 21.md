---
Title: Probability and Statistics Lab 16
Status: true
marker: 
tags: 
Date: 2025.02.19
Time: 14:08
---
> [!Continued From]
> [[Probability and Statistics Lecture 15]]


# Normal Distribution
# Questions
In an exam we can buy $800$ students. The $average$ and $standard~~deviation$ of marks obtained are $40\%$ and $10\%$. Find
1. number of students who will pass if $50\%$ is kept as minimum 
2. What should be the minimum score if $350$ Candidates are to be declared passed.
3. How many candidates have scored marks above $60\%$

### Answer
**Random Variable** : its what the average and standard deviation is describing about
$X\sim N(\mu=40,\sigma=10)$

#### 1. number of students who will pass if $50\%$ is kept as minimum 

$P(X>50)$ is what we are trying to find here
$$
P(X>50)=P(\frac{X-M}{\sigma}> \frac{50-40}{10})
$$
$$
P(X>50)=P(Z>1)
$$
$$
P(X>50)=0.1557
$$
$$
\text{no of students who score atleast 50\%} = P(X>50)\times 800
$$
$$
0.1557\times 800=127
$$

#### 2. What should be minimum score if 350 candidates are to be declared pass
We just discovered that the number of students that will pass is 127 by multiplying the probability with 800

$$
350 = P(X>X_{min})\times {800}
$$
$$ 
P(X>X_{min})=\frac{350}{800}
$$
$$
P(X>X_{min})=0.4375
$$
$$
P(X<X_{min})=0.5-0.4375
$$

We have flipped the 

## Question 2
The mean height of $500$ students is $151cms$ and the $standard~~deviation$ is $15cms$ assuming that the heights are normally distributed find 
1. The number of students whose height lies between $120$ and $155$ cms
### Answer
**Random Variable**: The random variable here is height of the students they are rather short.

We have been asked this
$P(120<X<155)$

$$
P(120<X<155)=P\left( \frac{{120-155}}{15} < \frac{{X-\mu}}{\sigma}< \frac{{155-151}}{15}\right)
$$
$$
P(120<X<155)=P\left( \frac{-31}{2} <Z < \frac{{3}}{15}\right)
$$
$$
P(120<X<155)=P\left( -2.07<Z < 0.27\right)
$$
$$
P(120<X<155)=P\left( -2.07<Z )+P(Z< 0.27\right)
$$
$$
P(120<X<155)=P\left( 2.07>Z )+P(Z< 0.27\right)
$$
$$
\text{Multiplied by left inequality by -1.}
$$
$$
P(120<X<155)=0.4808+0.1064
$$
$$
P(120<X<155)=0.5872
$$
$$
\text{Multiply that with 500}
$$
$$
P(120<X<155)\times 500= 0.5872=293.6$$
Number of students that have height greater than $120cms$ and less than $155cms$ is 293. ( Absolute Value )

$$$$

## Question 3
Fit a Binomial Distribution for the following

| X   | 0   | 1   | 2   | 3   | 4   | 5   | 6   | Total |
| --- | --- | --- | --- | --- | --- | --- | --- | ----- |
| $f$ | 5   | 18  | 28  | 12  | 7   | 6   | 4   | 80    |
Here n is equal to 6 and we can calculate $mean$ from the table.

- $n=6$
- $\text{mean of x}=E(x)=\sum \frac{xf}{f}$
- $mean$ = $2.4$
- $p = 2.4$

Plug this in the calculator for
 $n=6$ and $p=2.4$

## Question 4


# References


###### Information
- date: 2025.02.19
- time: 14:08
> [!Continued to]
> [[Probability and Statistics Lecture 17]]
