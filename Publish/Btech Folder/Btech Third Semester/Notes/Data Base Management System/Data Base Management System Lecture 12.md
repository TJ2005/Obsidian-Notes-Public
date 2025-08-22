---
Title: Data Base Management System Lecture 12
Status: 
marker:
  - "[[Normalization]]"
  - "[[Data Base]]"
  - "[[Normal FOrms]]"
tags:
  - BTech
Date: 2024.09.23
Time: 13:13
---
# Data Base Management System Lecture 12

# Normalization
Normalization is the organization of data to reduce redundancy and ensure data integrity. It involves refining the data into smaller data bases. Dividing the table into smaller tables which are inter related. It makes the data more efficient and easier to maintain.
### Objectives of Normalization:
1. **Eliminate redundant data**: Avoid storing the same piece of data in more than one place.
2. **Ensure data dependencies make sense**: Organize data so that each piece of information is stored in the right place and related correctly.
3. **Improve data integrity**: Reduce the likelihood of data anomalies, which can occur when inserting, updating, or deleting data.

### Normal Forms:
Normalization is done in stages, referred to as **normal forms (NF)**. Each stage builds upon the previous one, progressively organizing the data more efficiently.

1. **First Normal Form (1NF)**:
   - A table is in 1NF if:
     - All columns contain atomic values (indivisible units, no repeating groups).
     - Each record (row) is unique, identified by a **primary key**.
   - **Example**:
     - A table where each cell holds a single value, and there are no multiple values in a single column (no arrays or lists in a column).

2. **Second Normal Form (2NF)**:
   - A table is in 2NF if:
     - It is in 1NF.
     - All **non-key** attributes are fully functionally dependent on the **primary key** (i.e., no partial dependency on part of the composite primary key).
   - **Example**:
     - If a table has a composite primary key (more than one field), every non-key field must depend on the **whole key** and not just a part of it.

3. **Third Normal Form (3NF)**:
   - A table is in 3NF if:
     - It is in 2NF.
     - There are **no transitive dependencies** (i.e., no non-key attribute should depend on another non-key attribute).
   - **Example**:
     - In a table, if A depends on B and B depends on C, there is a transitive dependency. In 3NF, this is eliminated by splitting the table into two related tables.

4. **Boyce-Codd Normal Form (BCNF)**:
   - A stronger version of 3NF, where even more restrictive rules on dependencies are enforced. Any anomaly left after applying 3NF would be corrected by BCNF.

### Benefits of Normalization:
- **Reduced Data Redundancy**: Ensures that data is stored in one place, reducing the need for duplicate entries.
- **Improved Data Integrity**: Helps maintain consistency, especially when updating, inserting, or deleting data.
- **Easier Maintenance**: Well-structured databases are easier to modify and maintain over time.

### Trade-offs:
- **Performance**: Normalization can result in many tables, leading to slower query performance, especially for complex queries requiring multiple table joins.
- **Denormalization**: In some cases, databases are denormalized (the reverse process) to improve performance by reducing the number of joins required, though this introduces redundancy.

### Example:
Consider a table storing information about students and their courses:

#### Unnormalized Data:
| StudentID | StudentName | Course1 | Course2 |
|-----------|-------------|---------|---------|
| 101       | Alice       | Math    | English |
| 102       | Bob         | Science | Math    |

#### 1NF (Atomic values):
| StudentID | StudentName | Course  |
|-----------|-------------|---------|
| 101       | Alice       | Math    |
| 101       | Alice       | English |
| 102       | Bob         | Science |
| 102       | Bob         | Math    |

#### 2NF (Remove partial dependencies):
| StudentID | StudentName |
|-----------|-------------|
| 101       | Alice       |
| 102       | Bob         |

| StudentID | Course  |
|-----------|---------|
| 101       | Math    |
| 101       | English |
| 102       | Science |
| 102       | Math    |

#### 3NF (Remove transitive dependencies):
If student department information is added, it should be in a separate table rather than duplicating it in every row.

In conclusion, **normalization** optimizes database design by organizing tables to avoid redundancy and improve efficiency, ensuring that the database remains clean, consistent, and easily maintainable.



# References


###### Information
- date: 2024.09.23
- time: 13:13