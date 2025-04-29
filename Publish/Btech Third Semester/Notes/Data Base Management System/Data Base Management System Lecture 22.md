---
Title: Data Base Management System Lecture 8
Status: 
marker: 
tags: 
Date: 2024.08.26
Time: 13:11
---
# Database Management System - Lecture 8

## Metadata
Metadata refers to data about the data. It provides information about the structure and characteristics of the data in the database. For example, when you create a table, the definition of the table and its schema is part of the metadata.

## Data Definition Language (DDL)
DDL is used for defining and managing the structure of database objects. It includes commands for:
- **Creating Tables**: Defining the schema and structure of tables.
- **Defining Integrity Constraints**: Specifying rules to maintain data accuracy and integrity.
- **Defining Views**: Creating virtual tables based on the result of a query.
- **Managing Transactions**: Commands for starting and ending transactions.

## Data Manipulation Language (DML)
DML provides commands for querying and manipulating data within the database. It includes:
- **Querying Information**: Retrieving data from the database.
- **Inserting Tuples**: Adding new data records.
- **Deleting Tuples**: Removing existing data records.
- **Modifying Tuples**: Updating existing data records.

## Integrity Constraints
Integrity constraints are rules that ensure data accuracy and consistency. They are part of DDL and include:
- **Primary Key Constraints**: Ensure uniqueness of each row.
- **Foreign Key Constraints**: Maintain referential integrity between tables.
- **Unique Constraints**: Ensure uniqueness of values in specific columns.
- **Check Constraints**: Enforce domain-specific rules on column values.
- **Not Null Constraints**: Ensure that certain columns do not accept NULL values.
- **Default Constraints**: Provide default values for columns when no value is specified.

## Transaction Control
Transaction control commands manage transactions in the database to ensure data integrity during operations. Key commands include:
- **BEGIN TRANSACTION**: Start a new transaction.
- **COMMIT**: Save changes made during the transaction.
- **ROLLBACK**: Revert changes made during the transaction.

## Embedded SQL and Dynamic SQL
- **Embedded SQL**: Allows SQL statements to be included within general-purpose programming languages.
- **Dynamic SQL**: Enables the construction and execution of SQL statements at runtime.

## Authorization
Authorization involves granting and managing permissions to users, defining who can access and modify the database and its objects.

## Domain Types in SQL
Domain types define the type and constraints of data that can be stored in columns. Common domain types include:
- **CHAR(n)**: Fixed-length character data with a specified length \( n \).
- **VARCHAR(n)**: Variable-length character data with a maximum length \( n \).
## All operations within SQL
Refer [[SQL Operations]]

## Self Join and Referencing
### Self Join

A self join is a type of join that is used to combine and relate rows within the same table. It is a powerful technique for querying hierarchical or recursive relationships where a table needs to be joined with itself. This is particularly useful for scenarios where you want to compare rows within a single table based on certain criteria or to explore relationships between rows.

#### **Concept**

In a self join, a table is joined with itself, which means you need to use table aliases to distinguish between the different instances of the same table. This allows you to perform comparisons between rows within the same table.

#### **Syntax**

The basic syntax for a self join is:

```sql
SELECT a.column1, a.column2, b.column1, b.column2
FROM table_name a
JOIN table_name b
ON a.common_column = b.common_column
WHERE some_condition;
```

- `table_name a` and `table_name b`: The same table referred to with different aliases.
- `a.common_column = b.common_column`: The condition to join the table with itself, based on related columns.
- `some_condition`: Optional condition to filter results.

#### **Example**

Consider an `employees` table where each employee has a `manager_id` that refers to the `employee_id` of their manager. To find out which employees report to the same manager, you can use a self join.

**Table: employees**

| employee_id | first_name | last_name | manager_id |
|-------------|------------|-----------|------------|
| 1           | John       | Doe       | NULL       |
| 2           | Jane       | Smith     | 1          |
| 3           | Emily      | Johnson   | 1          |
| 4           | Mike       | Brown     | 2          |

To find employees who report to the same manager, you can write a self join query as follows:

```sql
SELECT e1.employee_id AS employee_id1, e1.first_name AS employee1, e2.employee_id AS employee_id2, e2.first_name AS employee2, e1.manager_id
FROM employees e1
JOIN employees e2
ON e1.manager_id = e2.manager_id
WHERE e1.employee_id <> e2.employee_id;
```

**Result:**

| employee_id1 | employee1 | employee_id2 | employee2 | manager_id |
|--------------|-----------|--------------|-----------|------------|
| 2            | Jane      | 3            | Emily     | 1          |
| 3            | Emily     | 2            | Jane      | 1          |

#### **Use Cases**

1. **Hierarchical Data**: Useful for exploring hierarchical relationships, such as employee-manager relationships.
2. **Comparing Rows**: Helps in comparing rows within the same table, for example, to find duplicate records or related items.
3. **Recursive Queries**: Can be part of recursive queries for complex hierarchies or network structures.

#### **Considerations**

- **Performance**: Self joins can be resource-intensive, especially with large tables, so ensure appropriate indexing.
- **Readability**: Using clear aliases and documenting the purpose of the self join can help maintain readability and understanding of the query.
In summary, a self join is a useful SQL operation for querying hierarchical and recursive relationships within a single table, providing insights into how rows within the same table relate to each other.
## 
---

### Information
- **Date**: 2024.08.26
- **Time**: 13:11
