SQL operations encompass a wide range of commands and functionalities used to interact with and manipulate data in a database. Here’s an organized overview of the major SQL operations:

---

## 1. **Data Definition Language (DDL) Operations**
DDL operations define and modify the structure of database objects.

### **Creating Database Objects**
- **`CREATE DATABASE`**: Creates a new database.
  ```sql
  CREATE DATABASE my_database;
  ```

- **`CREATE TABLE`**: Defines a new table and its columns.
  ```sql
  CREATE TABLE employees (
      employee_id INT PRIMARY KEY,
      first_name VARCHAR(50),
      last_name VARCHAR(50),
      hire_date DATE
  );
  ```

- **`CREATE VIEW`**: Defines a virtual table based on the result of a query.
  ```sql
  CREATE VIEW employee_summary AS
  SELECT employee_id, first_name, last_name
  FROM employees;
  ```

### **Modifying Database Objects**
- **`ALTER DATABASE`**: Modifies database properties or options.
  ```sql
  ALTER DATABASE my_database MODIFY FILE (NAME = mydata, SIZE = 10MB);
  ```

- **`ALTER TABLE`**: Changes the structure of an existing table.
  ```sql
  ALTER TABLE employees ADD department_id INT;
  ```

- **`ALTER VIEW`**: Modifies the definition of an existing view.
  ```sql
  CREATE OR ALTER VIEW employee_summary AS
  SELECT employee_id, first_name, last_name, hire_date
  FROM employees;
  ```

### **Removing Database Objects**
- **`DROP DATABASE`**: Deletes an existing database and all its objects.
  ```sql
  DROP DATABASE my_database;
  ```

- **`DROP TABLE`**: Deletes an existing table and its data.
  ```sql
  DROP TABLE employees;
  ```

- **`DROP VIEW`**: Removes an existing view.
  ```sql
  DROP VIEW employee_summary;
  ```

- **`TRUNCATE TABLE`**: Removes all rows from a table but keeps its structure.
  ```sql
  TRUNCATE TABLE employees;
  ```

## 2. **Data Manipulation Language (DML) Operations**
DML operations are used to query and modify data within tables.

### **Querying Data**
- **`SELECT`**: Retrieves data from one or more tables.
  ```sql
  SELECT first_name, last_name FROM employees;
  ```

- **`JOIN`**: Combines rows from two or more tables based on a related column.
  ```sql
  SELECT employees.first_name, departments.department_name
  FROM employees
  INNER JOIN departments ON employees.department_id = departments.department_id;
  ```

- **`WHERE`**: Filters rows based on a condition.
  ```sql
  SELECT * FROM employees WHERE hire_date > '2020-01-01';
  ```

- **`GROUP BY`**: Groups rows sharing a property and allows aggregate functions on these groups.
  ```sql
  SELECT department_id, COUNT(*) AS employee_count
  FROM employees
  GROUP BY department_id;
  ```

- **`HAVING`**: Filters groups based on a condition (used with `GROUP BY`).
  ```sql
  SELECT department_id, COUNT(*) AS employee_count
  FROM employees
  GROUP BY department_id
  HAVING COUNT(*) > 10;
  ```

- **`ORDER BY`**: Sorts the result set based on one or more columns.
  ```sql
  SELECT * FROM employees ORDER BY hire_date DESC;
  ```

### **Inserting Data**
- **`INSERT INTO`**: Adds new rows to a table.
  ```sql
  INSERT INTO employees (employee_id, first_name, last_name, hire_date)
  VALUES (1, 'John', 'Doe', '2024-08-26');
  ```

### **Updating Data**
- **`UPDATE`**: Modifies existing rows in a table.
  ```sql
  UPDATE employees
  SET department_id = 2
  WHERE employee_id = 1;
  ```

### **Deleting Data**
- **`DELETE`**: Removes rows from a table based on a condition.
  ```sql
  DELETE FROM employees WHERE employee_id = 1;
  ```

## 3. **Data Control Language (DCL) Operations**
DCL operations manage user permissions and access controls.

- **`GRANT`**: Provides specific privileges to users or roles.
  ```sql
  GRANT SELECT, INSERT ON employees TO user1;
  ```

- **`REVOKE`**: Removes specific privileges from users or roles.
  ```sql
  REVOKE INSERT ON employees FROM user1;
  ```

## 4. **Transaction Control Operations**
Transaction control operations manage the changes made by DML operations, ensuring data integrity.

- **`BEGIN TRANSACTION`**: Starts a new transaction.
  ```sql
  BEGIN TRANSACTION;
  ```

- **`COMMIT`**: Saves all changes made during the current transaction.
  ```sql
  COMMIT;
  ```

- **`ROLLBACK`**: Reverts all changes made during the current transaction.
  ```sql
  ROLLBACK;
  ```

- **`SAVEPOINT`**: Sets a point within a transaction to which you can roll back.
  ```sql
  SAVEPOINT savepoint_name;
  ```

- **`SET TRANSACTION`**: Configures the properties of a transaction (e.g., isolation level).
  ```sql
  SET TRANSACTION ISOLATION LEVEL READ COMMITTED;
  ```

## 5. **Procedural Extensions**
Procedural SQL extensions, such as PL/SQL (Oracle) or T-SQL (SQL Server), include additional operations for more complex logic and control flow.

- **`BEGIN...END`**: Defines a block of statements to be executed together.
  ```sql
  BEGIN
      -- SQL statements
  END;
  ```

- **`IF...ELSE`**: Executes statements conditionally.
  ```sql
  IF condition THEN
      -- SQL statements
  ELSE
      -- SQL statements
  END IF;
  ```

- **`LOOP`**: Iterates over a set of statements.
  ```sql
  LOOP
      -- SQL statements
  END LOOP;
  ```

- **`DECLARE`**: Defines variables and cursors.
  ```sql
  DECLARE
      variable_name data_type;
  BEGIN
      -- SQL statements
  END;
  ```
