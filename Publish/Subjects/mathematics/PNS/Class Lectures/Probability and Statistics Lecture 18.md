---
Title: Probability and Statistics Lecture 18
Status: 
marker: 
tags: 
Date: 2025.02.28
Time: 11:19
---
> [!Continued From]
> [[Probability and Statistics Lecture 17]]
> **Prerequsites**
> - [[Linear Regression]]


# Questions
### Question 3 
Calculate the correlation of marks of students
Following are the marks in Statistics ($x$) and Mathematics ($y$) of 10 students:
To calculate coefficient 

| $X$ | 56  | 55  | 58  | 57  | 56  | 60  | 54  | 60  | 54  | 59  | 57  | 58  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| $Y$ | 68  | 67  | 67  | 65  | 68  | 70  | 66  | 68  | 66  | 70  | 66  | 70  |

## Question 4
The following equations $2x+y=3$ and $x=2y+3$ are given prove that they cannot be lines of regression
The calculated values are as follows:

$$- ∑XY=46252\sum XY = 46252$$
$$- ∑X2=39036\sum X^2 = 39036$$
$$- ∑Y2=54843\sum Y^2 = 54843$$

Now, we can substitute these values into the correlation formula to calculate the correlation coefficient rr. Let me proceed with that calculation.

The correlation coefficient rr between the marks in Statistics (XX) and Mathematics (YY) is approximately 0.629. This indicates a moderate positive correlation between the two sets of marks.
### Answer
We assume that the given equations are the lines of regression. We have to find the correlation coefficient between the two lines. We will then try to violate the properties of regression lines.

To complete the solution, we need to follow these steps:

1. **Assume the given equations are lines of regression:**
   - The equations are \(2x + y = 3\) and \(x = 2y + 3\).

2. **Rewrite the equations in the form of regression lines:**
   - For the first equation: \(2x + y = 3\)
     \[
     y = 3 - 2x
     \]
   - For the second equation: \(x = 2y + 3\)
     \[
     x = 2y + 3
     \]

3. **Identify the slopes of the regression lines:**
   - The slope of the first line (\(y = 3 - 2x\)) is \(-2\).
   - The slope of the second line (\(x = 2y + 3\)) is \(2\) (since \(y = \frac{x - 3}{2}\)).

4. **Use the property of regression lines:**
   - The product of the slopes of the two regression lines should be equal to the square of the correlation coefficient \(r\).
     \[
     b_{yx} \cdot b_{xy} = r^2
     \]
   - Here, \(b_{yx} = -2\) and \(b_{xy} = 2\).

5. **Calculate the product of the slopes:**
   \[
   (-2) \cdot (2) = -4
   \]

6. **Compare with the property of regression lines:**
   - The product of the slopes is \(-4\), which is not possible because \(r^2\) (the square of the correlation coefficient) must be non-negative (since \(r^2 \geq 0\)).

7. **Conclusion:**
   - Since the product of the slopes does not satisfy the property of regression lines, the given equations cannot be lines of regression.

Thus, we have shown that the given equations \(2x + y = 3\) and \(x = 2y + 3\) cannot be lines of regression.

## Question 5
If two lines of regression are $x+3y-5=0$ and $4x+3y-8=0$ then the correlation coefficient is $r=0.5$
# References


###### Information
- date: 2025.02.28
- time: 11:19

> [!Continued to]
> [[Probability and Statistics Lecture 19]]