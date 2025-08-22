---
Title: "Data Warehousing and Mining Lab 12"
Status: 
marker: 
tags: 
Date: "2025.03.12"
Time: "13:14"
---
# Classification and Clustering


|Feature|Classification|Clustering|
|---|---|---|
|**Type of Learning**|Supervised (data is assigned to predefined categories)|Unsupervised|
|**Supervised/Unsupervised**|Supervised|Unsupervised|
|**Labeling Requirement**|Requires labeled data|No predefined labels|
|**Goal**|Classifies new data into known categories|Discovers hidden structures in the data|
|**Examples**|Spam detection, disease diagnosis, sentiment analysis|Image clustering, anomaly detection|
|**Algorithms**|Decision Trees, SVM, Random Forest, Neural Networks|K-Means, DBSCAN, Hierarchical Clustering|
|**Output**|Discrete categories (e.g., spam or not spam)|Grouped clusters based on similarity|
|**Use Case Focus**|Predicting labels for new data|Finding patterns and natural groupings in data|
|**Real-World Example**|Email classification into spam/ham|Grouping customers by purchasing behavior|

# KDD Issues
- Human Interaction
- Overfitting
- Outliers 
- Interpretation because of the complexity of the model
- Visualization because of high dimensionality
- Large Data sets because of computational complexity
- MultiMedia data is an issue because format of the data can be in various forms.
	- Example photos and videos
- Changing Data Streams is an issue because the model may not be able to adapt to the new data.


# Assignment
Solve two numerical examples on on decision tree, regression, naivee baye's, IDB

# ID3
# Entropy
If S is a collection of 14 examples with 9 yes and 5 no examples then
Entropy(S)=-9/14 Log_2 (9/14) - (5/14)Log_2(5/14)=0.940

# Information Gain
Gain is defined as the difference between how much information is needed to make a correct classification before the split versus how much information is needed after the split.
Id3

# References


###### Information
- date: 2025.03.12
- time: 13:14