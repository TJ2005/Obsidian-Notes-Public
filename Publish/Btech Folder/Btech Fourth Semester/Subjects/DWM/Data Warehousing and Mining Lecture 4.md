---
Title: Data Warehousing and Mining Lecture 4
Status: 
marker: 
tags: 
Date: 2025.01.10
Time: 10:20
---
# Data Warehousing and Mining Lecture 4

## Difference B/w Operational Systems &  Information System

|                  | Operational                | Informational                 |
| ---------------- | -------------------------- | ----------------------------- |
| Data Context     | Current Values             | Archived Derived Summarized   |
| Data Structure   | Optimized for Transactions | Optimized for complex Queries |
| Access Frequency | High                       | Medium to Low                 |
| Access Type      | Read Update Delete         | Read                          |
| Usage            | Predictable                | Ad Hoc, Random                |
| Response Times   | Sub Seconds                | Several Seconds to minutes    |
| Users            | Large Numbers              | Relatively Small Numbers      |
## Database V/S Data Warehouse
DataBase is an instant of a current data and data warehouse is a history and analysis on the previous data. With this information it is obvious That a database is used more frequently than a Data Warehouse. You can use this analogy to remember this : A user will deposit and withdraw money more frequently, However a user will not analyse data such as their savings record or credit score as frequent as a deposit.
## Properties of Datawarehouse
Data warehouses are subject oriented, Time Invariant and Accessible.
- Subject Oriented :
	- Data Warehouse is not a replacement to DBMS it is a layer above it. That means its use is subjective.
- Integrated Data:
	- Remove Inconsistencies
	- Standardize the various data elements
	- Make sure of the meanings of data names in each source applications
	- Standardization is necessary so the data warehouse can be valid
		- Naming Conventions
		- Codes
		- Data Attributes
		- Measurements
	- File Naming Conventions is a good example of standardization.
	- A file naming convention enables a person to have data sorted already. For example a teacher who names their student's project files with a naming convention has their files sorted and it becomes easy to grade the students. However, Once a naming convention is followed it cannot be defied.
	- Time Variant Data
		- Allows for analysis of the past
		- Relates information to the present
		- Enables forecast
### OLTP 
- Online Transaction processing Refers to the Operational System Handling Data Base Management System.
### OLAP
- Online Analytical Processing Refers to the Informational System Handling Data Warehouse and Data Mining Operations.
## Data Granularity
The term Data Granularity refers to the level of detail that a data has. 
A data can have multiple level of details. 
Data Warehouse have at least two levels of granularity. They are as follows
- Coarse Level 
- Fine Level

## Scenario 1
ABC Pvt. Ltd is a company with branches at Mumbai, Delhi, Chennai and Bangalore.
The Sales Manager quarterly Sales Report.

Each Branch has a Separate Operational System.
![[IMG-20250730000528496.png| 300]]
## Scenario 3
Cakes & Cookies is a small new company Chairman needs analysis and next steps.
- Improve quality of data
- Then Analyse it then chart it and show it to chairman where he thinks of next better steps
- Use query analysis tool to support adhoc queries.

## ETL
Extraction Transformation and Loading
The conversion of Ad hoc data in operational systems needs to be Processed and transformed before transferring it into a data warehouse system.

# References


###### Information
- date: 2025.01.10
- time: 10:20