##### For the DEMO_CUSTOMER Databse in Oracle XE
![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdApG1TAM9JUYUBYoFFMYuMfcXlPA7pS1NFtb6IVZD0Ky2Rq_JJv5Lrd_mbsmev_XHHbQMFB8bB_fLuG8OI7xW0EpKo3huNu8IiBliPgM8w9sZVvLZS8OYyqZg_XI5YCWYHciOQNsCUhPmoqnqXkHl6C9y67u4-sxgI6rs4?key=oTwoGBJd1F64LAoLwzYFLA)
##### 1. Retrieve all records from the DEMO_CUSTOMERS table.
```sql
select * from DEMO_CUSTOMERS
```
![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXesC7slGC2OW98j-caxq5iQN61t3AqZe5RNf0YMMYCygmbL0rBku0UeV84thwmfG7rWs016hnciYztqOWneXK8cY_JkkKVFvjc7PU4FBIt8RRjSsnErwZ7PCHkXpuR07SEjdGWccPtFDNCl-6V6MLdKLkoCmFeUL-oHlQ-ifQ?key=oTwoGBJd1F64LAoLwzYFLA)
##### 2. Retrieve the first name, last name, and email of all customers.
```sql
select CUST_FIRST_NAME, CUST_LAST_NAME, CUST_EMAIL from DEMO_CUSTOMERS
```
![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfdmyloHxpPfNU6H52I3SkM3dKv0c9a8Iii_yDl3YJZeXqoZmPDOzhgZvl5qsszcY7Ww5jfF7Q3mTWoiCBwU589m6WODwXM4ELWONH1cGHKGdoo_cffjVp5gtBLju7PZOEn-v_asepi6OtBhVXnqOxNIPzAiAtHIH65cPfhbA?key=oTwoGBJd1F64LAoLwzYFLA)
##### 3. Retrieve all distinct states from the DEMO_CUSTOMERS table.
```sql
select distinct CUST_STATE from DEMO_CUSTOMERS
```

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcCCjKDhO8PKvAc0EQ89y4RSLNYu_C55bhnhhy_A8RiAASCDUV2Gf7dWbUPEM7n8gipv6fnThfsrS1_MVhkYHWhGx2jwUo3-EnEkh1O81Kt7c9bIw-EUxsBz01NGNGtVSV3LzE1aYWY-a_Grtff-1GGzwNKG0fEwq2nt4FgKQ?key=oTwoGBJd1F64LAoLwzYFLA)
##### 4. Retrieve the order ID, customer ID, and order total for all orders sorted by order total in descending order.
```sql
select ORDER_ID, CUSTOMER_ID, ORDER_TOTAL from DEMO_ORDERS order by ORDER_TOTAL DESC;
```
![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdrDmnare3b11cS3EV78fRWfZV_NoEv9EwZqyDRc29AxFktVusQZnTMdgPjZdfp0cEND5FRsJGUlM70GhoPAq9K7PaDXyqE7rKxGFDg-RSzsrSveom0N8idQE9YbDsIKu8QFMlBoUEWXY1HQxxFTkiksjdTtMtEtmRySMR-?key=oTwoGBJd1F64LAoLwzYFLA)

##### 5. Find the total number of orders placed by each customer.
```sql
select CUST_FIRST_NAME, CUST_LAST_NAME, CUST_EMAIL from DEMO_CUSTOMERS
```
![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfdmyloHxpPfNU6H52I3SkM3dKv0c9a8Iii_yDl3YJZeXqoZmPDOzhgZvl5qsszcY7Ww5jfF7Q3mTWoiCBwU589m6WODwXM4ELWONH1cGHKGdoo_cffjVp5gtBLju7PZOEn-v_asepi6OtBhVXnqOxNIPzAiAtHIH65cPfhbA?key=oTwoGBJd1F64LAoLwzYFLA)
##### 6. 1. Calculate the average order total for each customer.
```sql
select CUSTOMER_ID, AVG(ORDER_TOTAL) as AVG_ODER_TOTAL from DEMO_ORDERS group by CUSTOMER_ID
```
##### 7.1. Retrieve all product names and their total quantities sold.
```sql
select PRODUCT_NAME, SUM(QUANTITY) TOTAL_SALE

from DEMO_PRODUCT_INFO PI, DEMO_ORDER_ITEMS OI

WHERE PI.PRODUCT_ID = OI.PRODUCT_ID

GROUP BY PRODUCT_NAME
```
![[Pasted image 20240823072220.png]]
##### 8 1. Find the highest order total in the DEMO_ORDERS table.
```sql
select MAX(ORDER_TOTAL) from DEMO_ORDERS
```
![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXd-229W14g7iq6oXz0ws9_9dBD1lcRMuYbUD1bVJITrfZ7ea3396K9MjUcTh21kNXGH4B0-0nIeLNCzKOOmFUdD-ZSM0mQ7VzmKWGAewNS7co3PwefXyb1slDeGtFg2BXcN6ECY4IZiAuDLU7C-DM-oIB2Yl-KdcdlJEOwcXg?key=oTwoGBJd1F64LAoLwzYFLA)
##### 9.1. Retrieve the name and price of all products that cost more than $50.
```sql
select PRODUCT_NAME, LIST_PRICE from DEMO_PRODUCT_INFO where LIST_PRICE>50
```

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXei3O81mfaai7aZ_xq-qIsFe-cIsbgxYakIJoYaX_vUyp3Y5Ww_D9GPVSd_VHIIBg0Wn6Pfab8oIKZrOal8taKrObmHS4BJ_JGx7N7sWqae4u4y8LvkW1IbBDGNPDrZpTYFr60U6ltU1OVMaxJN9OGW0VS2aYl_D3mujw9jbw?key=oTwoGBJd1F64LAoLwzYFLA)
##### 10. 1. Find the total sales amount for each product (unit price multiplied by quantity).
```sql
select PRODUCT_ID, sum(UNIT_PRICE * QUANTITY) 

TOTAL_SALES_AMOUNT from DEMO_ORDER_ITEMS group by PRODUCT_ID
```
![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXc1vUVpDASxDD0hi6VibgdcX8RWMA0f5yXHK7Ud6cEzL9MCUssTk_VKxvDLwW9R32s9SkBHRji0ZZpESyhGLVCVoWBHULb47dnMSNefGuIGNYHn2GLDt4qNvKzFOD9nkd06u9mdYUuVh2GRzrIKSPKPWxaAfBIBRTp7igVlyg?key=oTwoGBJd1F64LAoLwzYFLA)
##### 11. 1. Retrieve the user name and the total number of orders processed by each user.
```sql
select USER_NAME, COUNT(ORDER_ID) ORDERS_PROCESSED 

from DEMO_USERS, DEMO_ORDERS

where DEMO_USERS.USER_ID= DEMO_ORDERS.USER_ID

group by USER_NAME
```
![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfj3CLcdVkSfJC1nQh1lcfdJp0WE3uoTrSvwYy398NeYPJWLZCpf07yW970-XpHpOcc64vK_kU5zwIKY_ptud-JouLV25euQwsIPO_-XSJ33HWH1hHW1-MDzglqm2ZnLD4j4CGev1eCIdbLrzdNHUUGf2tPKhOLj1pf4Eha?key=oTwoGBJd1F64LAoLwzYFLA)
##### 12. 1. Create a backup table CUSTOMER_BACKUP containing all records from the DEMO_CUSTOMERS table.
```sql
create table CUSTOMER_BACKUP as 

select * from DEMO_CUSTOMERS
```
##### 13. 1. Insert data from the DEMO_CUSTOMERS table into the CUSTOMER_BACKUP table.
```sql
insert into CUASTOMER_BACKUP(CUSTOMER_ID, CUST_CITY, CUST_STATE)

SELECT CUSTOMER_ID, CUST_CITY, CUST_STATE FROM DEMO_CUSTOMERS
```
``
##### 14. 1. Retrieve the total number of unique customers from the DEMO_ORDERS table.
```sql
select count(DISTINCT CUSTOMER_ID) as UNI_CUS from DEMO_ORDERS
```
![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcxDHdVkY4F9m0zOPNNm5lDiB1G0m9Cvi-NeCibQ3xI9fAgO27LPxfCB_iroz-i4nISercSVzXN7hrNzenp_GMj2GCjzhO8qcesKoLLjbPMah2GIHv2lBZqXDAlvk4i5wRWU5Yg3-pmXelC0OjkGarspeaVoMd4G2HyKBebvg?key=oTwoGBJd1F64LAoLwzYFLA)
##### 15. 1. Retrieve all orders placed in the year 2023.
```sql
select * from DEMO_ORDERS where extract(YEAR from ORDER_TIMESTAMP)=2024
```
![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcxpK-Ilc8XQZWYjc7quDC2GZQOm_Ok_106ararUN9UzGHoNTCHRaJC01nWMhJTxRs1k8B9gw0r8LrGHCpHXUQKYrtNT8uc2gyLpf_bpdU-s0DQE9KV08p9BxIkoybNkrQj-3ljfBwxKJr4ocAsM8lgQL-n7WUQDa0H6iFT-w?key=oTwoGBJd1F64LAoLwzYFLA)

## Conclusion
We have tried new commands like inserting data from other tables, referring to other tables and using them. Creating comparison statements to get the desired data from the db.