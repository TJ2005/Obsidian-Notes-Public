---
Title: Linear method
Status: 
marker:
  - "[[Artificial Intelligence Index]]"
tags: 
Date: 2025.08.14
Time: 12:14
---
# Linear method
- Used when datasets linear
- Only allows rotate and stretch the data
- Relationships that exist between two columns will still exist and be the same.

If by any way we can divide the dataset spread on a graph with a single line we can call it a *Linear Method???*



<center>
<img height=400px width = auto src="https://mathinsight.org/media/image/image/linear_transformation_2d_m1_m1_1_3.png"></center>


## [[PCA]] Principal Component Analysis
- Reduces the variables of dataset while preserving the as much information as possible.
- Several Corelated Features and projects them onto a coordinated axis.
	- The corelated features are an indication of similar information being provided. This implies merging these columns together will still result in the same **Inference**.
- **Goal** : Identify patterns and latent structures to create new columns instead of the original feature
- with a data matrix of size $n \times d$ where $n$ is the number of columns
- It has to **Generate** columns with **Maximum Variance**.
	- Data of which aspects change the most and are more important for the analsysis
- PCA are ordered by variance. 
	- Higher Variance $\implies$ More information
- Covariance Matrix
- Eigen Values 
- Eigen Vectors
- We are trying to find out features that are highly corelated and try to combine them. 
	- These merged columns are called Principal Components
	- Mixture of initial Variables. 
	- Or Linear Combinations 
- Allows one to reduce the dimensionality without losing much information
- Here PC1 is the combination of all the features into a single column
- PC2 Will be orthogonal to pc1
- By being orthogonal
$$\text{Final Dataset}  =  \text{Standardized Dataset} \times \text{Feature Vector}$$
![[IMG-20250822101422214.webp|center]]
#### Example
| Large Apples | Rotten Apples | Damaged Apples | Small Apples |
| ------------ | ------------- | -------------- | ------------ |
| F1           | F2            | F3             | F4           |
| 8.4          | 3.2           | 5.7            | 2.5          |
| 7.1          | 1.8           | 4.3            | 6.8          |
| 0.85         | 0.15          | 0.42           | 0.67         |
| 1.2          | 4.9           | 3.6            | 0.9          |


# References


###### Information
- date: 2025.08.14
- time: 12:14