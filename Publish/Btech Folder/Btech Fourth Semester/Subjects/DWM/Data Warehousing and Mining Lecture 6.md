---
Title: Data Warehousing and Mining Lecture 6
Status: 
marker: 
tags: 
Date: 2025.01.22
Time: 13:20
---

---

# Data Warehousing and Mining Lecture 6

## Fact Table

- **Fact Table** = **P.K. of Dimension Table** + **Additional Facts**
- The **business metrics** (e.g., revenue, sales quantity, profit) are stored in the **Fact Table**.
- Contains **quantitative data** (measurable values).

### Types of Fact Tables:

1. **Transactional Fact Table**:
    - Stores transactional data (e.g., invoices, orders).
2. **Snapshot Fact Table**:
    - Captures data at specific time intervals (e.g., daily/weekly snapshots).
3. **Accumulating Snapshot Fact Table**:
    - Tracks the progress of a process over time (e.g., order-to-delivery cycle).

### Characteristics of Fact Tables:

- **Granularity**: The level of detail captured in the table (e.g., individual sales vs. monthly aggregates).
- **Additive Measures**: Can be summed across dimensions (e.g., total sales).
- **Semi-Additive Measures**: Can be summed across some dimensions but not all (e.g., account balances).
- **Non-Additive Measures**: Cannot be summed across dimensions (e.g., percentages).

---

## Dimension Table

- **Dimension Table**: Contains descriptive attributes (e.g., product name, customer region) used to analyze facts.
- Provides **context to facts** in the Fact Table.

### Characteristics of Dimension Tables:

- **Primary Key**: Unique identifier for each record.
- Contains **textual data** (e.g., product descriptions, customer demographics).
- Fewer records but **wider table** (more attributes).

### Examples of Dimensions:

1. **Time Dimension**: Year, Month, Day, Quarter, etc.
2. **Product Dimension**: Product ID, Product Name, Category, etc.
3. **Geography Dimension**: Region, Country, State, City, etc.

---

## Data Mining

- **Definition**: Extracting meaningful patterns, knowledge, and insights from large datasets.

### Key Techniques in Data Mining:

1. **Classification**: Categorizing data into predefined classes.
2. **Clustering**: Grouping similar data points without predefined classes.
3. **Association Rule Mining**: Identifying relationships between variables (e.g., market basket analysis).
4. **Regression**: Predicting continuous values (e.g., sales forecasting).
5. **Anomaly Detection**: Identifying outliers or unusual patterns.

### Applications of Data Mining:

- **Retail**: Customer behavior analysis, recommendation systems.
- **Healthcare**: Patient diagnosis prediction, drug discovery.
- **Finance**: Fraud detection, credit scoring.

---

1. **Choose a Business Process**:    
    - Identify a major operational process in the organization that generates raw data.
    - This helps to determine which fact tables are required.
    - Data is typically extracted from legacy systems or company-wide data warehouses.
2. **Choose the Granularity of Fact Tables**:
    - Define the level of detail (granularity) for each dimension in the database.
    - Finer granularity allows for more precise querying.
    - Common granularity levels include individual transactions, line items, daily snapshots, or monthly snapshots.


# Snowflake Schema