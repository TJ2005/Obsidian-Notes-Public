---
Title: "Probability distribution in R studio"
Status: 
marker: 
tags: 
Date: "2025.03.12"
Time: "16:50"
---
# Discrete & Continuous Probability distribution in R studio

## **Modules Required**

To work with discrete probability distributions in R, the following packages are required:

- `e1071` – Provides various statistical and machine learning functions.
- `distr` – Used for handling probability distributions.

The installation and removing packages can be done with GUI as well.
### **Installing Required Packages**

To install the required packages, run:

```r
install.packages("e1071")
install.packages("distr")
```

### **Loading Packages**

After installation, load the packages using:

```r
library(e1071)
library(distr)
```

### **Removing Packages (After Use)**

To unload a package from memory:

```r
detach("stats", unload = TRUE)
```

---

## **Concepts Covered**

- Working with **discrete probability distributions**.
- Calculating **probability mass function (PMF)**.
- Finding the **distribution function**, **quantiles**, and generating **random samples**.
- Computing **expected values**.
- **Solving probability equations** using root-finding methods.
- **Transforming random variables**.

---

## **Functions Used**

### **Discrete Probability Distribution Functions**

The `distr` package provides the following functions to work with discrete data:

|Function|Description|
|---|---|
|`ddiscrete(x, probs, values = 1:length(probs))`|Computes the probability mass function (PMF) of a discrete distribution.|
|`pdiscrete(q, probs, values = 1:length(probs))`|Computes the cumulative distribution function (CDF).|
|`qdiscrete(p, probs, values = 1:length(probs))`|Computes the quantile function (inverse of CDF).|
|`rdiscrete(n, probs, values = 1:length(probs), ...)`|Generates `n` random samples from a discrete distribution.|

### **Parameters**

|Parameter|Description|
|---|---|
|`x`, `q`|A vector or array of quantiles.|
|`p`|A vector or array of probabilities.|
|`n`|The number of observations (random samples to generate).|
|`probs`|The probability values associated with each outcome. The sum must be 1.|
|`values`|The possible values of the discrete distribution.|
|`...`|Additional arguments (ignored for compatibility).|

These functions allow us to work with discrete distributions where the probability of each value is proportional to the `probs` parameter.

---

## **Example 1: Creating a Discrete Probability Distribution**

To define a discrete probability distribution and compute the expected value:

```r
X <- c(0, 1, 2, 3, 4)  # Possible values
P <- c(0.1, 0.15, 0.2, 0.55)  # Corresponding probabilities

# Compute XP (value * probability)
XP <- X * P

# Create a data frame for better visualization
data.frame(X, P, XP)

# Compute the expected value (mean)
mean_value <- sum(XP)
print(mean_value)
```

---

## **Example 2: Finding a Missing Probability Value**

To find a missing probability in a probability distribution, convert it into a root-finding problem.

For example, to solve `0.6 + 6x = 1` for `x`:

```r
f <- function(x) (0.6 + 6*x - 1)
root_value <- uniroot(f, lower=0, upper=1)$root
print(root_value)
```

---

## **Example 3: Computing the Distribution of a Transformed Variable**

If `Y = g(X)`, we can compute the probability distribution of `Y` using transformations.

For instance, if `Y = 2X + 1` for a given discrete distribution, we can derive its probabilities accordingly.

---

# References
- This note is AI Generated with human modifications.

###### Information
- date: 2025.03.12
- time: 16:50