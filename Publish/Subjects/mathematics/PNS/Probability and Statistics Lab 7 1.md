---
Title: Probability and Statistics Lab 7
Status: 
marker: 
tags: 
Date: 2025.03.04
Time: 13:33
---
# Probability and Statistics Lab 7



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

### Output

# References
Lost snippet
```md

## Question 2

| X   | 62  | 64  | 65  | 69  | 70  | 71  | 72  | 74  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Y   | 126 | 125 | 139 | 145 | 165 | 152 | 180 | 208 |

### **Calculated Values**

#### **Mean Values**

- Xˉ=68.375\bar{X} = 68.375
- Yˉ=155.0\bar{Y} = 155.0

#### **Table with Calculated Values**

| X   | Y   | $X - \bar{X}$ | $Y- \bar{Y}$ | $(X - \bar{X})(Y - \bar{Y})$ | $D (X−Xˉ−(Y−Yˉ)X - \bar{X} - (Y - \bar{Y}))$ | D2D^2   |
| --- | --- | ------------- | ------------ | ---------------------------- | -------------------------------------------- | ------- |
| 62  | 126 | -6.375        | -29.0        | 184.875                      | 22.625                                       | 511.89  |
| 64  | 125 | -4.375        | -30.0        | 131.250                      | 25.625                                       | 656.64  |
| 65  | 139 | -3.375        | -16.0        | 54.000                       | 12.625                                       | 159.39  |
| 69  | 145 | 0.625         | -10.0        | -6.250                       | 10.625                                       | 112.89  |
| 70  | 165 | 1.625         | 10.0         | 16.250                       | -8.375                                       | 70.14   |
| 71  | 152 | 2.625         | -3.0         | -7.875                       | 5.625                                        | 31.64   |
| 72  | 180 | 3.625         | 25.0         | 90.625                       | -21.375                                      | 456.89  |
| 74  | 208 | 5.625         | 53.0         | 298.125                      | -47.375                                      | 2244.39 |

```

###### Information
- date: 2025.03.04
- time: 13:33