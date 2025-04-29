---
Title: Data Base Management System Lecture 11
Status: 
marker:
  - "[[Lossless Decomposition]]"
  - "[[Data Base]]"
  - "[[BCNF]]"
  - "[[Normalization]]"
tags: 
Date: 2024.09.09
Time: 13:07
---
It looks like you're discussing **decomposition in relational databases**, specifically focusing on **lossless decomposition** and **Boyce-Codd Normal Form (BCNF)**. Let me help you expand and complete your content.

### Lossless Decomposition

In relational database design, a **lossless decomposition** ensures that when a relation is decomposed into smaller relations, no information is lost, and we can recover the original relation by joining the decomposed relations.

#### Condition for Lossless Decomposition:

Let’s say we decompose a relation \( R \) into two relations \( R_1 \) and \( R_2 \). The decomposition is **lossless** if at least one of the following functional dependencies holds in \( F^+ \) (the closure of the functional dependencies):
- \( (R_1 \cap R_2) \rightarrow R_1 \)
- \( (R_1 \cap R_2) \rightarrow R_2 \)

This means that the common attributes between \( R_1 \) and \( R_2 \) (i.e., \( R_1 \cap R_2 \)) should be able to functionally determine either all of \( R_1 \) or all of \( R_2 \).

#### Example (Not Lossless Decomposition):

Consider the following schema:
- `dept_advisors(s_ID, i_ID, department_name)`  
  - Here, `s_ID` represents student ID, `i_ID` represents instructor ID, and `department_name` represents the department name.

If we decompose this schema into two relations:
- \( R_1 = \text{dept_advisors}(s_ID, department_name) \)
- \( R_2 = \text{dept_instructors}(i_ID, department_name) \)

This decomposition is **not lossless** unless there is a functional dependency such that `department_name` determines either `s_ID` or `i_ID`, which is often not the case.

### Boyce-Codd Normal Form (BCNF)

A relation schema \( R \) is in **Boyce-Codd Normal Form (BCNF)** with respect to a set of functional dependencies \( F \), if for every functional dependency \( \alpha \rightarrow \beta \) in \( F^+ \) (the closure of functional dependencies), where:
- \( \alpha \subseteq R \)
- \( \beta \subseteq R \)

At least one of the following holds:
1. \( \alpha \rightarrow \beta \) is **trivial**, meaning \( \beta \subseteq \alpha \).
2. \( \alpha \) is a **superkey** for the relation \( R \). A **superkey** is a set of attributes that can uniquely identify a tuple in the relation.

If a functional dependency violates these conditions, the schema is **not in BCNF**.

#### Example (Not in BCNF):

Consider the following schema:
- \( \text{in\_dep}(\underline{id}, name, salary, \underline{dept\_name}, building, budget) \)
  - This means we have an employee's ID (`id`), their name, salary, the department name (`dept_name`), the building they work in, and the department's budget.

Here, there is a functional dependency:
- \( \text{dept\_name} \rightarrow \text{building, budget} \)

This dependency is **not trivial** (since building and budget are not part of `dept_name`), and `dept_name` is not a superkey because it does not uniquely identify a tuple in the relation (since employees can work in the same department).

Thus, this schema is **not in BCNF**.

### Decomposing a Schema into BCNF

To convert a schema into BCNF, we repeatedly decompose it by removing the violating functional dependencies until all relations are in BCNF. This involves the following steps:

1. **Identify the violating functional dependency** \( \alpha \rightarrow \beta \).
2. **Decompose** the relation into two:
   - One relation containing \( \alpha \) and \( \beta \) (the attributes involved in the functional dependency).
   - Another relation containing \( \alpha \) and all other attributes not in \( \beta \).

This process is repeated until all relations are in BCNF.

#### Example of Decomposition into BCNF:

Let’s go back to the schema:
- \( \text{in\_dep}(\underline{id}, name, salary, \underline{dept\_name}, building, budget) \)

To make it BCNF:
1. We decompose based on the functional dependency \( \text{dept\_name} \rightarrow \text{building, budget} \):
   - \( R_1 = \text{dept}(\text{dept\_name, building, budget}) \)
   - \( R_2 = \text{employee}(\underline{id}, \text{name, salary, dept\_name}) \)

Now, both relations are in BCNF.

---

# Third Normal Form
A relational schema R is in athird Normal form (3NF) if for all
$$\alpha \rightarrow \beta$$
