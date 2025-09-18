---
Title: AI ML Lab 1
Status: true
marker:
  - "[[Artificial Intelligence Index]]"
tags:
Date: 2025.07.24
Time: 14:39
---
# AI ML Lab 1
To get started with using Pandas and DataFrames for data analysis and AI ML, especially focusing on normal distribution, identifying outliers, and understanding the uniqueness of data, let's go through some key concepts and examples.
### 1. Understanding Pandas and DataFrames
Pandas is a powerful data manipulation library in Python that provides data structures and functions needed to manipulate structured data. The primary data structure in Pandas is the `DataFrame`, which you can think of as a spreadsheet or SQL table.

### 2. Normal Distribution
A normal distribution is a bell-shaped frequency distribution curve. Most of the data points cluster toward the middle, with fewer data points at the extremes. In Pandas, you can check for normal distribution visually using histograms or statistically using tests like the Shapiro-Wilk test.

### 3. Identifying Outliers
Outliers are data points that differ significantly from other observations. They can be identified using statistical methods such as the Z-score or IQR (Interquartile Range).

### 4. Using `nunique()`
The `nunique()` function in Pandas is used to count the distinct observations over the requested axis. It's useful for understanding the uniqueness of data in a column.

#### Example: Checking Unique IP Addresses in a DDOS Attack

```python
import pandas as pd

# Sample data
data = {'ip_address': ['192.168.1.1', '192.168.1.2', '192.168.1.1', '192.168.1.3']}
df = pd.DataFrame(data)

# Count unique IP addresses
unique_ips = df['ip_address'].nunique()
print(f"Number of unique IP addresses: {unique_ips}")
```

#### Example: Checking SAP IDs

```python
# Sample data
data = {'sap_id': [1, 2, 3, 1, 2, 3, 4, 5, 6, 1]}
df = pd.DataFrame(data)

# Count unique SAP IDs
unique_sap_ids = df['sap_id'].nunique()
required_sap_ids = 60
print(f"Number of unique SAP IDs: {unique_sap_ids}")
print(f"Number of repeated SAP IDs: {required_sap_ids - unique_sap_ids}")
```

### 5. Using `describe()` for Data Preprocessing
The `describe()` function generates descriptive statistics that summarize the central tendency, dispersion, and shape of a dataset’s distribution, excluding `NaN` values.

```python
# Generate descriptive statistics
description = df.describe()
print(description)
```

### 6. Preworking Data with Pandas
- **Loading Data**: Use `pd.read_csv()` or `pd.read_excel()` to load data into a DataFrame.
- **Cleaning Data**: Handle missing values with `dropna()` or `fillna()`.
- **Transforming Data**: Use functions like `apply()`, `map()`, or `groupby()` to transform data.
- **Filtering Data**: Use boolean indexing to filter data.

### Example: Data Preprocessing
```python
# Load data
df = pd.read_csv('your_data.csv')

# Check for missing values
print(df.isnull().sum())

# Fill missing values
df.fillna(0, inplace=True)

# Describe the data
print(df.describe())

# Check unique values in a column
print(df['column_name'].nunique())
```

# Lab Work



# References


###### Information
- date: 2025.07.24
- time: 14:39