---
Title: Probability & Statistics Lab 4
Status: 
marker:
  - "[[Probability and Statistics (PNS)]]"
tags: 
Date: 2025.01.31
Time: 17:26
---


# Classwork

### Performing Classwork Example 1

```R
# Load the necessary library to read CSV files
# and perform statistical analysis
library(modeest)

# Specify the file path to your CSV file
# You can use double backslashes or forward slashes
# to avoid the issue with escape sequences
cgf <- read.csv("C:\\Users\\Sumit\\Downloads\\CardioGoodFitness.csv")

# Alternatively, you can use forward slashes
# cgf <- read.csv("C:/Users/Sumit/Downloads/CardioGoodFitness.csv")

# Calculate the mean (average) of the Age column
# This gives us an idea of the central tendency of the ages in the dataset
m <- mean(cgf$Age)

# Calculate the mode of the Age column
# The mode is the value that appears most frequently in the data
# We're using the 'mfv' function from the modeest package
m1 <- mfv(cgf$Age)

# Calculate the median of the Age column
# The median is the middle value when the data is sorted in ascending order
# It is less affected by outliers compared to the mean
m2 <- median(cgf$Age)

# Find the maximum age in the dataset
# This tells us the highest age recorded
m3 <- max(cgf$Age)

# Find the minimum age in the dataset
# This tells us the lowest age recorded
m4 <- min(cgf$Age)

# Calculate the range of ages
# The range is the difference between the maximum and minimum values
# It gives us a measure of the spread of the data
range <- m3 - m4

# Calculate the variance of the Age column
# Variance measures the degree of spread in the data
# A higher variance indicates that the data points are more spread out from the mean
m5 <- var(cgf$Age)

```

```R

```bash
 # Load the necessary library to read CSV files
> # and perform statistical analysis
> library(modeest)
> > # Specify the file path to your CSV file
> # You can use double backslashes or forward slashes
> # to avoid the issue with escape sequences
> cgf <- read.csv("C:\\Users\\Sumit\\Downloads\\CardioGoodFitness.csv")
> > # Alternatively, you can use forward slashes
> # cgf <- read.csv("C:/Users/Sumit/Downloads/CardioGoodFitness.csv")
> > # Calculate the mean (average) of the Age column
> # This gives us an idea of the central tendency of the ages in the dataset
> m <- mean(cgf$Age)
> > # Calculate the mode of the Age column
> # The mode is the value that appears most frequently in the data
> # We're using the 'mfv' function from the modeest package
> m1 <- mfv(cgf$Age)
> > # Calculate the median of the Age column
> # The median is the middle value when the data is sorted in ascending order
> # It is less affected by outliers compared to the mean
> m2 <- median(cgf$Age)
> > # Find the maximum age in the dataset
> # This tells us the highest age recorded
> m3 <- max(cgf$Age)
> > # Find the minimum age in the dataset
> # This tells us the lowest age recorded
> m4 <- min(cgf$Age)
> > # Calculate the range of ages
> # The range is the difference between the maximum and minimum values
> # It gives us a measure of the spread of the data
> range <- m3 - m4
> > # Calculate the variance of the Age column
> # Variance measures the degree of spread in the data
> # A higher variance indicates that the data points are more spread out from the mean
> m5 <- var(cgf$Age)
```


### Performing Classwork Example 2
```R
x=c(0:3)
p=c(0.1,0.2,0.3,0.4)
m0=1
m1=sum(x*p)
m2=sum(x^2*p)
m3=sum(x^3*p)
m4=sum(x^4*p)
m=c(m0,m1,m2,m3,m4)
m
cen1=raw2central(m)
central2raw(cen1,m1)
```

```R
> x=c(0:3)
> p=c(0.1,0.2,0.3,0.4)
> m0=1
> m1=sum(x*p)
> m2=sum(x^2*p)
> m3=sum(x^3*p)
> m4=sum(x^4*p)
> m=c(m0,m1,m2,m3,m4)
> m
[1]  1.0  2.0  5.0 13.4 37.4
> cen1=raw2central(m)
> central2raw(cen1,m1) 
[1]  1.0  2.0  5.0 13.4 37.4
```
---
# Questions
## Question 1

A random variable $X$ has the following probability distribution:

$$
\begin{array}{c|ccc}
X & 0 & 1 & 2 \\
\hline
P(X=x) & \frac{1}{3} & \frac{1}{3} & \frac{1}{3} \\
\end{array}
$$

Find the moment generating function, the first four raw moments, and the first four central moments. Write an R program for the above problem.

```R
# Define the values and probabilities
x <- c(0, 1, 2)
p <- c(1/3, 1/3, 1/3)

# Compute the Moment Generating Function (MGF) at t = 1 using vectorized operations
mgf_t1 <- sum(p * exp(1 * x))
cat("Moment Generating Function at t = 1:", mgf_t1, "\n\n")

# Compute the first four raw moments using vectorized operations
raw1 <- sum(p * x)       # First raw moment (mean)
raw2 <- sum(p * (x^2))     # Second raw moment
raw3 <- sum(p * (x^3))     # Third raw moment
raw4 <- sum(p * (x^4))     # Fourth raw moment

cat("First Raw Moment (Mean):", raw1, "\n")
cat("Second Raw Moment:", raw2, "\n")
cat("Third Raw Moment:", raw3, "\n")
cat("Fourth Raw Moment:", raw4, "\n\n")

# Compute the first four central moments using vectorized operations
cen1 <- sum(p * ((x - raw1)^1))  # First central moment (should be 0)
cen2 <- sum(p * ((x - raw1)^2))  # Second central moment (variance)
cen3 <- sum(p * ((x - raw1)^3))  # Third central moment
cen4 <- sum(p * ((x - raw1)^4))  # Fourth central moment

cat("First Central Moment:", cen1, "\n")
cat("Second Central Moment:", cen2, "\n")
cat("Third Central Moment:", cen3, "\n")
cat("Fourth Central Moment:", cen4, "\n")
```

```bash
> 
> clear
Error: object 'clear' not found
> # Define the values and probabilities
> x <- c(0, 1, 2)
> p <- c(1/3, 1/3, 1/3)
> > # Compute the Moment Generating Function (MGF) at t = 1 using vectorized operations
> mgf_t1 <- sum(p * exp(1 * x))
> cat("Moment Generating Function at t = 1:", mgf_t1, "\n\n")
Moment Generating Function at t = 1: 3.702446 

> > # Compute the first four raw moments using vectorized operations
> raw1 <- sum(p * x)       # First raw moment (mean)
> raw2 <- sum(p * (x^2))     # Second raw moment
> raw3 <- sum(p * (x^3))     # Third raw moment
> raw4 <- sum(p * (x^4))     # Fourth raw moment
> > cat("First Raw Moment (Mean):", raw1, "\n")
First Raw Moment (Mean): 1 
> cat("Second Raw Moment:", raw2, "\n")
Second Raw Moment: 1.666667 
> cat("Third Raw Moment:", raw3, "\n")
Third Raw Moment: 3 
> cat("Fourth Raw Moment:", raw4, "\n\n")
Fourth Raw Moment: 5.666667 

> > # Compute the first four central moments using vectorized operations
> cen1 <- sum(p * ((x - raw1)^1))  # First central moment (should be 0)
> cen2 <- sum(p * ((x - raw1)^2))  # Second central moment (variance)
> cen3 <- sum(p * ((x - raw1)^3))  # Third central moment
> cen4 <- sum(p * ((x - raw1)^4))  # Fourth central moment
> > cat("First Central Moment:", cen1, "\n")
First Central Moment: 0 
> cat("Second Central Moment:", cen2, "\n")
Second Central Moment: 0.6666667 
> cat("Third Central Moment:", cen3, "\n")
Third Central Moment: 0 
> cat("Fourth Central Moment:", cen4, "\n")
Fourth Central Moment: 0.666666
```


---

## Question 2

The first three moments of the distribution about the value 3 of the random variable are 2, 10, and -30 respectively. Find the mean, variance, and skewness. Write an R program for the above problem.

```r
## Q2
## K044 Sumit Pandey
# Given moments about the value 3
moment1_about_3 <- 2
moment2_about_3 <- 10
moment3_about_3 <- -30

# Calculate the mean
mean <- moment1_about_3 + 3

# Calculate the variance
variance <- moment2_about_3

# Calculate the skewness
skewness <- moment3_about_3 / (variance^(3/2))

# Output the results
cat("Mean:", mean, "\n")
cat("Variance:", variance, "\n")
cat("Skewness:", skewness, "\n")
```

```R
> ## Q2
> ## K044 Sumit Pandey
> # Given moments about the value 3
> moment1_about_3 <- 2
> moment2_about_3 <- 10
> moment3_about_3 <- -30
> > # Calculate the mean
> mean <- moment1_about_3 + 3
> > # Calculate the variance
> variance <- moment2_about_3
> > # Calculate the skewness
> skewness <- moment3_about_3 / (variance^(3/2))
> > # Output the results
> cat("Mean:", mean, "\n")
Mean: 5 
> cat("Variance:", variance, "\n")
Variance: 10 
> cat("Skewness:", skewness, "\n")
Skewness: -0.9486833
```


## Question 3

A random variable $X$ has the probability distribution:

$$
P(X=x) = \begin{cases}
\frac{1}{8} & \text{if } x = 0 \\
\frac{3}{8} & \text{if } x = 1 \\
\frac{3}{8} & \text{if } x = 2 \\
\frac{1}{8} & \text{if } x = 3 \\
\end{cases}
$$

Find the moment generating function of $X$ and then find the mean and variance. Write an R program for the above problem.

```R
## Q3
# Define the values and probabilities
X <- c(0, 1, 2, 3)
P <- c(1/8, 3/8, 3/8, 1/8)

# Moment Generating Function (MGF)
t <- 1  # Example value for t
mgf <- sum(P * exp(t * X))

# Calculate the mean (expected value)
mean_X <- sum(X * P)

# Calculate the second raw moment
second_raw_moment <- sum((X^2) * P)

# Calculate the variance
variance_X <- second_raw_moment - (mean_X^2)

# Output the results
cat("Moment Generating Function at t=1:", mgf, "\n")
cat("Mean (Expected Value):", mean_X, "\n")
cat("Variance:", variance_X, "\n")

```

```bash
> # K044
> ## Q3
> # Define the values and probabilities
> X <- c(0, 1, 2, 3)
> P <- c(1/8, 3/8, 3/8, 1/8)
> > # Moment Generating Function (MGF)
> t <- 1  # Example value for t
> mgf <- sum(P * exp(t * X))
> > # Calculate the mean (expected value)
> mean_X <- sum(X * P)
> > # Calculate the second raw moment
> second_raw_moment <- sum((X^2) * P)
> > # Calculate the variance
> variance_X <- second_raw_moment - (mean_X^2)
> > # Output the results
> cat("Moment Generating Function at t=1:", mgf, "\n")
Moment Generating Function at t=1: 6.425944 
> cat("Mean (Expected Value):", mean_X, "\n")
Mean (Expected Value): 1.5 
> cat("Variance:", variance_X, "\n")
Variance: 0.75
```
## Question 4

Find the first four moments about the mean of the random variable $X$ whose probability mass function is given by:

$$
\begin{array}{c|ccc}
X & -2 & 3 & 1 \\
\hline
P(X) & \frac{1}{3} & \frac{1}{2} & \frac{1}{6} \\
\end{array}
$$

Write an R program for the above problem.

```R
# K044
# Define the values and probabilities
X <- c(-2, 3, 1)
P <- c(1/3, 1/2, 1/6)

# Calculate the mean (first moment)
mean_X <- sum(X * P)

# Calculate the first four moments about the mean
moment1 <- sum((X - mean_X)^1 * P)  # Should be 0
moment2 <- sum((X - mean_X)^2 * P)  # Variance
moment3 <- sum((X - mean_X)^3 * P)  # Skewness
moment4 <- sum((X - mean_X)^4 * P)  # Kurtosis

# Output the results
cat("Mean:", mean_X, "\n")
cat("First Moment about the Mean:", moment1, "\n")
cat("Second Moment about the Mean :", moment2, "\n")
cat("Third Moment about the Mean:", moment3, "\n")
cat("Fourth Moment about the Mean :", moment4, "\n")

```

```bash
> # Calculate the first four moments about the mean
> moment1 <- sum((X - mean_X)^1 * P)  # Should be 0
> # K044
> # Define the values and probabilities
> X <- c(-2, 3, 1)
> P <- c(1/3, 1/2, 1/6)
> > # Calculate the mean (first moment)
> mean_X <- sum(X * P)
> > # Calculate the first four moments about the mean
> moment1 <- sum((X - mean_X)^1 * P)  # Should be 0
> moment2 <- sum((X - mean_X)^2 * P)  # Variance
> moment3 <- sum((X - mean_X)^3 * P)  # Skewness
> moment4 <- sum((X - mean_X)^4 * P)  # Kurtosis
> > # Output the results
> cat("Mean:", mean_X, "\n")
Mean: 1 
> cat("First Moment about the Mean:", moment1, "\n")
First Moment about the Mean: 0 
> cat("Second Moment about the Mean :", moment2, "\n")
Second Moment about the Mean : 5 
> cat("Third Moment about the Mean:", moment3, "\n")
Third Moment about the Mean: -5 
> cat("Fourth Moment about the Mean :", moment4, "\n")
Fourth Moment about the Mean : 35
```
# Questions handwritten
### Question1
<div style="display: flex; justify-content: center; align-items: center; height: 100%; overflow: hidden;">
    <img src="https://i.imgur.com/kgPeN9e.jpeg" style="width: 40vw; transform: rotate(0deg);" />
</div>
# Question 2

<div style="display: flex; justify-content: center; align-items: center; height: 100%; overflow: hidden;">
    <img src="https://i.imgur.com/eAFA0kM.jpeg" style="width: 40vw; transform: rotate(0deg);" />
</div>
# Question 3
<div style="display: flex; justify-content: center; align-items: center; height: 100%; overflow: hidden;">
    <img src="https://i.imgur.com/UYaYnoD.jpeg" style="width: 40vw; transform: rotate(0deg);" />
</div>
<div style="display: flex; justify-content: center; align-items: center; height: 100%; overflow: hidden;">
    <img src="https://i.imgur.com/Y6lL48y.jpeg" style="width: 40vw; transform: rotate(0deg);" />
</div>
<div style="display: flex; justify-content: center; align-items: center; height: 100%; overflow: hidden;">
    <img src="https://i.imgur.com/9283btk.jpeg" style="width: 40vw; transform: rotate(0deg);" />
</div>
# Question 4
<div style="display: flex; justify-content: center; align-items: center; height: 100%; overflow: hidden;">
    <img src="https://i.imgur.com/wWfa2ag.jpeg" style="width: 40vw; transform: rotate(0deg);" />
</div>
<div style="display: flex; justify-content: center; align-items: center; height: 100%; overflow: hidden;">
    <img src="https://i.imgur.com/XsOktkz.jpeg" style="width: 40vw; transform: rotate(0deg);" />
</div>

# References

###### Information
- date: 2025.01.31
- time: 17:26