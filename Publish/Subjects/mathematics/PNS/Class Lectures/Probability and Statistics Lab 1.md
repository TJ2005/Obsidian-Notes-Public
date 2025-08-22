---
Title: Probability & Statistics Lab 1
Status: true
marker:
  - "[[Probability and Statistics (PNS)]]"
  - "[[R Studio]]"
tags:
  - BTech
Date: 2025.01.11
Time: 15:33
---
## Probability & Statistics Lab 1

> [!INFO]
>  Concepts of [[Basic Probability]]
> To start learning basic R Studio, read [[IMG-20250730000529107.pdf]].

> [!WARNING]
> I was absent this lecture.

### Class Work

#### Q1 Create a vector with some of your friend’s names


```r
v1 <- c("Tanishq", "Krish", "Ananya", "Lakshya", "Sumit")
length(v1)
v12 <- v1[1:2]
v23 <- v1[2:3]
v12
v23
sort(v1, decreasing = TRUE)
sort(v1, decreasing = FALSE)
```

```js
[1] 5
[1] "Tanishq" "Krish"  
[1] "Krish"  "Ananya"
[1] "Tanishq" "Sumit" "Lakshya" "Krish" "Ananya"
[1] "Ananya" "Krish" "Lakshya" "Sumit" "Tanishq"
```

#### Q2 Compute the difference
Compute the difference between 2014 and the year you started at this university and divide this by the difference between 2014 and the year you were born. Multiply this with 100 to get the percentage of your life you have spent at this university.

```r
d1 <- 2025 - 2022
d2 <- 2025 - 2004
l <- d1 / d2
l * 100
```

```js
[1] 14.28571
```

#### Q3 Compute the sum of 4, 5, 8 and 11 by first combining them into a vector and then using the function sum.

```r
n <- c(4, 5, 8, 11)
tsum <- sum(n)
tsum
```

```js
[1] 28
```

#### Q4 Create three vectors x,y,z 
Create three vectors x,y,z with integers and each vector has 3 elements.Combine the three vectors to become a 3×3 matrix A where each column represents a vector. Change the row names to a,b,c.

```r
x <- c(1, 2, 3)
y <- c(4, 5, 6)
z <- c(7, 8, 9)
M <- cbind(x, y, z)
rownames(M) <- c("a", "b", "c")
M
```

```js
  x y z
a 1 4 7
b 2 5 8
c 3 6 9
```

#### Q5  What is a vector? How to create it? 
What is a vector? How to create it? Create a vector A of elements 5, 2, -2, 6,7,10,12,14,15 and from it create a vector Y containing elements of A>6

```r
A <- c(5, 2, -2, 6, 7, 10, 12, 14, 15)
Y <- A[A > 6]
Y
```

```js
[1]  7 10 12 14 15
```

#### Q6  Create a vector 
Create a vector containing following mixed elements {1, ‘a’, 2, ‘b’} and find out its class.

```r
mv <- c(1, 'a', 2, 'b')
vc <- class(mv)
vc
```

```js
[1] "character"
```

#### Q7  Write a R program to create three vectors numeric data
Write a R program to create three vectors numeric data, character data and logical data. Display the content of the vectors and their type.

```r
nv <- c(1.1, 2.2, 3.3)
cv <- c("R", "Programming", "Language")
lv <- c(TRUE, FALSE, TRUE)
class(nv)
class(cv)
class(lv)
```

```js
[1] "numeric"
[1] "character"
[1] "logical"
```

#### Q7: Create and display vectors of numeric, character, and logical data

**Code:**

```r
# Create three vectors: numeric, character, and logical
nv <- c(1.1, 2.2, 3.3)
cv <- c("R", "Programming", "Language")
lv <- c(TRUE, FALSE, TRUE)

# Display the content and class (type) of each vector
print(nv)
print(class(nv))

print(cv)
print(class(cv))

print(lv)
print(class(lv))
````

**Output:**

```r
[1] 1.1 2.2 3.3
[1] "numeric"

[1] "R"           "Programming" "Language"
[1] "character"

[1]  TRUE FALSE  TRUE
[1] "logical"
```

---

#### Q8: Create matrices of various dimensions with labels and specific fill orders

**Code:**

```r
# Create a 4 x 5 matrix (default fills by columns)
mat_4x5 <- matrix(1:20, nrow = 4, ncol = 5)
print(mat_4x5)

# Create a 3 x 2 matrix filled by rows with row and column labels
mat_3x2 <- matrix(1:6, nrow = 3, ncol = 2, byrow = TRUE)
rownames(mat_3x2) <- c("row1", "row2", "row3")
colnames(mat_3x2) <- c("col1", "col2")
print(mat_3x2)

# Create a 2 x 2 matrix filled by columns (default) with labels
mat_2x2 <- matrix(1:4, nrow = 2, ncol = 2)
rownames(mat_2x2) <- c("r1", "r2")
colnames(mat_2x2) <- c("c1", "c2")
print(mat_2x2)
```

**Output:**

For the 4×5 matrix:

```r
     [,1] [,2] [,3] [,4] [,5]
[1,]    1    5    9   13   17
[2,]    2    6   10   14   18
[3,]    3    7   11   15   19
[4,]    4    8   12   16   20
```

For the 3×2 matrix:

```r
     col1 col2
row1    1    2
row2    3    4
row3    5    6
```

For the 2×2 matrix:

```r
   c1 c2
r1  1  3
r2  2  4
```

---

#### Q9: Compute the sum, mean, and product of a vector's elements

**Code:**

```r
# Create a vector and compute its sum, mean, and product
vec <- c(2, 4, 6, 8)
vec_sum <- sum(vec)
vec_mean <- mean(vec)
vec_prod <- prod(vec)

print(vec_sum)
print(vec_mean)
print(vec_prod)
```

**Output:**

```r
[1] 20
[1] 5
[1] 384
```

---

#### Q10: List all the observations of the "airmiles" dataset

**Code:**

```r
# Load and display the built-in 'airmiles' dataset
data("airmiles")
print(airmiles)
```

**Output:**

```r
# The output will display the complete 'airmiles' time series dataset.
# (Exact values depend on the dataset version, typically similar to:)
Time Series:
Start = 1937 
End = 1960 
Frequency = 1 
 [1] 112 115 116 117 118 119 120 121 122 123 ... (continues)
```

---

#### Q11: Perform addition, subtraction, and element-wise multiplication of two 4×4 matrices

**Code:**

```r
# Create two 4x4 matrices
mat1 <- matrix(1:16, nrow = 4, ncol = 4)
mat2 <- matrix(17:32, nrow = 4, ncol = 4)

# Addition
mat_add <- mat1 + mat2
print(mat_add)

# Subtraction
mat_sub <- mat2 - mat1
print(mat_sub)

# Element-wise multiplication
mat_mul <- mat1 * mat2
print(mat_mul)
```

**Output:**

For addition (`mat_add`):

```r
     [,1] [,2] [,3] [,4]
[1,]   18   26   34   42
[2,]   20   28   36   44
[3,]   22   30   38   46
[4,]   24   32   40   48
```

For subtraction (`mat_sub`):

```r
     [,1] [,2] [,3] [,4]
[1,]   16   16   16   16
[2,]   16   16   16   16
[3,]   16   16   16   16
[4,]   16   16   16   16
```

For element-wise multiplication (`mat_mul`):

```r
     [,1] [,2] [,3] [,4]
[1,]   17  105  225  377
[2,]   36  132  260  420
[3,]   57  161  297  465
[4,]   80  192  336  512
```

---

#### Q12 & Q13: Create a list containing a vector, a matrix, and a list; name its elements and access the second element

**Code:**

```r
# Create individual components
my_vector <- c(10, 20, 30)
my_matrix <- matrix(1:9, nrow = 3, ncol = 3)
my_inner_list <- list(sub_vector = c("a", "b"), sub_value = 42)

# Combine them into a list with named elements
my_list <- list(
  vector_component = my_vector,
  matrix_component = my_matrix,
  list_component = my_inner_list
)

# Access the second element of the list (the matrix)
second_element <- my_list[[2]]
print(second_element)
```

**Output:**

```r
     [,1] [,2] [,3]
[1,]    1    4    7
[2,]    2    5    8
[3,]    3    6    9
```

