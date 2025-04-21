---
Title: Raw Moments
Status: 
marker:
  - "[[Probability and Statistics (PNS)]]"
tags:
  - BTech
Date: 2025.03.13
Time: 08:18
---
> [!INFO]
> In some snippets I have used $M$ to represent capital $\mu$ Since there is no support for capital mu try to interpret it as such.
## Moments
Moments are quantities that describe the shape of a distribution. These moments can be used to calculate $mean$, $variance$, $skewness$, $kurtosis$, and more details regarding them.
### Raw Moment
Moments are always described relative to a point. When a moment is relative to its origin $(O)$ It is given as 

$$r^{th}~raw~moment~~ \mu'_r=E((X-0)^r)=E(X^r)$$ The zero here denotes the value around which the moment is calculated. Here zero is the relative point. **For Raw Moments the relative point to which moments are calculated is zero**
$$\mu_o=E(1)=1$$
[[Expectation of a Random Variable#Properties|The property of expectation says that the expectation of constant is a constant]].

$$\mu^{'}_1=E(X)$$
$$\mu^{'}_2=E(X^2)$$
$$\mu^{'}_2=E(X^3)$$
and so on...
capital $\mu$ is used to represent the raw moments

---
### Central Moment
When a moment is relative to its mean its moments are said to be central moment

The $r^{th}$ Central Moment is given by 
$$\mu_r=E[(X-\mu)^r]$$
##### $0^{th}$ Central Moment
$$\mu_0 = 1$$
##### $1^{st}$ Central Moment
$$\mu_1=E[X-\mu]=[E(X)-M]=0$$
#### $2^{nd}$ Central Moment

1. **Solving for 2nd Central Moment**
   The given equation is:   $$E[(X-\mu)^2] = E[X^2 - 2X\mu + \mu^2] = E(X^2) - 2E(X)\mu + \mu^2$$
2. **Identify $\mu$ as the Mean:**
   Since $\mu$ represents the mean of $X$, we have:
   $$E(X) = \mu$$
3. **Substitute $E(X)$ with $\mu$:**
   Substitute $E(X)$ with $\mu$ in the equation:
   $$E[(X-\mu)^2] = E(X^2) - 2\mu^2 + \mu^2$$

4. **Simplify the Expression:**
   Simplify the right-hand side:
   $$E[(X-\mu)^2] = E(X^2) - \mu^2$$
5. **Relate to [[Expectation of a Random Variable#Formula for Variance|Variance]]:**
   The [[Expectation of a Random Variable#Formula for Variance|Variance]] $\sigma^2$ of a random variable $X$ is defined as:
   $$\sigma^2 = E[(X-\mu)^2]$$

   Therefore, we have:
   $$\sigma^2 = E(X^2) - \mu^2$$
So, the rewritten equation with $\mu$ and the derivation showing it as variance is:
$$\sigma^2 = E[(X-\mu)^2] = E(X^2) - \mu^2$$
This shows that the expected value of the squared deviation of $X$ from its mean $\mu$ is indeed the variance of $X$.

$$=E(X^2)-M^2$$
$$ = E(X^2)$$
---

#### Relation B/w Raw Moments and Central Moment
$$M_2=M_2'-(M_1')^2$$
$$M_2=M_2'-(M_1')^2$$
$$M_3=E[(X-M)^3]$$

$$M_3=M'_3-3M_2'M_1'+2(M'_1)^3$$

$$M_4=M'_4-4M_3~'M_1'+6M_2'~(M_1')^2+3~(M'_1)^4$$





# References


###### Information
- date: 2025.03.13
- time: 08:18