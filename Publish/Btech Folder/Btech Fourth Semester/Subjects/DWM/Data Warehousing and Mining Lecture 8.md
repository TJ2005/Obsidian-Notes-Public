---
Title: "Data Warehousing and Mining Lecture 8"
Status: 
marker: 
tags: 
Date: "2025.02.19"
Time: "13:11"
---
# Data Mining Introduction
Data mining is a series of algorithm to be executed on the input data that consists of the current state of the object plus the historical object state. The outcome of this algorithm is prediction with reference to a target variable or grouping similar data instances or identifying the different classes of data. This outcome is to be further interpreted by an expert in the domain to which the dataset belongs. 

## Datamining
For any datamining problem you need to implement series of models for the same set of target variables.
In the next step choose the best performing model from the above series

### Knowledge Discovery in databases
Process of semi automatically analysing large databases to find pattern that are:
- Valid : Hold on new data with some certainty
- Novel : Non-obvious to the system
- Useful: Should be possible to act on the item
- Understandable: Humans should be able to interpret the pattern

# KDT

KDT (Knowledge discovery in databases) consists of following phases   
1. Data set extraction from one or more sources  
2. Data pre processing that is data cleaning and normalisation of data  
3. identification of mining algorithm that is mapping of the data set through the appropriate mining technique  
4. Splitting of the training and testing subsets  
5. Fitting training data into the model  
6. Model prediction and evaluation   
7. Identifying the flaws in the model and reiterating the process for the next model.  
8. Choose the best performing model from the iterations.
9. Interpretation of the data
10. Linking the data to the problem statement

## Application
Medicine
Molecular Pharmaceutical
Scientific data analysis
Web site store design and promotion

# Classification ( Supervised Learning )
The set of classes or labels is already given in the dataset. The mining algorithm is supervised to predict the right class based upon the label provided.

In classification trget variable = class
In regression the target variable = dv
1. class - Customer Type
2. Value of the class variable - Eligible for loan or not.
3. possible decision rule - Salary, Age, Profession


# References


###### Information
- date: 2025.02.19
- time: 13:11