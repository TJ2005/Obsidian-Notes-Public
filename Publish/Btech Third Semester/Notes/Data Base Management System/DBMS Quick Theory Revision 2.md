---
Title: "DBMS Cheat Sheet to study"
Status: 
marker: 
tags: 
Date: "2025.02.18"
Time: "09:06"
---
# DBMS Theory
Let's break down each of these concepts related to database management systems (DBMS) and database design:

### Database Management System (DBMS)

**Definition:**
A DBMS is a software system that uses a standard method of cataloging, retrieving, and running queries on data. The DBMS manages incoming data, organizes it, and provides ways for the data to be modified or extracted by users or other programs.

**Why DBMS:**
- **Data Sharing:** Allows multiple users to access and share data.
- **Data Security:** Provides mechanisms to ensure data is secure from unauthorized access.
- **Data Integrity:** Ensures that data is accurate and consistent.
- **Data Independence:** Changes in data storage do not affect applications that use the data.
- **Backup and Recovery:** Facilitates data backup and recovery in case of failures.

### Database Administrator (DBA)

**Definition:**
A DBA is responsible for the performance, integrity, and security of a database. They are also involved in the planning and development of the database and troubleshooting any issues on behalf of the users.

**Functions of a DBA:**
- **Installation and Upgrade:** Installing and upgrading the DBMS software.
- **Database Design:** Designing the database schema.
- **Performance Monitoring:** Ensuring the database performs optimally.
- **Backup and Recovery:** Implementing backup and recovery procedures.
- **Security Management:** Managing user access and permissions.
- **Troubleshooting:** Diagnosing and resolving database-related issues.

### Schema

**Definition:**
A schema is the structure of a database, described in a formal language supported by the DBMS. It defines the tables, fields, relationships, views, indexes, and other elements.

### Entity-Relationship (ER) Diagram

**Definition:**
An ER diagram is a visual representation of the data and the relationships between different entities in a database.

**Full Form:**
- **Entity:** An object or thing in the real world that is distinguishable from other objects.
- **Relationship:** An association between entities.
- **Attributes:** Properties or details about an entity.

### Attributes

**Definition:**
Attributes are the properties or details of an entity. For example, an entity "Student" might have attributes like "StudentID," "Name," and "DateOfBirth."

### Keys

**Primary Key:**
- A primary key is a unique identifier for a record in a table. It must contain unique values and cannot contain NULLs.

**Candidate Key:**
- A candidate key is a set of attributes that can qualify as a primary key. A table can have multiple candidate keys, but only one can be chosen as the primary key.

**Determinants:**
- In the context of databases, a determinant is an attribute (or set of attributes) that determines the value of another attribute. This concept is often used in normalization to eliminate redundancy.

### Other Components

- **Foreign Key:** A field (or collection of fields) in one table that uniquely identifies a row of another table. It is used to establish and enforce a link between the data in the two tables.
- **Index:** A data structure that improves the speed of data retrieval operations on a database table at the cost of additional writes and storage space to maintain the index data structure.
- **View:** A virtual table based on the result set of an SQL query. A view contains rows and columns, just like a real table.
- **Normalization:** The process of organizing data to reduce redundancy and improve data integrity.

### DML vs. DDL

| **Feature** | **DML (Data Manipulation Language)** | **DDL (Data Definition Language)** |
|------------|---------------------------------|--------------------------------|
| **Purpose** | Used to manipulate data within database objects (tables, views, etc.). | Used to define and modify the structure of database objects. |
| **Examples** | `SELECT`, `INSERT`, `UPDATE`, `DELETE` | `CREATE`, `ALTER`, `DROP` |
| **Persistence** | Changes data but does not alter the schema of the database. | Alters the schema of the database permanently. |
| **Impact** | Affects the data contained within the database. | Affects the structure of the database itself. |
| **Usage** | Frequently used in day-to-day operations to manage and retrieve data. | Used during database design and maintenance to define and modify structures. |
| **Transaction Control** | Can be rolled back if part of a transaction. | Typically auto-committed and cannot be rolled back. |
| **Scope** | Operates on the data within tables, views, etc. | Operates on the structure of tables, indexes, schemas, etc. |
| **Security** | Requires permissions to manipulate data. | Requires higher-level permissions to alter database structures. |

### Key Points

- **DML** is focused on the data itself, allowing users to insert, update, delete, and retrieve records from the database. It is essential for everyday database operations and interactions.

- **DDL** is concerned with the structure of the database, defining how data is organized and managed. It includes commands to create, modify, and delete database objects like tables and indexes.

Both DML and DDL are crucial components of SQL, serving different purposes in database management and operation.



### ACID Properties

ACID properties ensure reliable database transactions:

1. **Atomicity**:
   - **Definition**: All-or-nothing rule for transactions.
   - **Keywords**: Complete or rollback, data integrity.
   - **Example**: Bank transfer completes fully or not at all.

2. **Consistency**:
   - **Definition**: Transactions maintain database rules.
   - **Keywords**: Valid state, constraints, invariants.
   - **Example**: Account balance constraints upheld.

3. **Isolation**:
   - **Definition**: Transactions execute independently.
   - **Keywords**: Concurrency control, no interference.
   - **Example**: One transaction cannot affect another until complete.

4. **Durability**:
   - **Definition**: Committed transactions are permanent.
   - **Keywords**: Persistence, recovery, system failure.
   - **Example**: Completed transactions survive system crashes.

### Importance

- **Data Integrity**: Maintains accurate and reliable data.
- **Concurrency Control**: Manages simultaneous transactions.
- **Recovery**: Ensures data persistence post-failure.

These properties are crucial for reliable database management, especially in critical environments.


### **Normalization in Database Management Systems (DBMS)**

Normalization is the process of organizing a database to reduce redundancy and improve data integrity. Different **normal forms (NF)** exist to ensure better database design.

---

## **1NF (First Normal Form)**

### **Definition**:

A relation is in **1NF** if:

1. Each column contains **atomic (indivisible) values**.
2. Each column contains values of a **single type**.
3. Each row is **uniquely identifiable** (must have a **primary key**).

### **Example (Before 1NF - Unnormalized Table)**

|Student_ID|Student_Name|Courses|
|---|---|---|
|101|John|Math, Science|
|102|Alice|English, Math|

🚨 **Problem**: The "Courses" column contains **multiple values** (not atomic).

### **Example (After 1NF - Converted Table)**

|Student_ID|Student_Name|Course|
|---|---|---|
|101|John|Math|
|101|John|Science|
|102|Alice|English|
|102|Alice|Math|

✅ **Fix**: We created **separate rows** for each course.

---

## **2NF (Second Normal Form)**

### **Definition**:

A relation is in **2NF** if:

4. It is already in **1NF**.
5. **No partial dependency** exists (i.e., no non-key attribute should depend on part of a composite key).

### **Example (Before 2NF - Partial Dependency Exists)**

**Table: Student_Course**

|Student_ID|Course|Student_Name|Instructor|
|---|---|---|---|
|101|Math|John|Mr. A|
|101|Science|John|Ms. B|
|102|English|Alice|Mr. C|

🚨 **Problem**:

- **Primary Key** = (Student_ID, Course).
- **Student_Name** depends **only** on **Student_ID**, **not on Course** → **Partial Dependency!**

### **Example (After 2NF - Remove Partial Dependency)**

✅ **Break into two tables**:

1️⃣ **Student Table**

|Student_ID|Student_Name|
|---|---|
|101|John|
|102|Alice|

2️⃣ **Student_Course Table**

|Student_ID|Course|Instructor|
|---|---|---|
|101|Math|Mr. A|
|101|Science|Ms. B|
|102|English|Mr. C|

✅ **Fix**: Now, **Student_Name** is fully dependent on **Student_ID**, and Instructor is dependent on Course.

---

## **3NF (Third Normal Form)**

### **Definition**:

A relation is in **3NF** if:

6. It is already in **2NF**.
7. **No transitive dependency exists** (i.e., a non-key attribute should not depend on another non-key attribute).

### **Example (Before 3NF - Transitive Dependency Exists)**

|Student_ID|Student_Name|Course|Instructor|Instructor_Age|
|---|---|---|---|---|
|101|John|Math|Mr. A|45|
|101|John|Science|Ms. B|38|
|102|Alice|English|Mr. C|50|

🚨 **Problem**:

- **Instructor_Age** depends on **Instructor**, not directly on **Student_ID or Course** → **Transitive Dependency!**

### **Example (After 3NF - Remove Transitive Dependency)**

✅ **Break into two tables**:

1️⃣ **Student_Course Table**

|Student_ID|Course|Instructor|
|---|---|---|
|101|Math|Mr. A|
|101|Science|Ms. B|
|102|English|Mr. C|

2️⃣ **Instructor Table**

|Instructor|Instructor_Age|
|---|---|
|Mr. A|45|
|Ms. B|38|
|Mr. C|50|

✅ **Fix**: Now, **Instructor_Age** depends only on **Instructor**.

---

## **BCNF (Boyce-Codd Normal Form)**

### **Definition**:

A relation is in **BCNF** if:

8. It is already in **3NF**.
9. **Every determinant is a candidate key** (i.e., no non-trivial functional dependency exists where a non-key attribute determines another attribute).

### **Example (Before BCNF - Violation Exists)**

|Professor|Course|Department|
|---|---|---|
|Dr. A|Math|Science|
|Dr. B|History|Arts|
|Dr. A|Physics|Science|

🚨 **Problem**:

- **Professor → Department**, but **Professor** is not a candidate key.
- This violates **BCNF**.

### **Example (After BCNF - Fix the Violation)**

✅ **Break into two tables**:

1️⃣ **Professor_Department Table**

|Professor|Department|
|---|---|
|Dr. A|Science|
|Dr. B|Arts|

2️⃣ **Course_Assignment Table**

|Course|Professor|
|---|---|
|Math|Dr. A|
|History|Dr. B|
|Physics|Dr. A|

✅ **Fix**: Now, each determinant is a **candidate key**.

---

## **4NF (Fourth Normal Form)**

### **Definition**:

A relation is in **4NF** if:

10. It is already in **BCNF**.
11. **No multi-valued dependencies exist** (i.e., no attribute depends on multiple independent values).

### **Example (Before 4NF - Multi-Valued Dependency Exists)**

|Student|Hobby|Language|
|---|---|---|
|John|Music|English|
|John|Painting|English|
|John|Music|French|
|Alice|Dancing|Spanish|
|Alice|Dancing|English|

🚨 **Problem**:

- **Hobby** and **Language** are **independent** properties of **Student**.
- This causes **multi-valued dependency**.

### **Example (After 4NF - Remove Multi-Valued Dependency)**

✅ **Break into two tables**:

1️⃣ **Student_Hobby Table**

|Student|Hobby|
|---|---|
|John|Music|
|John|Painting|
|Alice|Dancing|

2️⃣ **Student_Language Table**

|Student|Language|
|---|---|
|John|English|
|John|French|
|Alice|Spanish|
|Alice|English|

✅ **Fix**: Now, **each table contains only one independent relationship**.

---

## **Summary Table**

|**Normal Form**|**Condition**|
|---|---|
|**1NF**|No multi-valued attributes (Atomic values).|
|**2NF**|No **partial dependency** (Every non-key attribute depends on the whole primary key).|
|**3NF**|No **transitive dependency** (A non-key attribute should not depend on another non-key attribute).|
|**BCNF**|Every **determinant** must be a **candidate key**.|
|**4NF**|No **multi-valued dependencies**.|

---

Let me know if you need any clarifications! 🚀
# References


###### Information
- date: 2025.02.18
- time: 09:06