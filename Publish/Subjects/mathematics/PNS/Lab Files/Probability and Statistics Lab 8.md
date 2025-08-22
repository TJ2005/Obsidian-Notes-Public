---
Title: Probability and Statistics Lab 8
Status: 
marker: 
tags: 
Date: 2025-03-11
Time: 22:06
---
# Probability and Statistics Lab 8
## Questions

### Question 1

```r
#Q1 
X_calcutta <- 70
r <- -0.75
mean_X <- 65
mean_Y <- 67
sd_X <- 2.5
sd_Y <- 3.5
Y_mumbai <- mean_Y + r * (sd_Y / sd_X) * (X_calcutta - mean_X)
Y_mumbai
```

**Output:**  
```bash
 #Q1 
> X_calcutta <- 70
> r <- -0.75
> mean_X <- 65
> mean_Y <- 67
> sd_X <- 2.5
> sd_Y <- 3.5
> Y_mumbai <- mean_Y + r * (sd_Y / sd_X) * (X_calcutta - mean_X)
> Y_mumbai
[1] 61.75
```

---

### Question 

```r
#Q2 
x <- c(25, 27.5, 32.5, 35, 45)
y <- c(105, 125, 140, 140, 150)
corr <- cor(x, y)
corr
```

**Output:**  
```bash
> #Q2 
> x <- c(25, 27.5, 32.5, 35, 45)
> y <- c(105, 125, 140, 140, 150)
> corr <- cor(x, y)
> corr
[1] 0.8834641
```

---

### Question 

```r
##Q4 
data(Auto)
model_auto <- lm(mpg ~ . - name, data = Auto)
summary(model_auto)
```

**Output:**  ![](https://i.imgur.com/7nxWBJd.png)

---

### Question 5

```r
#Q5 
data(Carseats)
model_carseats <- lm(Sales ~ Price + Urban + US, data = Carseats)
summary(model_carseats)
```

**Output:**  
![](https://i.imgur.com/zJZfN1I.png)


---

### Question 6

```r
#Q6 
A <- matrix(c(1, 6, 3, 2), nrow=2, byrow=TRUE)
B <- c(6, 10)
means <- solve(A, B)
mean_x <- means[1]
mean_y <- means[2]
b_x <- -1/6
b_y <- -3/2
r <- sqrt(b_x * b_y)
mean_x
mean_y
r
```

**Output:**  
```bash
> #Q6 
> A <- matrix(c(1, 6, 3, 2), nrow=2, byrow=TRUE)
> B <- c(6, 10)
> means <- solve(A, B)
> mean_x <- means[1]
> mean_y <- means[2]
> b_x <- -1/6
> b_y <- -3/2
> r <- sqrt(b_x * b_y)
> mean_x
[1] 3
> mean_y
[1] 0.5
> r
[1] 0.5
```
---
# References


###### Information
- date: 2025.03.11
- time: 22:06