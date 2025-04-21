It looks like you've provided an image with an ER diagram and some SQL-related tasks. I'll help you write SQL queries based on the provided diagram.

### 1. Retrieve all records from the `DEMO_CUSTOMERS` table:
```sql
SELECT * FROM DEMO_CUSTOMERS;
```

### 2. Retrieve the first name, last name, and email of all customers:
```sql
SELECT CUST_FIRST_NAME, CUST_LAST_NAME, CUST_EMAIL FROM DEMO_CUSTOMERS;
```

### 3. Retrieve all distinct states from the `DEMO_CUSTOMERS` table:
```sql
SELECT DISTINCT CUST_STATE FROM DEMO_CUSTOMERS;
```

### 4. Retrieve the order ID, customer ID, and order total for all orders sorted by order total in descending order:
```sql
SELECT ORDER_ID, CUSTOMER_ID, ORDER_TOTAL 
FROM DEMO_ORDERS 
ORDER BY ORDER_TOTAL DESC;
```

### 5. Find the total number of orders placed by each customer:
```sql
SELECT CUSTOMER_ID, COUNT(*) AS TOTAL_ORDERS 
FROM DEMO_ORDERS 
GROUP BY CUSTOMER_ID;
```

### 6. Calculate the average order total for each customer:
```sql
SELECT CUSTOMER_ID, AVG(ORDER_TOTAL) AS AVERAGE_ORDER_TOTAL 
FROM DEMO_ORDERS 
GROUP BY CUSTOMER_ID;
```

### 7. Retrieve all product names and their total quantities sold:
```sql
SELECT P.PRODUCT_NAME, SUM(OI.QUANTITY) AS TOTAL_QUANTITY_SOLD 
FROM DEMO_PRODUCT_INFO P 
JOIN DEMO_ORDER_ITEMS OI ON P.PRODUCT_ID = OI.PRODUCT_ID 
GROUP BY P.PRODUCT_NAME;
```

### 8. Find the highest order total in the `DEMO_ORDERS` table:
```sql
SELECT MAX(ORDER_TOTAL) AS HIGHEST_ORDER_TOTAL 
FROM DEMO_ORDERS;
```

### 9. Retrieve the name and price of all products that cost more than $50:
```sql
SELECT PRODUCT_NAME, LIST_PRICE 
FROM DEMO_PRODUCT_INFO 
WHERE LIST_PRICE > 50;
```

### 10. Find the total sales amount for each product (unit price multiplied by quantity):
```sql
SELECT P.PRODUCT_NAME, SUM(OI.UNIT_PRICE * OI.QUANTITY) AS TOTAL_SALES_AMOUNT 
FROM DEMO_PRODUCT_INFO P 
JOIN DEMO_ORDER_ITEMS OI ON P.PRODUCT_ID = OI.PRODUCT_ID 
GROUP BY P.PRODUCT_NAME;
```

### 11. Retrieve the user name and the total number of orders processed by each user:
```sql
SELECT U.USER_NAME, COUNT(O.ORDER_ID) AS TOTAL_ORDERS_PROCESSED 
FROM DEMO_USER U 
JOIN DEMO_ORDERS O ON U.USER_ID = O.USER_ID 
GROUP BY U.USER_NAME;
```

### 12. Create a backup table `CUSTOMER_BACKUP` containing all records from the `DEMO_CUSTOMERS` table:
```sql
CREATE TABLE CUSTOMER_BACKUP AS 
SELECT * FROM DEMO_CUSTOMERS;
```

### 13. Insert data from the `DEMO_CUSTOMERS` table into the `CUSTOMER_BACKUP` table:
```sql
INSERT INTO CUSTOMER_BACKUP 
SELECT * FROM DEMO_CUSTOMERS;
```

### 14. Retrieve the total number of unique customers from the `DEMO_ORDERS` table:
```sql
SELECT COUNT(DISTINCT CUSTOMER_ID) AS TOTAL_UNIQUE_CUSTOMERS 
FROM DEMO_ORDERS;
```

### 15. Retrieve all orders placed in the year 2023:
```sql
SELECT * FROM DEMO_ORDERS 
WHERE EXTRACT(YEAR FROM ORDER_TIMESTAMP) = 2023;
```

Let me know if you need any more assistance!