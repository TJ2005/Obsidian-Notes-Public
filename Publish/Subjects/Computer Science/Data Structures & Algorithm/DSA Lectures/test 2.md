### Relational Algebra Expressions

#### Qt 1: Employee Database

**Schema:**
- `employee(person_name, street, city)`
- `works(person_name, company_name, salary)`
- `company(company_name, city)`

**a. Find the names of all employees who work for "First Bank Corporation".**

```plaintext
π_person_name(σ_company_name='First Bank Corporation'(works))
```

- **Explanation**: Select rows from the `works` relation where the `company_name` is "First Bank Corporation" and project the `person_name` from the result.

**b. Find the names and cities of residence of all employees who work for "First Bank Corporation".**

```plaintext
π_person_name, city(employee ⨝ (works ⨝ σ_company_name='First Bank Corporation'(works)))
```

- **Explanation**: 
  1. Perform a selection on `works` to get employees working for "First Bank Corporation".
  2. Join the result with `employee` to get the city of residence.
  3. Project the `person_name` and `city`.

**c. Find the names, street address, and cities of residence of all employees who work for "First Bank Corporation" and earn more than $10,000.**

```plaintext
π_person_name, street, city(employee ⨝ (σ_salary>10000(works ⨝ σ_company_name='First Bank Corporation'(works))))
```

- **Explanation**:
  1. Select rows from `works` where the `company_name` is "First Bank Corporation" and `salary` is greater than $10,000.
  2. Join this result with `employee` to get the street and city of the employees.
  3. Project the `person_name`, `street`, and `city`.

#### Qt 2: Bank Database

**Schema:**
- `branch(branch_name, branch_city, assets)`
- `customer(customer_name, customer_street, customer_city)`
- `loan(loan_number, branch_name, amount)`
- `borrower(customer_name, loan_number)`
- `account(account_number, branch_name, balance)`
	- `depositor(customer_name, account_number)`

**a. Find all loan numbers with a loan value greater than $10,000.**

```plaintext
π_loan_number(σ_amount>10000(loan))
```

- **Explanation**: Select rows from `loan` where the `amount` is greater than $10,000 and project the `loan_number`.

**b. Find the names of all depositors who have an account with a value greater than $6,000.**

```plaintext
π_customer_name(depositor ⨝ (σ_balance>6000(account)))
```

- **Explanation**:
  1. Select rows from `account` where the `balance` is greater than $6,000.
  2. Join this result with `depositor` to get the names of depositors.
  3. Project the `customer_name`.

**c. Find the names of all depositors who have an account with a value greater than $6,000 at the “Uptown” branch.**

```plaintext
π_customer_name(depositor ⨝ (σ_balance>6000(account ⨝ σ_branch_name='Uptown'(branch))))
```

- **Explanation**:
  1. Select rows from `account` where the `balance` is greater than $6,000 and the `branch_name` is "Uptown".
  2. Join this result with `depositor` to get the names of depositors.
  3. Project the `customer_name`.

In summary:
- Use **selection** (σ) to filter rows based on conditions.
- Use **projection** (π) to choose specific columns.
- Use **join** (⨝) to combine information from multiple tables.