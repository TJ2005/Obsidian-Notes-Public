---
Title: Spearman's Correlation Coefficient
Status: true
marker:
  - "[[Probability and Statistics (PNS)]]"
  - "[[CoVariance]]"
tags: 
Date: 2025.03.22
Time: 18:46
---
# Spearman's Correlation Coefficient
Spearman's Correlation
$$
R = 1-\frac{{6\sum D^2}}{N^3 -N}
$$
the difference of ranks $$D = R_{1}-R_{2}$$
$N$ is the number of observations

## Note for equal ranks
If two items have the same rank then assign the average of the ranks to both of them. 
That is if if two items have the same rank then assign the average of the ranks to both of them. 
For example, if two items have the same rank 2 then assign the rank 2.5 to both of them. 

If there are three items that have the ranks 4,4,4 then assign $\frac{{4+5+6}}{3}$ = $5$ to all of them.

If '$m$' are the items having equal rank then a factor of $\frac{(m^3-m)}{12}$ is added to  $\sum D^2$ .
if there is more than one case of equal ranks then this factor gets added correspondingly for each case

thus 
$$
R = 1 - \frac{{6\sum D^2 + \sum \frac{(m^3_{i}-m_{i})}{12}}}{N^3 -N}
$$
Where $i$ is the number of cases of equal ranks

# References


###### Information
- date: 2025.03.22
- time: 18:46