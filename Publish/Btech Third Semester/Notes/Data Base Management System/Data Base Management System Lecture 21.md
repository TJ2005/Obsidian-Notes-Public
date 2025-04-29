---
Title: Data Base Management System Lecture 9
Status: 
marker:
  - "[[DBMS]]"
  - "[[Data Base]]"
  - "[[Functional Dependency]]"
  - "[[CLosure]]"
tags:
  - BTech
Date: 2024.09.09
Time: 13:12
---
# Functional Dependency in DBMS

In the context of **Database Management Systems (DBMS)**, **Functional Dependency (FD)** is a relationship that exists between two attributes (or sets of attributes) in a database. It is a constraint that describes how one attribute (or a group of attributes) uniquely determines another attribute.

### Key Concept:
If we have a relation (or table) **R**, and two attributes **X** and **Y** from that relation, we say that **Y is functionally dependent on X** (denoted as **X → Y**) if, for every unique value of X, there is exactly one corresponding value of Y.

### Example:
Consider a relation **Students** with the following attributes:
- **StudentID** (Primary Key)
- **StudentName**
- **StudentAddress**

Here, **StudentID → StudentName** means that for each unique **StudentID**, there is a corresponding single **StudentName**. The **StudentID** uniquely determines **StudentName**. If two rows have the same **StudentID**, they must also have the same **StudentName**.

### Types of Functional Dependency:
1. **Trivial Functional Dependency**: 
   - If **Y** is a subset of **X**, then the functional dependency **X → Y** is said to be trivial.
   - Example: If **X = {StudentID, StudentName}** and **Y = {StudentID}**, then **X → Y** is trivial because **Y** is part of **X**.

2. **Non-trivial Functional Dependency**: 
   - If **Y** is not a subset of **X**, then **X → Y** is non-trivial.
   - Example: **StudentID → StudentName** is non-trivial because **StudentName** is not part of **StudentID**.

3. **Full Functional Dependency**: 
   - If removing any attribute from **X** makes the dependency invalid, then **X → Y** is fully functional dependent.
   - Example: If **{StudentID, CourseID} → Grade**, and neither **StudentID → Grade** nor **CourseID → Grade**, then **{StudentID, CourseID} → Grade** is a full functional dependency.

4. **Partial Functional Dependency**: 
   - If a proper subset of **X** can still determine **Y**, then **X → Y** is partially dependent.
   - Example: If **{StudentID, CourseID} → Grade** but **StudentID → Grade**, then **{StudentID, CourseID} → Grade** is a partial dependency.

5. **Transitive Functional Dependency**:
   - If **X → Y** and **Y → Z**, then **X → Z** is a transitive dependency.
   - Example: If **StudentID → DepartmentID** and **DepartmentID → DepartmentName**, then **StudentID → DepartmentName** is a transitive dependency.

### Importance of Functional Dependencies:
Functional dependencies are crucial in:
- **Normalization**: They help in eliminating redundancy and anomalies by splitting tables into smaller tables and establishing relationships through primary and foreign keys.
- **Designing relational schemas**: They ensure that the database follows the desired constraints, improving the overall database structure.

### Conclusion:
Functional dependencies define the relationship between attributes in a relation and are the foundation for database normalization. Understanding them is key to designing efficient and consistent databases.

Let me know if you need more details on any specific type or concept!](<# Data Base Management System Lecture 9

# Closure of a set of functional Dependency
Given a set F set of functional dependencies, there are certain other functional dependencies that are implied by F.
- if $A \rightarrow B$ and $B \rightarrow C$ then $A\rightarrow C$ 
- Like Transitivity
- Represented by $F^+$ 

# Keys and Functional Dependency
- K is a superkey for relation schema R if and only if $K\rightarrow R$
	- Super Key is all combination
	- Every candidate key is a super key
	- Not every super key
	- K 

## Example
Menu has item with $id$ and $name$ and $price$ for which it is being sold.
```sql
select * from menu
where name=IDLI FRY, Price
```
Admission. We all did 12th Science. So we are all super keys. Criteria is 80% so the children with 80% become candidate. Above that we get constraints.

# Trivial Functional Dependencies
A Functional Dependency is **Trivial** if it is satisfied by all instances of relation.
- $id,~name \rightarrow ID$
- $name \rightarrow name$ 
	- Null is subset

# References


###### Information
- date: 2024.09.09
- time: 13:12>)