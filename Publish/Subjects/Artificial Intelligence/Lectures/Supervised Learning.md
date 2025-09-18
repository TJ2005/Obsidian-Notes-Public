---
Title: Supervised Learning
Status:
marker:
  - "[[Artificial Intelligence Index]]"
tags:
Date: 2025.08.26
Time: 14:19
---
# Supervised Learning

## Classification
- Predict Discrete Values
- Two possible Values
	- True or False
- Multi Class CLassification
	- Multi class classification
- Decision Tree, ID3 etc
## Regression
- Continuous
- Data to predict Continuous Values
- We try to plot a Linear Equation on a Graph that fits the dataset such that the average line from the distance is **MINIMUM**.
	- Before Applying Linear Regression we check that if the dataset has a plot in a linear way or not.
	- A linear regression is a good model if the data point is on the line or somewhere close to the line
	- If a situation where the linear regression has data points far away from the line then it is a 
	- Multiple Linear Regression
	- Shape of regression
	- Type of dependant Variable

- Charles darwin coined regression
$$ Y = a+b*X + e$$
Where $a$ is intercept, $b$ is slope of the line $e$ is the error.

Phishing mail example
$$ \text{No of compromised attacks} = -1.91 + 0.146 \times \text{X(phishing mails)} $$
Here when there are $0$ Phishing mails then there will be $-1.91$ attacks that means there will be no attacks.

For each phishing mail the number of compromised accounts increases by $0.146$.  

Regression V/s Classification
- Cont / Discrete
- Preediction of quant/class
- Real Number then regression/Class then classification

- **multiple regression**
	- Multiple regression works in favour when the rows are not highly corelated to each other
	- We have already done methods like PCA and other stuff
	- $Y + a+bX + e$
	- for $k$ number of independent variables
		- $y= a+b_1X_1+...+b_{k}X_{k}$
	- Case study
- **Cost Function**
	- Calculation of the error between the predicted and expected value
	- Average of error of n sample data.
	- Minimize Cost.
		- Indicates that the values are coming closer to the actual value
	- For the record if we calculate the average error it will be our cost function
- **Loss Function**
	- The Loss function represents difference between one prediction and its actual value.

- Metrics Used for Cost and Loss Functions
	- mean Error
		- Negative values will kill the values meaning by 
	- Mean Square Error
		- Avoids negative error balancing by squaring it and turning it into positive
		- Outliers will spike this metric by a lot since the values are already abnormally high or low.
		- Sensitive to outliers
	- Mean Absolute Error
		- Ignore the negative values so we dont have a negative value balancing situation
		- Robust to outliers
- **Bias**
	-  If bias is high then 
		- The Model is underfitted
	- Types of Bias:
		- Prejudicial Bias
			- Example : Candidate selections
			- Previous Data => more males are selected
			- Model Trains to be more biased to male while deployment
		- Sampling Bias
			- Imbalance of samples in Dataset
			- It should represent all the population that might come up when the model is actually deployed.
		- Algorithm Bias
			- Wrong Choice of algorithm
		- Confirmation Bias
			- Lets say a student named 
	- When Developing an application we focused the development for a different region but it was deployed to a different region we have a biasedness
- **VARIANCE**
	- How model acts on different samples of data.
	- High Variance $\implies$ Overfitting
	- Complexity Grows $\implies$ Bias Reduces
	- Complexity Grows $\implies$ Variance Increases
	- Model should have minimal variance and bias but having it as 0 is impossible
	- There is a sweet spot between these for different models.
	- Example
		- Dataset cosnsists of mixed traffic
			- Port Scans
			- SQL Injections
			- DDos
		- When trained on sample 1 it scans port scans correctly but fails on sql injections
		- Sample 2 gave a failure on DDoS but others were detected
		- Sample 3 Gave a failure on port scans
- **Example on Bias and Variance**
	- When a polynomial is fitted with a linear eqn we get a high bias
	- When a polynomial is fitted with another polynomial with an even higher degree of a polynomial the Bias is Very low but the variance is High

## Algorithms & Techniques for Classification

### Logistical Regression
- **Input Types** : 
	- Nominal
	- Ordinal
	- Interval Type
- Logistic Regression is derived fromt he concept of the logistic function that it uses
- Value of logistic function lies between $(1,0)$
- The curve indicates the likelihood of something
	- Example Whether the cells are cancerous or not
	- Email spam or not
	- Attack Malicious or not
- **Prerequisites / Assumptions**
	- Dependant variables must be categorical in nature
	- Only relevant variables should be included
	- Independent Variables are unrelated
- How linear regression differs from logistic regression
	- Logistic Function ( Sigmoid Function)
		- Maps the prpedicted values to probabilities
		- range $[0,1]$
		- It forms a curve like the $S$ form 
		- Logistical Regression Equation

		- **Types**
			- Binomial : Only two possible types
			- Multinomial Functions
				- 3 or more possible order types
				- Softmax Functions
			- **Ordinal** : 3 or more possible ordered types of independant variables
- Pros and Cons
	- **Pros**
		- Works well when the dataset is linearly seperable
		- The training time of logistic regression is small
		- Multi class classification
	- Cons
		- Overfitting 
			- If number of features > number of observations
		- Sensitive to outliers
		- Complex Data
			- Hits Linear Boundaries

### Support Vector Machine
- Works best on Small Datasets
- Hyperplane that best seperates two or more classes
- Hyperplane that has a maximum distances between the classes
- Type
	- Linear SVM 
		- Data is linearly seperable
		- Classification into 2 classes can be done using a single line
	- Non Linear SVM
		- Used when data is not seperable
- Datasets which has high dimensions relative to the observations
- Example 
	- Dna records
	- IP ADdresses
		- Multi ips but few info
- Terms
	- Hyperplane
	- Support Vector
	- margin
- Gap should be more then error will be reduced
	- Overlaps 
- Non Linear
	- Used for data that cant be seperated due to high dimensions
	- Kind of SVM that is implemented in practice using a kernel
	- Choice of kernel function
- **Pros**
	- Effective in high dimensional Space
	- Memory  Efficient
	- Hyperplane is affected by only the support vectors


| Rank | Marks1 | Marks2 |
| ---- | ------ | ------ |
|      |        |        |


# References


###### Information
- date: 2025.08.26
- time: 14:19