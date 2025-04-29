---
Title: Data Base Management System Lab 1
Status: 
marker:
  - "[[Btech Second Semester/Notes/Data Base Management System/Data Base Management System|Data Base Management System]]"
  - "[[Data Base]]"
tags: 
Date: 2024-07-18
Time: 2024-07-18T04:00:00
---
# Data Base Management System Lab 1

## Index

1. [Introduction](#introduction)
2. [Content](#content)
   - [Applications](#applications)
   - [Consistency in DBMS](#consistency-in-dbms)
     - [Rolling Back](#rolling-back)
     - [Parallel Calling](#parallel-calling)
     - [Constraints](#constraints)
   - [Purpose](#purpose)
     - [Data Redundancy](#data-redundancy)
     - [Difficulty in Accessing Data](#difficulty-in-accessing-data)
     - [Integrity Problems](#integrity-problems)
     - [Atomicity of Updates](#atomicity-of-updates)
     - [Concurrent Access by Multiple Users](#concurrent-access-by-multiple-users)
     - [Security Problems](#security-problems)
   - [Data Models](#data-models)
     - [Tools](#tools)
     - [Relational Model](#relational-model)
       - [Example](#relational-model-example)
       - [Fields](#fields)
       - [Schema](#schema)
       - [Instances](#instances)
   - [Data Definition Language (DDL)](#data-definition-language-ddl)
   - [Data Manipulation Language (DML)](#data-manipulation-language-dml)
     - [Types of DML](#types-of-dml)
   - [SQL](#sql)
   - [Database Design](#database-design)
     - [Logical Design](#logical-design)
     - [Physical Design](#physical-design)
   - [Components](#components)
   - [Applications](#applications)
     - [Two-Tier Architecture](#two-tier-architecture)
     - [Three-Tier Architecture](#three-tier-architecture)
   - [Database Users](#database-users)
   - [Enigma](#enigma)
     - [Physical Data Independence](#physical-data-independence)
3. [References](#references)


## Introduction
We generated a substantial amount of data, organized it systematically, and then utilized a DBMS for efficient management. This project explores various aspects of DBMS.

## Content

### Applications

### Consistency in DBMS
#### Rolling Back
Mechanism to revert changes to maintain data integrity.

#### Parallel Calling
Executing multiple processes simultaneously to improve efficiency.

#### Constraints
Rules applied to data to maintain accuracy and integrity.

### Purpose
#### Data Redundancy
Reducing duplication of data.

#### Difficulty in Accessing Data
Improving ease of data retrieval.

#### Integrity Problems
Ensuring accuracy and consistency of data over its lifecycle.

#### Atomicity of Updates
Ensuring all parts of a transaction are completed successfully.

#### Concurrent Access by Multiple Users
Handling simultaneous data access by multiple users without conflicts.

#### Security Problems
Protecting data from unauthorized access and breaches.

### Data Models
#### Tools
- Data: Raw information.
- Data Relationships: Connections between data items.
- Data Semantics: Meaning and context of data.
- Data Constraints: Rules and limitations on data.

#### Relational Model
Explains how to relate two databases together.

### Relational Model Example
| ID  | Name | Dept_Name | Salary |
| --- | ---- | --------- | ------ |
| 101 | John | CS        | 70000  |
| 102 | Jane | EE        | 80000  |

Fig 1
#### Fields
ID, Name, Dept_Name, and Salary are attributes called **Fields**.

#### Schema
Defines the structure of the database. For example, the ID field with 5 characters is part of the Schema.

#### Instances
Specific data at a particular moment in time.

### Data Definition Language (DDL)
Specification syntax for defining the database schema. Example:
```sql
CREATE TABLE instructor(
    id CHAR(5),
    name VARCHAR(20),
    dept_name VARCHAR(20),
    salary NUMERIC(8,2)
);
```
DDL Compiler generates table templates stored in the database.

### Data Manipulation Language (DML)
Language for accessing and updating data organized by the data model.
- **DML** is also known as the query language.
- Two classes of DML:
  - Pure: For proving computational power and optimization.
  - Commercial: Used in commercial systems, with SQL being the most widely used.

#### Types of DML
- Procedural DML
- Non-Procedural DML

### SQL
SQL is a non-procedural query language that inputs multiple tables and returns a single table. It is not Turing machine equivalent.

### Database Design
#### Logical Design
Conceptual framework of the database.

#### Physical Design
Actual storage of data in the database.

### Components
- **Storage Manager**
- **Query Processor**
- **Transaction Management Component**

### Applications
#### Two-Tier Architecture
Client-server architecture with two layers.

#### Three-Tier Architecture
Client-server architecture with three layers.

### Database Users
Naive users ( Expand here )

### Enigma

#### Physical Data Independence
Ability to change the physical schema without affecting the logical schema.

## Relevant Information

### Rolling Back
Rolling back in a DBMS is a process where the system reverts changes made during a transaction to maintain data integrity in case of an error or failure. This is crucial for ensuring that only valid and accurate data is stored in the database.

### Parallel Calling
Parallel calling allows multiple processes to execute simultaneously, enhancing the efficiency and performance of the DBMS. This approach is particularly useful in handling large datasets and complex queries.

### Constraints
Constraints are rules applied to the data in a database to ensure data integrity and accuracy. Common types of constraints include primary keys, foreign keys, unique constraints, and check constraints.

### Data Redundancy
Data redundancy involves unnecessary duplication of data within a database. Reducing redundancy helps in optimizing storage, improving performance, and maintaining data consistency.

### Difficulty in Accessing Data
Improving data retrieval methods within a DBMS can significantly enhance user experience and operational efficiency. Techniques such as indexing and optimized queries are often employed to address this issue.

### Integrity Problems
Ensuring the accuracy and consistency of data throughout its lifecycle is critical in a DBMS. Integrity problems can be minimized through the use of constraints, transactions, and proper database design.

### Atomicity of Updates
Atomicity ensures that all parts of a transaction are completed successfully; if any part of the transaction fails, the entire transaction is rolled back. This property is one of the ACID (Atomicity, Consistency, Isolation, Durability) principles in DBMS.

### Concurrent Access by Multiple Users
Handling concurrent access in a DBMS involves managing multiple users accessing the database simultaneously without causing conflicts. Techniques such as locking, transaction management, and isolation levels are used to manage concurrency.

### Security Problems
Protecting data from unauthorized access and breaches is a fundamental aspect of DBMS security. Implementing authentication, authorization, encryption, and auditing measures are essential practices for ensuring data security.

## References

- Date, C. J. (2004). *An Introduction to Database Systems*. Addison-Wesley.
- Silberschatz, A., Korth, H. F., & Sudarshan, S. (2010). *Database System Concepts*. McGraw-Hill.
- Elmasri, R., & Navathe, S. B. (2015). *Fundamentals of Database Systems*. Pearson.