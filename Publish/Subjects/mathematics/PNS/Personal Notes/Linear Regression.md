---
Title: Linear Regression
Status: true
marker:
  - "[[Probability and Statistics (PNS)]]"
tags:
  - BTech
Date: 2025.03.26
Time: 16:57
---
# Regression
if x values are missing and x and y are related we are going to use x on y
	and if y values are given the
Regression can be defined as a statistical method used to determine the strength and character of the relationship between one dependent variable (usually denoted by Y) and one or more independent variables (usually denoted by X).
Regression analysis is a mathematical measure of the average relationship between two or more variables in terms of the original units of the data.

## Equation of Regression Line
The regression line is a straight line that best fits the data points in a scatter plot. It is represented by the equation:

1) $b_{yx}=\frac{r\sigma_y}{\sigma_x}$
2) $b_{xy}=\frac{r\sigma_x}{\sigma_y}$
3) Line of regression of $y$ on $x$: 
	1) $$
	 y = a + bx
	 $$
	2)  $$y-\bar{y}=b_{yx}(x-\bar{x})$$
4) Line of regression of $x$ on $y$:
	3) $$
	 x = a + by
	 $$
	4)  $$x-\bar{x}=b_{xy}(y-\bar{y})$$

We can calculate the value of $r$ using 
## Properties of Regression Line
Average of the equation of regression line is the point $(\bar{x},\bar{y})$. The regression line passes through this point.
1) The regression line passes through the point $(\bar{x},\bar{y})$.
2) $b_{yx}=\frac{r\sigma_y}{\sigma_x}$ and $b_{xy}=\frac{r\sigma_x}{\sigma_y}$
3) $b_{yx}\times b_{xy}=r^2$   $\therefore r = \sqrt{b_{yx} b_{xy}  }$
4) Signatures of both $b_{yx}$ and $b_{xy}$ have to be the same as r.=
5) The sign of r can is the sign of $b_{yx}$ and $b_{xy}$. If r is positive, both $b_{yx}$ and $b_{xy}$ are positive, and if r is negative, both $b_{yx}$ and $b_{xy}$ are negative.
6) $(\bar{x},\bar{y})$ is the solution to the equation

# Least Squares Method

The least squares method is a standard approach in regression analysis to approximate the solution of overdetermined systems by minimizing the sum of the squares of the errors made in the results of every single equation.

$$
y = a + bX
$$

To find the coefficients \(a\) and \(b\), we use the following equations:

$$
\sum y = \sum a + \sum bX = na + b\sum X
$$

$$
\sum xy = a\sum x + b\sum x^2
$$

These equations are derived from the condition that the sum of the squared differences between the observed and predicted values is minimized.
# Multiple Regression
Lets say there is a regression line that goes by 
$$Y=a+bX_{1}+cX_{2}$$
where $Y$ is the dependent variable and $X_{1}$ and $X_{2}$ are the independent variables. The coefficients $a$, $b$, and $c$ are the regression coefficients.

We can summate on both the sides
$$\sum Y=Na+b\sum X_{1}+c\sum X_{2}$$
$$\sum X_{1}Y=a\sum X+b\sum X_{1}^{2}+c\sum X_{2}X_{1}$$


# References


###### Information
- date: 2025.03.26
- time: 16:57