---
Title: Feature Engineering
Status: 
marker:
  - "[[Artificial Intelligence Index]]"
tags:
  - BTech
Date: 2025.08.07
Time: 12:23
---
# Feature Engineering
One can call the columns as features. The columns represent information that may be related to each other. To find patterns between them is to learn about the dataset.

- Number of features are important.
	- Not enough informative features $\implies$ unable to perform the ultimate task
	- Too Many features $\implies$ Expensive and need more time to train
		- Can also result in a hallucinating model


#### Steps in Feature engineering
- Feature engineering and its parts
	- Selecting the relevant feature
	- Handling Missing data
	- Encoding the data and normalizing it.
- Proper dataset ready for training the model is the resulted expected.

- Another approach
	- **Feature Creations**
		- Creating new variables
		- Adding or removing some features
	- **Transformations**
		- Transforms one feature representation to another
		- Goal is
			- To prepare and convert raw data into a format that is more suitable and effective for training purposes
	- **Feature Extraction**
		- Extracting/Deriving Information from the original features subspace
		- Primary idea behind this is to compress the data and removing the unneeded columns for the data for a temporary amount of time.
	- **Exploratory Data Analysis**
		- Exploring its properties.
		- Find Hypothesis 
		- Patterns in data
	- **Benchmarking**
		- User trains model on any set of dataset.
		- Now all researches collectively use a benchmark dataset.
			- Checks the best score and compares itself with other models.
		- Models don't always outperform on datasets that it has not seen yet.

### Difference between Feature selection & Feature Extraction

|Aspect|Feature Selection|Feature Extraction|
|---|---|---|
|**Definition**|Selects a subset of relevant **original features** from the dataset|Transforms data into a new **feature space** using mathematical techniques|
|**Original Features**|**Maintained** (unchanged)|**Transformed** or replaced with new features|
|**Goal**|Remove irrelevant/redundant features while keeping the data interpretable|Derive informative new features to capture the underlying structure|
|**Method**|Choose features based on certain criteria (filter, wrapper, embedded)|Apply dimensionality reduction or transformation algorithms|
|**Resulting Feature Space**|Subset of original features|Completely new features (combinations of original ones)|
|**Interpretability**|High (features retain original meaning)|Often low (transformed features may be abstract or hard to interpret)|
|**Techniques**|- Mutual Information - Chi-Square Test - Recursive Feature Elimination (RFE) - LASSO|- Principal Component Analysis (PCA) - Linear Discriminant Analysis (LDA) - Autoencoders - t-SNE|
|**Data Dependency**|Relies on relevance of existing features|Derives information by projecting into new dimensions|
|**Computational Cost**|Typically lower|Can be higher due to matrix operations or learning algorithms|
|**Use Cases**|When interpretability is important or when original features are meaningful|When data is high-dimensional or complex patterns need capturing|
|**Example**|Keeping only “age” and “income” from a dataset of 10 features|Creating PC1, PC2 from 10 correlated features using PCA|


<center>
<img height=400px width = auto src="https://www.datocms-assets.com/88712/1689066538-https-blogs-images-forbes-com_gilpress_files_2016_03_time-1200x511-1.jpg?auto=format&w=960"></center>

## Feature Selection Techniques
- Feature Selection Technique
	- Supervised 
		- Filters Method
			- Checking correlation for correlated columns and drop.
			- Missing Value
			- Information Gain
			- Chi Squared Test
			- Etc
		- Wrapper Method
			- Search Problem
			- Different Combinations are made, evaluated and compared with the other combinations
			- It trains the algorithm by using the subset of features iteratively
			- Forward Selection: 
				- Begins with an empty set of features.
				- Start adding features and evaluate the performance.
			- Backward Elimination
				- Considers all Features
				- Removes one feature
			- Exhaustive Feature Selection
				- Brute Force
				- Tries & Make each possible combination of features
		- Embedded Technique
			- Combine the filter method and the wrapper method to save time.
		- Dimensionality Reduction
			- Performance Directly proportional to Input Variables
			- Columns as n Dimensional Feature Space
			- Rows as Data Points
			- Curse of dimensionality.
	- 

# References


###### Information
- date: 2025.08.07
- time: 12:23