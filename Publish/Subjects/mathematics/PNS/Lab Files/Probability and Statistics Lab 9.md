---
Title: Probability and Statistics Lab 10
Status: 
marker: 
tags: 
Date: 2025.03.25
Time: 12:27
---
# Questions & Answers

## Question 1
```R
# Sample data
mu = 1.5          # Population mean
x_bar = 1.52      # Sample mean
sigma = 0.2        # Standard deviation
n = 100            # Sample size
alpha = 0.05       # Level of significance

# Z-test statistic
z_stat = (x_bar - mu) / (sigma / sqrt(n))
print(paste("Z-statistic:", z_stat))

# P-value for two-tailed test
p_value = 2 * pnorm(-abs(z_stat))
print(paste("P-value:", p_value))

# Decision
if (p_value < alpha) {
  print("Reject Null Hypothesis: The machine is NOT working to the standards set.")
} else {
  print("Fail to Reject Null Hypothesis: The machine is working to the Standards set.")
}

```

```bash
1] "Z-statistic: 1"
> > # P-value for two-tailed test
> p_value = 2 * pnorm(-abs(z_stat))
> print(paste("P-value:", p_value))
[1] "P-value: 0.317310507862914"
> > # Decision
> if (p_value < alpha) {
+ print("Reject Null Hypothesis: The machine is NOT working to the standards set.")
+ } else {
+ print("Fail to Reject Null Hypothesis: The machine is working to the Standards set.")
+ }
[1] "Fail to Reject Null Hypothesis: The machine is working to the Standards set."
```

## Question 2

```R
# Sample data
x1 <- 72        # Mean of boys
s1 <- 8         # SD of boys
n1 <- 32        # Sample size of boys

x2 <- 70        # Mean of girls
s2 <- 6         # SD of girls
n2 <- 36        # Sample size of girls

alpha <- 0.01   # Level of significance

# t-test statistic
t_stat <- (x1 - x2) / sqrt((s1^2 / n1) + (s2^2 / n2))
print(paste("t-statistic:", t_stat))

# Degrees of freedom (Welch-Satterthwaite)
df <- ((s1^2 / n1 + s2^2 / n2)^2) /
      ((s1^2 / n1)^2 / (n1 - 1) + (s2^2 / n2)^2 / (n2 - 1))
print(paste("Degrees of freedom:", df))

# P-value (two-tailed test)
p_value <- 2 * pt(-abs(t_stat), df)
print(paste("P-value:", p_value))

# Decision
if (p_value < alpha) {
  print("Reject Null Hypothesis: Boys and girls perform differently.")
} else {
  print("Fail to Reject Null Hypothesis: Boys and girls perform equally.")
}

```

**Output**
```bash
R version 4.4.2 (2024-10-31 ucrt) -- "Pile of Leaves"
Copyright (C) 2024 The R Foundation for Statistical Computing
Platform: x86_64-w64-mingw32/x64

R is free software and comes with ABSOLUTELY NO WARRANTY.
You are welcome to redistribute it under certain conditions.
Type 'license()' or 'licence()' for distribution details.

  Natural language support but running in an English locale

R is a collaborative project with many contributors.
Type 'contributors()' for more information and
'citation()' on how to cite R or R packages in publications.

Type 'demo()' for some demos, 'help()' for on-line help, or
'help.start()' for an HTML browser interface to help.
Type 'q()' to quit R.

> # Sample data
> mu = 1.5          # Population mean
> x_bar = 1.52      # Sample mean
> sigma = 0.2        # Standard deviation
> n = 100            # Sample size
> alpha = 0.05       # Level of significance
> > # Z-test statistic
> z_stat = (x_bar - mu) / (sigma / sqrt(n))
> print(paste("Z-statistic:", z_stat))
[1] "Z-statistic: 1"
> > # P-value for two-tailed test
> p_value = 2 * pnorm(-abs(z_stat))
> print(paste("P-value:", p_value))
[1] "P-value: 0.317310507862914"
> > # Decision
> if (p_value < alpha) {
+ print("Reject Null Hypothesis: The machine is NOT working to the standards set.")
+ } else {
+ print("Fail to Reject Null Hypothesis: The machine is working to the Standards set.")
+ }
[1] "Fail to Reject Null Hypothesis: The machine is working to the Standards set."
> # Sample data
> x1 <- 72        # Mean of boys
> s1 <- 8         # SD of boys
> n1 <- 32        # Sample size of boys
> > x2 <- 70        # Mean of girls
> s2 <- 6         # SD of girls
> n2 <- 36        # Sample size of girls
> > alpha <- 0.01   # Level of significance
> > # t-test statistic
> t_stat <- (x1 - x2) / sqrt((s1^2 / n1) + (s2^2 / n2))
> print(paste("t-statistic:", t_stat))
[1] "t-statistic: 1.15470053837925"
> > # Degrees of freedom (Welch-Satterthwaite)
> df <- ((s1^2 / n1 + s2^2 / n2)^2) /
+ ((s1^2 / n1)^2 / (n1 - 1) + (s2^2 / n2)^2 / (n2 - 1))
> print(paste("Degrees of freedom:", df))
[1] "Degrees of freedom: 57.1052631578947"
> > # P-value (two-tailed test)
> p_value <- 2 * pt(-abs(t_stat), df)
> print(paste("P-value:", p_value))
[1] "P-value: 0.253022304616441"
> > # Decision
> if (p_value < alpha) {
+ print("Reject Null Hypothesis: Boys and girls perform differently.")
+ } else {
+ print("Fail to Reject Null Hypothesis: Boys and girls perform equally.")
+ }
[1] "Fail to Reject Null Hypothesis: Boys and girls perform equally."
```
## Question 3

```R
# Quality Control Analysis for Plastic Golf Tees
# Hypothesis Testing to Determine if Production Process is Satisfactory

# Input the data
tee_weights <- c(0.253, 0.253, 0.249, 0.247, 0.252, 0.253, 0.250, 0.251, 0.253, 0.248,
                0.254, 0.254, 0.256, 0.251, 0.251, 0.253, 0.254, 0.253, 0.251, 0.253,
                0.256, 0.256, 0.255, 0.248, 0.252, 0.254, 0.251, 0.253, 0.251, 0.250,
                0.253, 0.255, 0.253, 0.254, 0.252, 0.256, 0.252, 0.251, 0.255, 0.253)

# Calculate basic statistics
n <- length(tee_weights)
sample_mean <- mean(tee_weights)
sample_sd <- sd(tee_weights)
target_mean <- 0.256

# Display basic statistics
cat("Sample size:", n, "\n")
cat("Sample mean:", sample_mean, "\n")
cat("Sample standard deviation:", sample_sd, "\n")
cat("Target mean:", target_mean, "\n")

# a) Null and Alternative Hypotheses
cat("\na) Hypotheses:\n")
cat("Null Hypothesis (H0): μ = 0.256 (The production process is performing satisfactorily)\n")
cat("Alternative Hypothesis (Ha): μ ≠ 0.256 (The production process is performing unsatisfactorily)\n")

# b) Calculate the test statistic (t-score)
standard_error <- sample_sd / sqrt(n)
t_stat <- (sample_mean - target_mean) / standard_error
cat("\nb) Test statistic (t-score):", t_stat, "\n")

# c) Determine the rejection region
alpha <- 0.05
critical_value <- qt(1 - alpha/2, df = n - 1)
cat("\nc) Rejection Region:\n")
cat("Critical values at alpha =", alpha, ":", -critical_value, "and", critical_value, "\n")
cat("Rejection region: t <", -critical_value, "or t >", critical_value, "\n")

# Determine if we reject the null hypothesis
p_value <- 2 * pt(-abs(t_stat), df = n - 1)
cat("\nAdditional Analysis:\n")
cat("p-value:", p_value, "\n")

if(abs(t_stat) > critical_value) {
  cat("Decision: Reject H0 (The production process is performing unsatisfactorily)\n")
} else {
  cat("Decision: Fail to reject H0 (The production process may be performing satisfactorily)\n")
}

# Perform one-sample t-test using R's built-in function
t_test_result <- t.test(tee_weights, mu = target_mean)
cat("\nComplete t-test results:\n")
print(t_test_result)

# Create visualizations
par(mfrow=c(2,1))  # Set up a 2x1 plotting area

# Histogram
hist(tee_weights, breaks = 10, main = "Distribution of Golf Tee Weights", 
     xlab = "Weight (ounces)", col = "lightblue", border = "white")
abline(v = target_mean, col = "red", lwd = 2, lty = 2)
abline(v = sample_mean, col = "blue", lwd = 2)
legend("topright", legend = c("Target Mean (0.256)", "Sample Mean"), 
       col = c("red", "blue"), lty = c(2, 1), lwd = 2)

# Boxplot
boxplot(tee_weights, main = "Boxplot of Golf Tee Weights", 
        ylab = "Weight (ounces)", col = "lightgreen")
abline(h = target_mean, col = "red", lwd = 2, lty = 2)
text(1.3, target_mean, "Target Mean (0.256)", col = "red", pos = 4)

# Reset plotting area
par(mfrow=c(1,1))

```

```bash
Sample size: 40 
> cat("Sample mean:", sample_mean, "\n")
Sample mean: 0.252475 
> cat("Sample standard deviation:", sample_sd, "\n")
Sample standard deviation: 0.002230183 
> cat("Target mean:", target_mean, "\n")
Target mean: 0.256 
> > # a) Null and Alternative Hypotheses
> cat("\na) Hypotheses:\n")
a) Hypotheses:
> cat("Null Hypothesis (H0): μ = 0.256 (The production process is performing satisfactorily)\n")
Null Hypothesis (H0): μ = 0.256 (The production process is performing satisfactorily)
> cat("Alternative Hypothesis (Ha): μ ≠ 0.256 (The production process is performing unsatisfactorily)\n")
Alternative Hypothesis (Ha): μ ≠ 0.256 (The production process is performing unsatisfactorily)
> > # b) Calculate the test statistic (t-score)
> standard_error <- sample_sd / sqrt(n)
> t_stat <- (sample_mean - target_mean) / standard_error
> cat("\nb) Test statistic (t-score):", t_stat, "\n")
b) Test statistic (t-score): -9.996513 
> > # c) Determine the rejection region
> alpha <- 0.05
> critical_value <- qt(1 - alpha/2, df = n - 1)
> cat("\nc) Rejection Region:\n")
c) Rejection Region:
> cat("Critical values at alpha =", alpha, ":", -critical_value, "and", critical_value, "\n")
Critical values at alpha = 0.05 : -2.022691 and 2.022691 
> cat("Rejection region: t <", -critical_value, "or t >", critical_value, "\n")
Rejection region: t < -2.022691 or t > 2.022691 
> > # Determine if we reject the null hypothesis
> p_value <- 2 * pt(-abs(t_stat), df = n - 1)
> cat("\nAdditional Analysis:\n")
Additional Analysis:
> cat("p-value:", p_value, "\n")
p-value: 2.58434e-12 
> > if(abs(t_stat) > critical_value) {
+ cat("Decision: Reject H0 (The production process is performing unsatisfactorily)\n")
+ } else {
+ cat("Decision: Fail to reject H0 (The production process may be performing satisfactorily)\n")
+ }
Decision: Reject H0 (The production process is performing unsatisfactorily)
> > # Perform one-sample t-test using R's built-in function
> t_test_result <- t.test(tee_weights, mu = target_mean)
> cat("\nComplete t-test results:\n")
Complete t-test results:
> print(t_test_result)
	One Sample t-test

data:  tee_weights
t = -9.9965, df = 39, p-value = 2.584e-12
alternative hypothesis: true mean is not equal to 0.256
95 percent confidence interval:
 0.2517618 0.2531882
sample estimates:
mean of x 
 0.252475 

> > # Create visualizations
> par(mfrow=c(2,1))  # Set up a 2x1 plotting area
> > # Histogram
> hist(tee_weights, breaks = 10, main = "Distribution of Golf Tee Weights", 
+ xlab = "Weight (ounces)", col = "lightblue", border = "white")
> abline(v = target_mean, col = "red", lwd = 2, lty = 2)
> abline(v = sample_mean, col = "blue", lwd = 2)
> legend("topright", legend = c("Target Mean (0.256)", "Sample Mean"), 
+ col = c("red", "blue"), lty = c(2, 1), lwd = 2)
> > # Boxplot
> boxplot(tee_weights, main = "Boxplot of Golf Tee Weights", 
+ ylab = "Weight (ounces)", col = "lightgreen")
> abline(h = target_mean, col = "red", lwd = 2, lty = 2)
> text(1.3, target_mean, "Target Mean (0.256)", col = "red", pos = 4)
> > # Reset plotting area
> par(mfrow=c(1,1))
```

![](https://i.imgur.com/pC2e5g8.png)
# References

###### Information
- date: 2025.03.25
- time: 12:27