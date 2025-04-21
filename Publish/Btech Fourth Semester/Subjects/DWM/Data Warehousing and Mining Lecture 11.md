---
Title: "Data Warehousing and Mining Lecture 11"
Status: 
marker: 
tags: 
Date: "2025.03.05"
Time: "13:05"
---
# Mining K Nearest Neighbours
KNN is a supervised learning algorithm that can be used to identify the class for an unknown data instance based upon a similarity measure or a distance metric i.e. (KNN)
# K-Nearest Neighbors (KNN)

K-Nearest Neighbors (KNN) is a simple, intuitive machine learning algorithm used for both classification and regression tasks. It is a type of instance-based learning, where the function is only approximated locally and all computation is deferred until classification.

### How KNN Works

The KNN algorithm operates on the principle that similar data points tend to cluster together. When a new data point needs to be classified or evaluated, KNN looks at the 'k' closest data points in the feature space and uses their properties to make a prediction.

#### Key Concepts:
- **Distance Metric**: The distance between data points is typically measured using Euclidean distance, but other metrics like Manhattan distance or Minkowski distance can also be used.

  For two points $p$ and $q$ in Euclidean space, the Euclidean distance is given by:
  $$d(p,q)=\sqrt{\sum_{i=1}^{n}(p_i-q_i)^2}$$

- **Choice of K**: The number of nearest neighbors (k) is a critical parameter. A small value of k makes the model more sensitive to noise in the training data, while a large value of k makes the model less sensitive to relevant patterns.

### Steps in KNN Algorithm

1. **Choose the number of neighbors (k)**.
2. **Calculate the distance** between the new data point and all training data points.
3. **Sort the distances** and determine the k-nearest neighbors.
4. **Aggregate the labels** of the k-nearest neighbors to make a prediction (for classification, this is typically done by majority vote; for regression, it is done by averaging the values).

### Applications of KNN

KNN is versatile and can be applied to various domains:
- **Classification**: Used in text categorization, image recognition, and recommendation systems.
- **Regression**: Used in predicting continuous values like house prices or stock market trends.

### Advantages and Disadvantages

#### Advantages:
- **Simplicity**: Easy to understand and implement.
- **Non-parametric**: Makes no assumptions about the underlying data distribution.
- **Versatile**: Can be used for both classification and regression tasks.

#### Disadvantages:
- **Computational Cost**: High computational cost for large datasets due to the need to compute distances to all training points.
- **Memory Usage**: Requires storing the entire training dataset.
- **Sensitivity to Irrelevant Features**: Performance can degrade with high-dimensional data due to the curse of dimensionality.

### Improvements and Variations

Several techniques can improve the performance of KNN:
- **Feature Scaling**: Normalizing or standardizing features to ensure that distance calculations are meaningful.
- **Dimensionality Reduction**: Using techniques like Principal Component Analysis (PCA) to reduce the number of features.
- **Weighted KNN**: Assigning weights to neighbors based on their distance, giving closer neighbors more influence.

### Conclusion

KNN is a powerful and flexible algorithm suitable for a wide range of applications. Its simplicity makes it a good starting point for many machine learning tasks, but care must be taken to choose the right value of k and to manage computational efficiency, especially with large datasets.

### References

###### Information
- date: 2024.08.06
- time: 18:00




# References


###### Information
- date: 2025.03.05
- time: 13:05