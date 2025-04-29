---
Title: "Data Warehousing and Mining Lecture 10"
Status: 
marker: 
tags: 
Date: "2025.02.28"
Time: "10:27"
---
# Data Mining Steps 
1. Extract the dataset from heterogenous data sources
2. Data preprocessing and normalisation
3. Identification of data classes
4. Identification of input parameters to the classification technique
5. Splitting of the dataset into training and testing
6. Fitting the model in the training subset
7. Implementation of the classification technique
8. Evaluation of the output parameters
9. Interpretation of the output wrt the problem statements
# Clustering and Classification
**Clustering** and **Classification** are both common techniques used in machine learning, but they differ in terms of their approach, use cases, and types of data they handle. Here’s a breakdown of both:
### 1. **Clustering:**
Clustering is an **unsupervised learning** technique that groups similar data points together based on certain features or characteristics. The goal is to identify natural groupings in the data without prior knowledge of labels.
- **Type of Learning:** Unsupervised
- **Purpose:** To discover hidden patterns or inherent groupings in data without predefined labels.
- **Input:** Data without any labels (no output category is known in advance).
- **Output:** Groups or clusters of similar data points.
- **How it Works:** The algorithm identifies similarity between data points and assigns them to clusters. The number of clusters may or may not be predefined, depending on the algorithm used.
**Example Algorithms:**
- **K-Means**: Partitions data into K clusters based on centroids.
- **DBSCAN (Density-Based Spatial Clustering of Applications with Noise)**: Groups points that are closely packed together and marks outliers as noise.
- **Hierarchical Clustering**: Builds a tree-like structure (dendrogram) of clusters.
**Use Cases:**
- Market segmentation (grouping customers by behavior).
- Image compression.
- Document categorization.
- Anomaly detection (identifying unusual patterns in data).

---

### 2. **Classification:**

Classification is a **supervised learning** technique where the goal is to assign predefined labels to data based on input features. It uses labeled training data to learn the mapping between the input features and the output class.

- **Type of Learning:** Supervised
- **Purpose:** To predict a category or class label for new, unseen data based on learned relationships from labeled data.
- **Input:** Data with predefined labels (output categories are known during training).
- **Output:** A class label (e.g., "spam" or "not spam," "dog" or "cat").
- **How it Works:** The algorithm learns the relationship between input features and output labels from the training data and uses this knowledge to classify new data.

**Example Algorithms:**

- **Logistic Regression**: Predicts binary outcomes.
- **Decision Trees**: Classifies data by splitting it at various decision points.
- **Random Forest**: An ensemble method that combines multiple decision trees.
- **Support Vector Machines (SVM)**: Finds a hyperplane that best separates data into different classes.

**Use Cases:**

- Email spam detection.
- Sentiment analysis (positive, negative, neutral).
- Medical diagnosis (e.g., classifying diseases).
- Image recognition (e.g., identifying objects or faces).

---

### **Key Differences Between Clustering and Classification:**

|**Aspect**|**Clustering**|**Classification**|
|---|---|---|
|**Type of Learning**|Unsupervised (no labels during training)|Supervised (requires labeled data for training)|
|**Goal**|To group similar data points together|To assign data points to predefined categories|
|**Input Data**|Unlabeled data|Labeled data (features with known class labels)|
|**Output**|Clusters (groups) of similar data points|Class labels (predictions of categories)|
|**Nature of Task**|Pattern discovery or grouping|Prediction of labels based on known patterns|
|**Examples of Algorithms**|K-Means, DBSCAN, Hierarchical Clustering|Decision Trees, SVM, Random Forest, Logistic Regression|
|**Use Cases**|Customer segmentation, image compression, anomaly detection|Fraud detection, medical diagnosis, sentiment analysis|

---
### **How to identify the object on the basis of classification or clustering.**

- If we want to find behaviour, trend we will use clustering. It is unsupervised identifying technique
- Classification is a supervised learning approach used to categorize items into predefined classes or groups based on labelled data.
### **Summary:**

- **Clustering** is used for discovering patterns or structures in data when labels are unknown. It works well when you want to understand the natural groupings in your data without prior knowledge of what those groups should be.
- **Classification** is used for predicting predefined labels based on historical data with known labels. It is typically used in situations where you want to categorize new data points into classes based on what the model has learned.

In short, clustering **finds structure** in data, while classification **assigns labels** to data.

## Statistical Baye's method
Classification is done on the basis of 
1. Regression technique
	1. based on Statistical Principal of dependant and independent variables and following the eqn $y=mx+c$
	2. y is the dependant variable and x is the independent variable
	3. m is the slope of the line and c is the intercept of the line
	4. The value of y is calculated on the basis of the value of x
	5. The value of m and c is calculated on the basis of the training data
	6. The value of y is calculated on the basis of the testing data
	7. The value of y is calculated on the basis of the testing data
	8. The value of y is calculated on the basis of the testing data


-  Regression Technique : Based upon statistical principle of dependent and independent variables and following the equation ![](data:image/png;base64,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)
- Bayesian Classification: Based on the statistical principle of bayes theorem i.e. conditional *probability*

- Distance based classification

- K-Nearest Neighbour (KNN): Dividing the objects on the base of distance between the set of classes like Euclidean distance method

- Decision Tree Based Classification

- Dividing the input dataset into a set of classes based upon the hierarchical tree like structure having set of rules and classes

Based on the statistical principal of bayes theorem that is conditional probability 

Distance based classification
Dividing the data instances based upon the distance b/w set of classes
like euclidean distance method

Decision Tree based classification
Dividing the input data set having tree like structure that has set of rules or decision tree based classification

## Bayesian Classifier
The Bayesian theorem 
# Problem Statements
## Q1
Suppose $D=\{t_1,t_2,\dots t_{m}\}$ of tuples and a set of class $C=\{c_1,c_2,\dots\}$





# References


###### Information
- date: 2025.02.28
- time: 10:27