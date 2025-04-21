---
Title: Data Warehousing and Mining Lecture 5
Status: 
marker: 
tags: 
Date: 2025.01.17
Time: 10:31
---
# Data Warehousing and Mining Lecture 4

## Data Mart

- **Definition**: A data mart is a departmental subset of a data warehouse that focuses on a single business process.
- **Characteristics**:
    - Departmental
    - Star join schema
    - Optimized for data access and analysis
    - Structured to suit the departmental view

---

## Dimensional Modelling
### Overview
Dimensional modelling determines how data is stored in a data warehouse. It involves identifying data related to business subjects, referred to as dimensions or business dimensions. These dimensions are directly tied to the centralized repository.

### Star Schema
Dimensional modelling is implemented using the **Star Schema**, which is divided into:
1. **Dimensions**
2. **Facts**
- **Fact Tables**: Store quantitative data.
- **Dimension Tables**: Store descriptive information about the data.

The organization of data in a database follows the database model, also known as the **Entity-Relationship (ER) Model**, which includes entities and their relationships.

---

## Dimensions

- **Definition**: Dimensions store descriptions of the characteristics of a business and usually contain descriptive information that qualifies a fact.
- **Key Features**:
    - Dimensions change slowly over time (if at all).

### Key Decisions in Dimensional Modelling

1. Choosing the subjects.
2. Determining the resolution.
3. Identifying and confirming dimensions.
4. Selecting the facts.
5. Deciding on the duration of the database.

---

## Steps to Implement Star Schema

1. Identify the business subject.
2. Identify business dimensions.
3. Identify the facts.
4. Determine granularity.

---

## Facts

- **Definition**: Quantitative data that describe a business subject, typically having fixed values.

---

## Dimension Table

- **Key Features**:
    - Contains the dimension table key.
    - Wide table structure with textual attributes.
    - Attributes are not normalized.
    - Supports drilling down and rolling up to finer or broader levels.
    - May include multiple hierarchies.
    - Typically has fewer records.

---

## Example: Slide Study

### Identifying Subject, Dimensions, Facts, and Granularity

#### Subject: Automaker Sales

#### Dimensions:

1. **Product**:
    
    - Model Name
    - Model Year
    - Package Styling
    - Product Lining
    - Product Category
    - Exterior Color
    - Interior Color
    - First Color
2. **Payment Method**:
    
    - Finance Type
    - Term (months)
    - Interest Rate
    - Agent
3. **Customer Demographics**:
    
    - Age
    - Gender
    - Income Range
    - Marital Status
    - Household Size
    - Vehicles Owned
    - Home Value
    - Own or Rent
4. **Dealer**:
    
    - Dealer Name
    - City
    - State
    - Single Brand Flag
    - Date of First Operation

#### Facts:

- Actual Sale Price
- MSRP Sale Price
- Options Price
- Full Price
- Dealer Add-ons
- Dealer Credits
- Proceeds
- Finance

---

## Key Concepts

- **Drilling Down**: Moving to finer levels of detail.
- **Rolling Up**: Aggregating data to higher levels of detail.

---

## References

- Date: 2025.01.17
- Time: 10:31