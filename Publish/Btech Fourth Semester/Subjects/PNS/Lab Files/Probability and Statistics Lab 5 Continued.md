---
Title: Probability and Statistics Lab 5 Continued
Status: 
marker: 
tags: 
Date: 2025-02-11
Time: 21:21
---
# Probability and Statistics Lab 5 Continued
## Questions
### Question 1
The first four moments of a distribution about the value 5 of the random variable X are 2, 20, 40 and 50. Compute a measure, each of central tendency, dispersion, skewness and kurtosis. Comment on the skewness and kurtosis of the distribution.
#### Code
```R
momentsat51=2
momentsat52=20
momentsat53=40
momentsat54=50
a=5
momat5=c(1,momentsat51,momentsat52,momentsat53,momentsat54)
b=raw2central(momat5)
b
variance=b[3]
skewness=b[4]/b[3]^(3/2)
skewness
kurtosis=b[5]/(b[3]^2)
kurtosis
```

```bash
> momentsat51=2
> momentsat52=20
> momentsat53=40
> momentsat54=50
> a=5
> momat5=c(1,momentsat51,momentsat52,momentsat53,momentsat54)
> b=raw2central(momat5)
> b
[1]   1   0  16 -64 162
> variance=b[3]
> skewness=b[4]/b[3]^(3/2)
> skewness
[1] -1
> kurtosis=b[5]/(b[3]^2)
> kurtosis
[1] 0.6328125
```


### Question 2
The first three moments of the distribution about the value 3 of the random variable are 2, 10, -30 respectively. Find mean variance and skewness. Write a R program for above problem.
#### Code
```R
momentsat31=2
momentsat32=10
momentsat33=-30
a=3
momat3=c(1,momentsat31,momentsat32,momentsat33)
b=raw2central(momat3)
b
variance=b[3]
skewness=b[4]/b[3]^(3/2)
skewness
```
``
```bash
momentsat31=2
> momentsat32=10
> momentsat33=-30
> a=3
> momat3=c(1,momentsat31,momentsat32,momentsat33)
> b=raw2central(momat3)
> b
[1]   1   0   6 -74
> variance=b[3]
> skewness=b[4]/b[3]^(3/2)
> skewness
[1] -5.035062
```
### Question 3
The first three moments of the distribution about the value 2 of the random variable are 1, 16, -40 respectively. Find mean, variance and skewness.
#### Code
```R
#q2 
momentsat21=1
momentsat22=16
momentsat23=-40
a=2
momat2=c(1,momentsat21,momentsat22,momentsat23)
b=raw2central(momat2)
b
variance=b[3]
skewness=b[4]/b[3]^(3/2)
skewness
```

```bash
 #q2 
> momentsat21=1
> momentsat22=16
> momentsat23=-40
> a=2
> momat2=c(1,momentsat21,momentsat22,momentsat23)
> b=raw2central(momat2)
> b
[1]   1   0  15 -86
> variance=b[3]
> skewness=b[4]/b[3]^(3/2)
> skewness
[1] -1.48034
```

### Question 4
Given a distribution with mean=10, variance=16, skewness=1, and kurtosis=4, find the raw moments about the origin.
#### Code
```R
#q4 
mean=10
variance=16
skewness= 1
kurtosis= 4
momentsat41=mean
momentsat42=variance + mean^2
momentsat42
momentsat43=skewness*(variance^(3/2)) + 3 * mean* momentsat42 - 2 * mean^3
momentsat43
momentsat44=kurtosis* (variance^2) + (4 * mean*momentsat43) - (6 * mean^2 * momentsat42) + 3*mean^4
momentsat44
```

```bash
 #q4 
> mean=10
> variance=16
> skewness= 1
> kurtosis= 4
> momentsat41=mean
> momentsat42=variance + mean^2
> momentsat42
[1] 116
> momentsat43=skewness*(variance^(3/2)) + 3 * mean* momentsat42 - 2 * mean^3
> momentsat43
[1] 1544
> momentsat44=kurtosis* (variance^2) + (4 * mean*momentsat43) - (6 * mean^2 * momentsat42) + 3*mean^4
> momentsat44
[1] 23184
```
<div style="text-align: center">⁂</div>
###### Information
- date: 2025.2.11
- time: 21:21