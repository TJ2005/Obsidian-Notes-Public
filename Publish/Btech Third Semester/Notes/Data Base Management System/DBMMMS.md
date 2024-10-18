Here are the SQL commands from the screenshots you uploaded, written in markdown format:

```sql
-- Command 1
SELECT COUNT(*) AS Total_Customers
FROM DEMO_CUSTOMERS;
```

```sql
-- Command 2
SELECT AVG(List_Price) AS Average_List_Price
FROM DEMO_PRODUCT_INFO;
```

```sql
-- Command 3
SELECT SUM(Order_Total) AS Total_Order_Sum
FROM DEMO_ORDERS;
```

```sql
-- Command 4
SELECT MAX(Credit_Limit) AS Highest_Credit_Limit
FROM DEMO_CUSTOMERS;
```

```sql
-- Command 5
SELECT MIN(Order_Total) AS Lowest_Order_Total
FROM DEMO_ORDERS;
```

```sql
-- Command 6
SELECT PRODUCT_ID, ROUND(List_Price) AS Rounded_List_Price
FROM DEMO_PRODUCT_INFO;
```

```sql
-- Command 7
SELECT SYSDATE AS Current_Date_Time
FROM Dual;
```

```sql
-- Command 8
SELECT Order_ID, EXTRACT(YEAR FROM Order_Timestamp) AS Order_Year
FROM DEMO_ORDERS;
```

```sql
-- Command 9
SELECT Order_ID, Order_Timestamp, 
       Order_Timestamp + INTERVAL '30' DAY AS New_Timestamp
FROM DEMO_ORDERS;
```

```sql
-- Command 10
SELECT *
FROM DEMO_Orders
ORDER BY Order_Total DESC;
```

```sql
-- Command 11
SELECT Product_ID, SUM(Unit_Price * Quantity) AS Total_Sales_Amount
FROM DEMO_ORDER_ITEMS
GROUP BY Product_ID;
```

```sql
-- Command 12
SELECT Customer_ID, COUNT(*) AS Number_of_Orders
FROM DEMO_ORDERS
GROUP BY Customer_ID;
```

```sql
-- Command 13
SELECT Customer_ID, COUNT(*) AS Number_of_Orders
FROM DEMO_ORDERS
GROUP BY Customer_ID
HAVING COUNT(*) > 5;
```

```sql
-- Command 14
SELECT Product_ID, SUM(Quantity) AS Total_Ordered
FROM DEMO_ORDER_ITEMS
GROUP BY Product_ID
HAVING SUM(Quantity) > 10;
```

Let me know if you need further assistance!