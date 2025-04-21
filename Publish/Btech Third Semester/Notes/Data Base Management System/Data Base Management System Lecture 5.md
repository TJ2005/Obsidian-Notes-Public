---
Title: Data Base Management System Lecture 5
Status: 
marker: 
tags: 
Date: 2024.08.07
Time: 15:12
---
# Data Base Management System Lecture 5

Prerequisites
- Rows Queries Data

# Main note

## Attribute
One attribute cannot be split
## Relations are unordered

### Keys
- Let $K \subset R$ 
- That means k is a **SuperKey** of R.
- IF values of a k is sufficient to identify a unique tuple of each possible relation (R)
	- Example. 
		- Consider Roll number Sap ID Name
		- If I have the roll number and the sap id with these two data we can get a unique information back. That is what defines a superkey.
		- If we only consider Name then we might get two pieces information back. This means it is not unique.
		- Thus Sap ID is superkey here and Sap ID with any other key is superkey
- Superkey K is **Candidate** Key.
- Out of these multiple candidate keys we select one to be primary key.
- **Foreign Key** Constraint in one relation must appear in another
	- Referencing relation
	- Referenced Relation


#### Database Schema 
It is the logical Structure of a database add schema example.
- Primary key is where the arrow points ( index this later )

#### Database instance
it is a snapshot of the data in the database at a given instant in time.

## Relational Query languages
Procedural V/s non-procedural or declarative
- Pure languages:
	- Relational Algebra
	- Tuple Relational Calculus
#### Operators
Six Basic Operators
- Select: $\sigma$
	- Selects Tuples that satisfies a given predicate
	- $\sigma_p(R)$
	- p is called the selection predicate
	- $\sigma_{physics}(R)$
	- Comparisons using $=$, $\neq$, $>$ , $\geq$,<,$\leq$
		- ^ v $-$
		- $\sigma_p=(Physics) \^ ~Salary > 90,000(instructor)$
- Project: $\pi$
	- Displays the result.
	- $\Phi~A_1,A_2,A_3,...A_k$
	- $\Pi, Name, Salary^{(instructor)}$
- Union: $\union$
- Set Difference: $-$
- Cartesian Product : $\times$
	- It is expressed in tabular form
	- T1

| $a_1$ | $a_2$ |
| ----- | ----- |
| a     | c     |
| b     | d     |

		- T2

| $a_1$ | $a_2$ |
| ----- | ----- |
| a     | e     |
| b     | f     |

$T_1$ $\times$ $T_2$

| $T_1,a_1$ | $T1,a_2$ | $T_2,a$ | $T_2,A_3$ |
| --------- | -------- | ------- | --------- |
| a         | c        | a       | e         |
| b         | d        | a       | f         |

- Rename: $\rho$

Arity

#### Composition of relational Operations
The result of relational-algebra operation is relation and therefore of relational algebra can be composed into a relational algebra expression.

Consider the query -- Find the names of all instructors in the






## Instructor Relations




# References


###### Information
- date: 2024.08.07
- time: 15:12](<# Data Base Management System Lecture 5

## Prerequisites
- Rows
- Queries
- Data

## Main Note

### Attribute
- One attribute cannot be split.

### Relations are Unordered

### Keys
- Let K ⊆ R
- K is a **SuperKey** of R if the values of K are sufficient to identify a unique tuple of each possible relation (R).

#### Example
- Consider Roll number, Sap ID, Name
  - If we have the Roll number and the Sap ID, these two pieces of data can uniquely identify information. This defines a superkey.
  - If we only consider Name, we might get duplicate information, which means it is not unique.
  - Thus, Sap ID is a superkey here, and Sap ID with any other key is also a superkey.

- Superkey K is a **Candidate Key**.
- Out of these multiple candidate keys, we select one to be the **Primary Key**.
- **Foreign Key** constraints in one relation must appear in another:
  - Referencing Relation
  - Referenced Relation

### Database Schema
- It is the logical structure of a database.
- The primary key is where the arrow points (index this later).

### Database Instance
- It is a snapshot of the data in the database at a given instant in time.

## Relational Query Languages
- Procedural vs. Non-procedural or Declarative
- Pure Languages:
  - Relational Algebra
  - Tuple Relational Calculus

### Operators
Six Basic Operators:
1. **Select (σ)**
   - Selects tuples that satisfy a given predicate.
   - σ_p(R)
   - p is called the selection predicate.
   - Example: σ_physics(R)
   - Comparisons using =, ≠, %3E, ≥, %3C, ≤
     - σ_p = (Physics) ∧ ~Salary > 90,000 (instructor)

2. **Project (π)**
   - Displays the result.
   - π_A1, A2, A3, ..., Ak
   - Example: π_Name, Salary(instructor)

3. **Union (∪)**

4. **Set Difference (-)**

5. **Cartesian Product (×)**
   - It is expressed in tabular form.
   - Example: T1 × T2

| T1.a1 | T1.a2 | T2.a | T2.A3 |
| ----- | ----- | ---- | ----- |
| a     | c     | a    | e     |
| b     | d     | a    | f     |

6. **Rename (ρ)**

### Arity

### Composition of Relational Operations
- The result of a relational-algebra operation is a relation, and therefore, relational algebra can be composed into a relational algebra expression.

#### Example Query
- Find the names of all instructors in the...

## Instructor Relations

## References

**Information**
- Date: 2024-08-07
- Time: 15:12>)