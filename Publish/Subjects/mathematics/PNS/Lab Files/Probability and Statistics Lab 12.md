---
Title: "Probability and Statistics Lab 10"
Status: 
marker: 
tags: 
Date: "2025.03.25"
Time: "13:09"
---
# Hypothesis Small Sample

## Question 1
The annual rainfall at a certain place is normally distributed with mean 30. If the rainfall during the past 8 years are 
31.1, 30.7, 24.3, 28.1, 27.9, 32.2, 25.4 and 29.1,
can we conclude that average rainfall during the past 8 years is less than the normal rainfall? Write R program for above problem.

$\mu=30$
$\alpha=0.05$

```R
# Sample data
rainfall <- c(31.1, 30.7, 24.3, 28.1, 27.9, 32.2, 25.4, 29.1)
mu <- 30           # Population mean
alpha <- 0.05       # Level of significance

# t-test
t_test <- t.test(rainfall, mu = mu, alternative = "less")

# Display results
print(t_test)

# Decision
if (t_test$p.value < alpha) {
  print("Reject Null Hypothesis: The average rainfall is less than the normal rainfall.")
} else {
  print("Fail to Reject Null Hypothesis: The average rainfall is NOT significantly less than the normal rainfall.")
}

```

## Question 2
Two random samples gave the following data:

| **Sample** | **Size $n$** | **Mean $\bar{X}$** | **Variance $s^2$** |
| ---------- | ------------ | ------------------ | ------------------ |
| **1**      | 16           | 440                | 40                 |
| **2**      | 25           | 460                | 42                 |
Can we conclude that the means of the two samples differ Significantly?
### Solution
No significance given $\alpha = 0.05$ 

**Hypothesis:**
- $H_0: \mu_1 = \mu_2$ → The means of the two samples are **equal**.
- $H_1: \mu_1 \neq \mu_2$ → The means of the two samples **differ significantly** (**two-tailed test**).

```R
# Given data
n1 <- 16
n2 <- 25
mean1 <- 440
mean2 <- 460
var1 <- 40
var2 <- 42
alpha <- 0.05

# Calculate the pooled variance
pooled_var <- ((n1-1)*var1 + (n2-1)*var2) / (n1 + n2 - 2)

# Calculate the t-statistic
t_stat <- (mean1 - mean2) / sqrt(pooled_var * (1/n1 + 1/n2))

# Calculate degrees of freedom
df <- n1 + n2 - 2

# Calculate critical t-value for two-tailed test
t_critical <- qt(1 - alpha/2, df)

# Calculate p-value
p_value <- 2 * pt(-abs(t_stat), df)

# Print results
cat("t-statistic:", t_stat, "\n")
cat("Degrees of freedom:", df, "\n")
cat("Critical t-value (two-tailed):", t_critical, "\n")
cat("p-value:", p_value, "\n")

# Decision
if(abs(t_stat) > t_critical) {
  cat("Reject H0: The means differ significantly.\n")
} else {
  cat("Fail to reject H0: No significant difference between means.\n")
}

# Alternative using t.test function
result <- t.test(x = NULL, y = NULL, 
                 alternative = "two.sided", 
                 mu = 0, paired = FALSE, 
                 var.equal = TRUE,
                 conf.level = 0.95,
                 data.frame(
                   x = rep(mean1, n1),
                   y = rep(mean2, n2),
                   var.x = rep(var1, n1),
                   var.y = rep(var2, n2)
                 ))

# Print t.test results
print(result)

```

**Output:**
```bash
[1] "Accept Null Hypothesis."
Reject H0: The means differ significantly.
t-statistic: -9.728757 
> cat("Degrees of freedom:", df, "\n")
Degrees of freedom: 39 
> cat("Critical t-value (two-tailed):", t_critical, "\n")
Critical t-value (two-tailed): 2.022691 
> cat("p-value:", p_value, "\n")
p-value: 5.542818e-12
```
## Question 3
The following data relate to the marks obtained by 11 students in 2 tests, one held at the beginning of a year and the other at the end of the year after intensive coaching.
Do the data indicate that the students have benefited by coaching? Write R program for above problem.
### **Given Data**

|**Student**|**Test 1 (Before Coaching)**|**Test 2 (After Coaching)**|
|---|---|---|
|1|55|63|
|2|60|70|
|3|65|70|
|4|75|81|
|5|49|54|
|6|25|29|
|7|18|21|
|8|30|38|
|9|35|32|
|10|54|50|
|11|61|70|
|12|72|80|
## Solution
### **Hypothesis:**
- $H_0: \mu_d = 0$ → **No significant difference** in scores before and after coaching.
- $H_1: \mu_d > 0$→ **Significant improvement** in scores after coaching (**right-tailed test**). 

### Data


```R
# Given data
test1 <- c(55, 60, 65, 75, 49, 25, 18, 30, 35, 54, 61, 72)  # Before coaching
test2 <- c(63, 70, 70, 81, 54, 29, 21, 38, 32, 50, 70, 80)  # After coaching

# Paired t-test (right-tailed)
result <- t.test(test2, test1, paired = TRUE, alternative = "greater", conf.level = 0.95)

print(result)
```

**Output**
```bash
Paired t-test

data:  test2 and test1
t = 3.8178, df = 11, p-value = 0.001427
alternative hypothesis: true mean difference is greater than 0
95 percent confidence interval:
 2.603905      Inf
sample estimates:
mean difference 
       4.916667
```

---
### **Question 4**
In a test given to two groups of students, the marks obtained were as follows:
#### **First Group:**
$18, 20, 36, 50, 49, 36, 34, 49, 41$
#### **Second Group:**
$29, 28, 26, 35, 30, 44, 46$
Examine whether there is a **significant difference** between the means of marks secured by students of the above two groups.
### **Solution**
#### **Hypothesis:**
- $H_0: \mu_1 = \mu_2$ → The means of the two groups are **equal**.
- $H_1: \mu_1 \neq \mu_2$ → The means of the two groups **differ significantly** (**two-tailed test**).
### **R Program**
```r
# Data for the two groups
group1 <- c(18, 20, 36, 50, 49, 36, 34, 49, 41)
group2 <- c(29, 28, 26, 35, 30, 44, 46)

# Two-sample t-test (two-tailed)
result <- t.test(group1, group2, var.equal = TRUE, alternative = "two.sided")

# Display result
print(result)
```

**Output:**
```bash
Two Sample t-test

data:  group1 and group2
t = 0.57131, df = 14, p-value = 0.5768
alternative hypothesis: true difference in means is not equal to 0
95 percent confidence interval:
 -8.262417 14.262417
sample estimates:
mean of x mean of y 
       37        34
```

# References

###### Information
- date: 2025.03.25
- time: 13:09