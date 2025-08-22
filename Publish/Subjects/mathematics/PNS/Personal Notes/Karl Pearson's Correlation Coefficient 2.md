---
Title: Karl Pearson's Correlation Coefficient
Status: 
marker:
  - "[[Probability and Statistics (PNS)]]"
  - "[[CoVariance]]"
tags:
  - BTech
Date: 2025.03.22
Time: 18:45
---
# Karl Pearson's Correlation Coefficient
Corelation is a statistical measure is a coefficient which describes the **size** and **direction** of the relation between two or more variables. Two variables are said to be corelated if the change in one variable affects the change in the other variable.
Karl Pearson's Correlation Coefficient between two variables $X$ and $Y$ is given by.

Here $\bar{X}$ is the average

Variation of a random variable $X$ is $E(X-\mu)^2$
Therefore,
$$
r=
E[(X-\bar{X})(Y-\bar{Y})]
$$
where $r$ is the coefficient of correlation
it has to be a number without unit so we divide 


$$
r=
\frac{E[(X-\bar{X})(Y-\bar{Y})]}{\sigma_{x} \sigma_{y}}
$$
$$
r=
\frac{E[(X-\bar{X})(Y-\bar{Y})]}{(E(X^2)-E(X)^2)(E(Y^2)-E(Y)^2)}
$$
$$
r=\frac{{\sum(X-\bar{X})(Y-\bar{Y})}}{\sqrt{ \sum E(X-X^2) E(Y-Y^2) }}
$$

$$
r=
\frac{\frac{{\sum XY}}{N}-\bar{X}\bar{Y}}{\sqrt{ \left( \frac{{\sum X^2}}{N}-\bar{X}^2 \right) \left( \frac{{\sum Y^2}}{N}-\bar{Y^2} \right) }}
$$
$$
r = \frac{{\sum xy}}{\sqrt{ \left( \sum X^2 \right)\left( \sum Y^2 \right) }}
$$





---
## Positive Correlation
Two variables are said to be positively correlated if they deviate to the same direction.  Examples are height & weight, income & expenditure.
https://www.investopedia.com/ask/answers/032515/what-does-it-mean-if-correlation-coefficient-positive-negative-or-zero.asp
## Negative Correlation
Two variables are said to be negatively correlated if they deviate in the opposite direction. Example volume and pressure of a perfect gas, price and demand.
## Uncorrelation
Two variable are said to be uncorrelated or statistically independent if there is no relation
### Implication from the value of $r$
Using Karl Pearson's coefficient we can conclude the following 
- if $r=1$ then correlation is perfectly positive
- if $r=-1$ then th5e correlation is perfectly negative
- if $r=0$ then variables are uncorrelated
and for values lying between $0~to~1$
- if $r\in(0,1)$ then correlation is perfectly positive
- if $r\in(-1,0)$ then the correlation is perfectly negative
- if $r=0$ then variables are uncorrelated- if $r\in(0,1)$ then the correlation is positive
# References


###### Information
- date: 2025.03.22
- time: 18:45