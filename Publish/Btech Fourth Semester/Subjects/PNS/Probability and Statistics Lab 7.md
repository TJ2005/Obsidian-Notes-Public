---
Title: Probability and Statistics Lab 7
Status: 
marker: 
tags: 
Date: 2025.03.04
Time: 13:33
---
# Probability and Statistics Lab 7

> [!Prerequisites]
> [[Probability and Statistics Lecture 17]]
 
## Explanatory code
```R
# Load necessary libraries
library(ggplot2)
library(GGally)
library(corrplot)

# Load the built-in 'mtcars' dataset
data(mtcars)

# Compute Pearson correlation between mpg and hp
correlation <- cor(mtcars$mpg, mtcars$hp, method = "pearson")
cat("Correlation between mpg and hp:", correlation, "\n")

# Scatter plot of hp vs mpg using ggplot2
ggplot(mtcars) +
  aes(x = hp, y = mpg) +
  geom_point(color = "red") +
  theme_minimal() +
  ggtitle("Scatter Plot of HP vs MPG")

# Pairwise scatter plots for all variables
ggpairs(mtcars)

# Select specific columns (1, 4, 6, 7) for scatterplot matrix
pairs(mtcars[, c(1, 4, 6, 7)])

# GGPairs for selected columns
ggpairs(mtcars[, c(1, 4, 6, 7)])

# Compute correlation matrix for all variables
mat <- cor(mtcars)
print(mat)

# Plot the correlation matrix
corrplot(mat, method = "circle")
```

![](https://i.imgur.com/qDfrzGN.png)
![](https://i.imgur.com/d1hpt7O.png)
![](https://i.imgur.com/vFC6xXM.png)
![](https://i.imgur.com/yXgtrzd.png)
![](https://i.imgur.com/HR4xoN6.png)

## Question  2
```R
# Q1 

# Define rankings given by two judges
judgeA = c(8,7,6,3,2,1,5,4)
judgeB = c(7,5,4,1,3,2,6,8)

# Compute Pearson correlation coefficient between Judge A and Judge B
rescorr <- cor(judgeA, judgeB, method = "pearson")
rescorr  # Print the correlation value

# Create a dataframe with the rankings
judge_data = data.frame(Play = 1:8, judgeA, judgeB)

# Scatter plot using ggplot2
ggplot(judge_data, aes(x = judgeA, y = judgeB)) +
  geom_point(color = "blue", size = 3) +  # Blue scatter points
  labs(title = "Scatter plot of Judge A vs Judge B Rankings",
       x = "Judge A Rankings",
       y = "Judge B Rankings") +
  theme_minimal()  # Minimalistic theme for better appearance

```

```bash
# Q1 
> > # Define rankings given by two judges
> judgeA = c(8,7,6,3,2,1,5,4)
> judgeB = c(7,5,4,1,3,2,6,8)
> > # Compute Pearson correlation coefficient between Judge A and Judge B
> rescorr <- cor(judgeA, judgeB, method = "pearson")
> rescorr  # Print the correlation value
[1] 0.6190476
```
![](https://i.imgur.com/GakwpKP.png)


### Question 3
```R

x <- c(62, 64, 65, 69, 70, 71, 72, 74)
y <- c(126, 125, 139, 145, 165, 152, 180, 208)
corr <- cor(x, y, method = "pearson")
corr
ggplot(data.frame(x,y), aes(x,y))+
  geom_point(color = "green", size = 3) +
  labs(title = "Scatter plot of X vs Y",
       x = "X values",
       y = "Y values") +
  theme_minimal()

```

```bash
> corr <- cor(x, y, method = "pearson")
> corr
[1] 0.9031822
> ggplot(data.frame(x,y), aes(x,y))+
+ geom_point(color = "green", size = 3) +
+ labs(title = "Scatter plot of X vs Y",
+ x = "X values",
+ y = "Y values") +
+   theme_minimal()
```

![](https://i.imgur.com/Q81gBhj.png)


### Question 4
```R

x <- c(62, 64, 65, 69, 70, 71, 72, 74)
y <- c(126, 125, 139, 145, 165, 152, 180, 208)
corr <- cor(x, y, method = "pearson")
corr
ggplot(data.frame(x,y), aes(x,y))+
  geom_point(color = "green", size = 3) +
  labs(title = "K071 Scatter plot of X vs Y",
       x = "X values",
       y = "Y values") +
  theme_minimal()


data("airquality")
data("faithful")
data("trees")
data("longley")
airquality_corr <- cor(airquality)
airquality_corr
ggpairs(airquality)
faithful_corr <- cor(faithful)
faithful_corr
ggpairs(faithful)
trees_corr <- cor(trees)
trees_corr
ggpairs(trees)
longley_corr <- cor(longley)
longley_corr
ggpairs(longley)

```

```bash
> #Q3
> data("airquality")
> data("faithful")
> data("trees")
> data("longley")
> airquality_corr <- cor(airquality)
> airquality_corr
        Ozone Solar.R       Wind       Temp        Month          Day
Ozone       1      NA         NA         NA           NA           NA
Solar.R    NA       1         NA         NA           NA           NA
Wind       NA      NA  1.0000000 -0.4579879 -0.178292579  0.027180903
Temp       NA      NA -0.4579879  1.0000000  0.420947252 -0.130593175
Month      NA      NA -0.1782926  0.4209473  1.000000000 -0.007961763
Day        NA      NA  0.0271809 -0.1305932 -0.007961763  1.000000000
```

![](https://i.imgur.com/4o4U9Ht.png)
![](https://i.imgur.com/AV5yGSZ.png)
![](https://i.imgur.com/rRd9Ekq.png)


### Question 4
```R

# Q2
x <- c(62, 64, 65, 69, 70, 71, 72, 74)
y <- c(126, 125, 139, 145, 165, 152, 180, 208)
corr <- cor(x, y, method = "pearson")
corr
ggplot(data.frame(x,y), aes(x,y))+
  geom_point(color = "green", size = 3) +
  labs(title = "Scatter plot of X vs Y",
       x = "X values",
       y = "Y values") +
  theme_minimal()

# Q3
data("airquality")
data("faithful")
data("trees")
data("longley")
airquality_corr <- cor(airquality)
airquality_corr
ggpairs(airquality)
faithful_corr <- cor(faithful)
faithful_corr
ggpairs(faithful)
trees_corr <- cor(trees)
trees_corr
ggpairs(trees)
longley_corr <- cor(longley)
longley_corr
ggpairs(longley)

# Q4
getSymbols("TSLA", from = "2023-01-01", to = "2023-12-31")
getSymbols("F", from = "2023-01-01", to = "2023-12-31")
TSLA_returns <- dailyReturn(Cl(TSLA))
F_returns <- dailyReturn(Cl(F))
#Calculate the correlation between Tesla and Ford daily returns
correlation <- cor(TSLA_returns, F_returns)
cat("Correlation between TSLA and F daily returns:", correlation, "\n")
par(mfrow = c(2, 1))  # Two plots in one row
plot(TSLA_returns, main = "Tesla Daily Returns", col = "blue", type = "l")
plot(F_returns, main = "Ford Daily Returns", col = "red", type = "l")
plot(TSLA_returns, F_returns, main = "Correlation between TSLA and F Returns",
     xlab = "TSLA Returns", ylab = "Ford Returns", pch = 19, col = "purple")
abline(lm(F_returns ~ TSLA_returns), col = "red")

```
![](https://i.imgur.com/sIwMAsF.png)

### Output
- date: 2025.03.04
- time: 13:33