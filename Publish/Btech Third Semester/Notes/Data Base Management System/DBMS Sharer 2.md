# File 1 P4
Here’s a markdown-friendly version of your queries with proper separation in code blocks:

```markdown
# Part B:

1. **Create a backup of all the 5 tables. Add a prefix BACKUP_<table name> to the backup table. Perform remaining operations on the backup table.**

```sql
CREATE TABLE BACKUP_DEMO_CUSTOMERS AS SELECT * FROM DEMO_CUSTOMERS;
CREATE TABLE BACKUP_DEMO_ORDERS AS SELECT * FROM DEMO_ORDERS;
CREATE TABLE BACKUP_DEMO_ORDER_ITEMS AS SELECT * FROM DEMO_ORDER_ITEMS;
CREATE TABLE BACKUP_DEMO_PRODUCT_INFO AS SELECT * FROM DEMO_PRODUCT_INFO;
CREATE TABLE BACKUP_DEMO_STATES AS SELECT * FROM DEMO_STATES;
```

2. **Delete all records from the BACKUP_DEMO_CUSTOMERS table where the state is 'GA'.**

```sql
DELETE FROM BACKUP_DEMO_CUSTOMERS WHERE CUST_STATE = 'GA';
```

3. **Delete all orders with an ORDER_TOTAL less than 1000 from the BACKUP_DEMO_ORDERS table.**

```sql
DELETE FROM BACKUP_DEMO_ORDERS WHERE ORDER_TOTAL < 1000;
```

4. **Delete all order items associated with a specific ORDER_ID (e.g., 1001) from the BACKUP_DEMO_ORDER_ITEMS table.**

```sql
DELETE FROM BACKUP_DEMO_ORDER_ITEMS WHERE ORDER_ID = 1001;
```

5. **Update the email address of a customer with CUSTOMER_ID 1 to 'newemail@example.com' in the BACKUP_DEMO_CUSTOMERS table.**

```sql
UPDATE BACKUP_DEMO_CUSTOMERS SET CUST_EMAIL = 'newemail@example.com' WHERE CUSTOMER_ID = 1;
```

6. **Increase the CREDIT_LIMIT of all customers by 500 in the BACKUP_DEMO_CUSTOMERS table.**

```sql
UPDATE BACKUP_DEMO_CUSTOMERS SET CREDIT_LIMIT = CREDIT_LIMIT + 500;
```

7. **Update the ORDER_TOTAL to 0 for all orders with a USER_ID of 2 in the BACKUP_DEMO_ORDERS table.**

```sql
UPDATE BACKUP_DEMO_ORDERS SET ORDER_TOTAL = 0 WHERE USER_ID = 2;
```

8. **Add a new column LOYALTY_POINTS of type NUMBER to the BACKUP_DEMO_CUSTOMERS table.**

```sql
ALTER TABLE BACKUP_DEMO_CUSTOMERS ADD (LOYALTY_POINTS NUMBER);
```

9. **Change the data type of the PRODUCT_NAME column in the BACKUP_DEMO_PRODUCT_INFO table to VARCHAR2(100).**

```sql
ALTER TABLE BACKUP_DEMO_PRODUCT_INFO MODIFY (PRODUCT_NAME VARCHAR2(100));
```

10. **Drop the PHONE_NUMBER2 column from the BACKUP_DEMO_CUSTOMERS table.**

```sql
ALTER TABLE BACKUP_DEMO_CUSTOMERS DROP COLUMN PHONE_NUMBER2;
```

11. **Rename the BACKUP_DEMO_CUSTOMERS table to BACKUP_CUSTOMERS.**

```sql
ALTER TABLE BACKUP_DEMO_CUSTOMERS RENAME TO BACKUP_CUSTOMERS;
```

12. **Rename the BACKUP_DEMO_ORDERS table to BACKUP_ORDERS.**

```sql
ALTER TABLE BACKUP_DEMO_ORDERS RENAME TO BACKUP_ORDERS;
```

13. **Add a primary key constraint to the CUSTOMER_ID column in the BACKUP_CUSTOMERS table.**

```sql
ALTER TABLE BACKUP_CUSTOMERS ADD CONSTRAINT PK_CUSTOMER_ID PRIMARY KEY (CUSTOMER_ID);
```

14. **Add a foreign key constraint to the CUSTOMER_ID column in the BACKUP_ORDERS table referencing the BACKUP_CUSTOMERS table.**

```sql
ALTER TABLE BACKUP_ORDERS
ADD FOREIGN KEY (CUSTOMER_ID)
REFERENCES BACKUP_CUSTOMERS (CUSTOMER_ID);
```

15. **Add a unique constraint to the CUST_EMAIL column in the BACKUP_CUSTOMERS table.**

```sql
ALTER TABLE BACKUP_CUSTOMERS ADD CONSTRAINT UQ_CUST_EMAIL UNIQUE (CUST_EMAIL);
```

16. **Add a check constraint to ensure ORDER_TOTAL in the BACKUP_ORDERS table is greater than 0.**

```sql
ALTER TABLE BACKUP_ORDERS ADD CONSTRAINT CK_ORDER_TOTAL CHECK (ORDER_TOTAL >= 0);
```

17. **Drop the primary key constraint from the BACKUP_CUSTOMERS table.**

```sql
ALTER TABLE BACKUP_CUSTOMERS DROP CONSTRAINT PK_CUSTOMER_ID;
```

18. **Drop the foreign key constraint from the BACKUP_ORDERS table.**

```sql
ALTER TABLE BACKUP_ORDERS DROP CONSTRAINT FK_CUSTOMER_ID;
```

19. **Drop the unique constraint from the CUST_EMAIL column in the BACKUP_CUSTOMERS table.**

```sql
ALTER TABLE BACKUP_CUSTOMERS DROP CONSTRAINT UQ_CUST_EMAIL;
```

20. **Drop the check constraint on ORDER_TOTAL from the BACKUP_ORDERS table.**

```sql
ALTER TABLE BACKUP_ORDERS DROP CONSTRAINT CK_ORDER_TOTAL;
```

21. **Truncate all the backup tables.**

```sql
TRUNCATE TABLE BACKUP_CUSTOMERS;
TRUNCATE TABLE BACKUP_ORDERS;
TRUNCATE TABLE BACKUP_DEMO_ORDER_ITEMS;
TRUNCATE TABLE BACKUP_DEMO_PRODUCT_INFO;
TRUNCATE TABLE BACKUP_DEMO_STATES;
```

22. **Drop all the backup tables.**
```sql
DROP TABLE BACKUP_CUSTOMERS;
DROP TABLE BACKUP_ORDERS;
DROP TABLE BACKUP_DEMO_ORDER_ITEMS;
DROP TABLE BACKUP_DEMO_PRODUCT_INFO;
DROP TABLE BACKUP_DEMO_STATES;

```


# File 2
Here’s the SQL queries in a markdown format with proper code blocks for easy copying and pasting:

```markdown
# Kunj Thakker

### K070 

### BTech Cybersecurity, Sem-3

---

1. **Calculate the total credit limit of all customers.**

```sql
SELECT SUM(CREDIT_LIMIT) AS TOTAL_CREDIT_LIMIT 
FROM DEMO_CUSTOMERS;
```

2. **Find the maximum and minimum list price of products in the DEMO_PRODUCT_INFO table.**

```sql
SELECT MAX(LIST_PRICE) AS MAX_LIST_PRICE, MIN(LIST_PRICE) AS MIN_LIST_PRICE 
FROM DEMO_PRODUCT_INFO;
```

3. **Retrieve all customers whose first name starts with 'J'.**

```sql
SELECT *  
FROM DEMO_CUSTOMERS  
WHERE CUST_FIRST_NAME LIKE 'J%';
```

4. **Find all products whose name contains the word 'Shoes'.**

```sql
SELECT * 
FROM DEMO_PRODUCT_INFO 
WHERE PRODUCT_NAME LIKE '%Shoes%';
```

5. **Retrieve all orders where the USER_ID ends with '2'.**

```sql
SELECT * 
FROM DEMO_ORDERS 
WHERE USER_ID LIKE '%2';
```

6. **Find all customers whose last name has exactly 5 characters.**

```sql
SELECT * 
FROM DEMO_CUSTOMERS 
WHERE LENGTH(CUST_LAST_NAME) = 5;
```

7. **Retrieve all products whose description contains the word 'business', ignoring case sensitivity.**

```sql
SELECT * 
FROM DEMO_PRODUCT_INFO 
WHERE LOWER(PRODUCT_DESCRIPTION) LIKE '%business%';
```

8. **Retrieve all orders made by customers with IDs 1, 2, and 3.**

```sql
SELECT * 
FROM DEMO_ORDERS 
WHERE CUSTOMER_ID IN (1, 2, 3);
```

9. **Find all customers who do not live in the states 'GA', 'NY', and 'CT'.**

```sql
SELECT * 
FROM DEMO_CUSTOMERS 
WHERE CUST_STATE NOT IN ('GA', 'NY', 'CT');
```

10. **Retrieve all products whose category is either 'Womens' or 'Accessories'.**

```sql
SELECT * 
FROM DEMO_PRODUCT_INFO 
WHERE CATEGORY IN ('Womens', 'Accessories');
```

11. **Find all orders that were not placed by customers with IDs 1, 2, and 3.**

```sql
SELECT * 
FROM DEMO_ORDERS 
WHERE CUSTOMER_ID NOT IN (1, 2, 3);
```

12. **Retrieve all orders placed between April 1, 2024, and December 31, 2024.**

```sql
SELECT * 
FROM DEMO_ORDERS 
WHERE ORDER_TIMESTAMP BETWEEN '04-01-2024' AND '12-31-2024';
```

13. **Find all products with a list price between 50 and 100.**

```sql
SELECT * 
FROM DEMO_PRODUCT_INFO 
WHERE LIST_PRICE BETWEEN 50 AND 100;
```

14. **Find all orders with a total amount between 200 and 1000.**

```sql
SELECT * 
FROM DEMO_ORDERS 
WHERE ORDER_TOTAL BETWEEN 200 AND 1000;
```
```

This structure is clean and ready to use in markdown format for easy reference or sharing.