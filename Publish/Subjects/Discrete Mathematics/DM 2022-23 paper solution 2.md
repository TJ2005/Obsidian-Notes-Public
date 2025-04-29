---
Title: DM 2022-23 paper solution
Status: 
marker: 
tags: 
Date: 2024.11.25
Time: 03:37
---
# DM 2022-23 paper solution

## Question 1
### QA) Venn Diagram
cant solve on pdf

### QB)

---

We aim to show that $((p \lor q) \land (p \rightarrow q)) \lor \neg q$ is a tautology. Below is the **truth table**:

|$p$|$q$|$(p \lor q)$|$(p \rightarrow q)$|$\neg q$|$((p \lor q) \land (p \rightarrow q))$|$((p \lor q) \land (p \rightarrow q)) \lor \neg q$|
|---|---|---|---|---|---|---|
|$\text{True}$|$\text{True}$|$\text{True}$|$\text{True}$|$\text{False}$|$\text{True}$|$\text{True}$|
|$\text{True}$|$\text{False}$|$\text{True}$|$\text{False}$|$\text{True}$|$\text{False}$|$\text{True}$|
|$\text{False}$|$\text{True}$|$\text{True}$|$\text{True}$|$\text{False}$|$\text{True}$|$\text{True}$|
|$\text{False}$|$\text{False}$|$\text{False}$|$\text{True}$|$\text{True}$|$\text{False}$|$\text{True}$|

---

#### Explanation of Columns:

1. **$p$** and **$q$**: Represent the possible truth values of $p$ and $q$.
2. **$(p \lor q)$**: True if either $p$ or $q$ is true.
3. **$(p \rightarrow q)$**: Equivalent to $\neg p \lor q$ (True if $p$ implies $q$).
4. **$\neg q$**: The negation of $q$.
5. **$((p \lor q) \land (p \rightarrow q))$**: Combines the results of $(p \lor q)$ and $(p \rightarrow q)$ using $\land$ (AND).
6. **$((p \lor q) \land (p \rightarrow q)) \lor \neg q$**: Adds $\neg q$ to the previous column using $\lor$ (OR).

---

#### Conclusion:

Since the final column is **True** for all possible truth values of $p$ and $q$, the statement $((p \lor q) \land (p \rightarrow q)) \lor \neg q$ is a **tautology**.

### QC
To solve this using the **pigeonhole principle**, let's analyze step by step:

1. **Pigeonholes and Pigeons:**
    
    - The "holes" in this case are the **pairs of cards** that sum to 21:  
        (1, 20), (2, 19), (3, 18), (4, 17), (5, 16), (6, 15), (7, 14), (8, 13), (9, 12), (10, 11).  
        Thus, there are 10 pairs (holes).
    - The "pigeons" are the **cards selected**. You are selecting 11 cards.
2. **Pigeonhole Principle:**  
    According to the pigeonhole principle, if you distribute more pigeons (11 cards) among fewer pigeonholes (10 pairs), at least one pigeonhole must contain at least 2 pigeons.  
    This means that **at least one of the pairs summing to 21 will have both of its cards selected**.
    
3. **Outcome:**  
    If both cards from any pair (hole) are selected, the sum is 21, which causes the player to lose.
    

#### Conclusion:

Using the pigeonhole principle, it is clear that selecting 11 cards will **always result in a loss**, because it is guaranteed that at least one pair of cards summing to 21 will be selected. Hence, **it is impossible to win this game**.



### QD)

#### **Question (i): For which values of $n$ are the graphs $K_n$ bipartite?**

- **Definition of a Bipartite Graph:** A graph is bipartite if its vertex set can be divided into two disjoint subsets such that no two vertices within the same subset are adjacent.
    
- **Complete Graph $K_n$:** A complete graph $K_n$ has $n$ vertices, and every pair of vertices is connected by an edge.
    
- **Condition for Bipartiteness:** $K_n$ is bipartite if and only if $n \leq 2$. For $n > 2$, there will always be a triangle (a cycle of length 3), which violates the condition of bipartiteness (as cycles of odd length cannot exist in bipartite graphs).
    

**Answer:** The graph $K_n$ is bipartite **only when $n = 2$**.

---

#### **Question (ii): For which values of $n$ are the graphs $K_n$ regular?**

- **Definition of Regular Graph:** A graph is regular if every vertex has the same degree.
    
- **Complete Graph $K_n$:** In $K_n$, every vertex is connected to all other $n-1$ vertices. Hence, the degree of every vertex is $n-1$.
    
- **Condition for Regularity:** Since the degree of every vertex is equal ($n-1$), $K_n$ is regular for **all values of $n \geq 1$**.
    

**Answer:** The graph $K_n$ is regular for **all $n \geq 1$**.

---

#### Final Answers:

- (i) $K_n$ is bipartite if and only if $n = 2$.
- (ii) $K_n$ is regular for all $n \geq 1$.
### QE) 
To determine whether the set of odd integers together with the operation $a * b = ab$ is a monoid, we need to evaluate the following criteria:

1. **Closure**: The set must be closed under the operation.
2. **Associativity**: The operation must be associative.
3. **Identity Element**: There must exist an identity element in the set such that $a * e = e * a = a$ for all $a$ in the set.

#### Step 1: Closure

The operation is defined as $a * b = ab$, which is standard multiplication. Let $a$ and $b$ be any two odd integers. The product of two odd integers is always odd. For example, if $a = 3$ and $b = 5$, then $ab = 15$, which is odd.

Thus, the set of odd integers is **closed** under multiplication.

#### Step 2: Associativity

The operation $a * b = ab$ represents standard multiplication, which is known to be associative. That is,

$$(a∗b)∗c=(ab)c=a(bc)=a∗(b∗c).(a * b) * c = (ab)c = a(bc) = a * (b * c).$$

Therefore, the operation is **associative**.

#### Step 3: Identity Element

The identity element $e$ must satisfy $a * e = e * a = a$ for all $a$ in the set. For standard multiplication, the identity element is $e = 1$, because

$$a∗1=1∗a=a$$for any integer $$a.a * 1 = 1 * a = a \quad \text{for any integer } a.$$

Since $1$ is an odd integer, it belongs to the set of odd integers.

Thus, an identity element exists in the set.

#### Conclusion

The set of odd integers, together with the operation $a * b = ab$, satisfies the criteria of closure, associativity, and the existence of an identity element. Therefore, it forms a **monoid**.
## Question 2
### QA
To solve the recurrence relation

$an=2an−1+an−2, n≥2,a_n = 2a_{n-1} + a_{n-2}, \, n \geq 2,$

with initial conditions:

$a0=0 and a1=1,a_0 = 0 \text{ and } a_1 = 1,$

we proceed as follows:

####
Step 1: Solve the characteristic equation

The recurrence relation can be expressed as:

$an−2an−1−an−2=0.a_n - 2a_{n-1} - a_{n-2} = 0.$

The corresponding characteristic equation is:

$x2−2x−1=0.x^2 - 2x - 1 = 0.$

Solve this quadratic equation using the quadratic formula:

$x=−b±b2−4ac2a,x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a},$

where $a = 1$, $b = -2$, and $c = -1$:

$$x=−(−2)±(−2)2−4(1)(−1)2(1)=2±4+42=2±82=2±222=1±2.x$$ $$= \frac{-(-2) \pm \sqrt{(-2)^2 - 4(1)(-1)}}{2(1)} = \frac{2 \pm \sqrt{4 + 4}}{2}$$ $$= \frac{2 \pm \sqrt{8}}{2} = \frac{2 \pm 2\sqrt{2}}{2} = 1 \pm \sqrt{2}.$$

Thus, the roots are:

$x1=1+2,x2=1−2.x_1 = 1 + \sqrt{2}, \quad x_2 = 1 - \sqrt{2}.$

#### Step 2: General solution

The general solution of the recurrence relation is:

$an=A(x1)n+B(x2)n,a_n = A(x_1)^n + B(x_2)^n,$

where $x_1 = 1 + \sqrt{2}$ and $x_2 = 1 - \sqrt{2}$.

#### Step 3: Apply initial conditions

Using the initial conditions:

1. When $n = 0$: $a0=A(x1)0+B(x2)0=A+B=0.a_0 = A(x_1)^0 + B(x_2)^0 = A + B = 0$.
    
    Thus, $B = -A$.
    
2. When $n = 1$: $a1=A(x1)1+B(x2)1=A(1+2)−A(1−2)=A2+A2=2A2.a_1 = A(x_1)^1 + B(x_2)^1 = A(1 + \sqrt{2}) - A(1 - \sqrt{2}) = A\sqrt{2} + A\sqrt{2} = 2A\sqrt{2}$.
    
    Since $a_1 = 1$, we have: $2A2=1  ⟹  A=122=24.2A\sqrt{2} = 1 \quad \implies \quad A = \frac{1}{2\sqrt{2}} = \frac{\sqrt{2}}{4}$.
    
    From $B = -A$, we get: $B=−24.B = -\frac{\sqrt{2}}{4}$.
    

####
Step 4: Final solution

Substitute $A$ and $B$ into the general solution:

$an=24(1+2)n−24(1−2)n.a_n = \frac{\sqrt{2}}{4}(1 + \sqrt{2})^n - \frac{\sqrt{2}}{4}(1 - \sqrt{2})^n$.

Factor out $\frac{\sqrt{2}}{4}$:

$an=24[(1+2)n−(1−2)n].a_n = \frac{\sqrt{2}}{4} \left[(1 + \sqrt{2})^n - (1 - \sqrt{2})^n\right]$.

This is the closed-form solution for the recurrence relation.
### QB
Bi partite solve on paper.
### QC
Let's solve the problem step by step as per the given instructions.

---

#### Problem Statement

Let $\mathbb{Z}$ denote the set of integers. Define a relation $R$ on $\mathbb{Z}$ by setting $xRy$ if and only if $x = y$ or $x = -y$.

1. Examine whether $R$ is an equivalence relation.
2. Find all equivalence classes of $\mathbb{Z}$ induced by $R$.

---

#### (i) Check if $R$ is an equivalence relation

To check if $R$ is an equivalence relation, we verify the three properties:

1. **Reflexive**: For any $x \in \mathbb{Z}$, $xRx$ must hold.
    
    - Here, $x = y$ satisfies the relation $xRx$, as $x = x$ is true for all $x \in \mathbb{Z}$.
    - Thus, $R$ is reflexive.
2. **Symmetric**: If $xRy$, then $yRx$ must also hold.
    
    - If $xRy$, then either $x = y$ or $x = -y$.
    - In either case, $yRx$ holds because if $x = y$, then $y = x$ (trivially symmetric), and if $x = -y$, then $y = -x$ (also satisfies the relation).
    - Thus, $R$ is symmetric.
3. **Transitive**: If $xRy$ and $yRz$, then $xRz$ must hold.
    
    - Case 1: If $x = y$ and $y = z$, then $x = z$.
    - Case 2: If $x = -y$ and $y = z$, then $x = -z$.
    - Case 3: If $x = y$ and $y = -z$, then $x = -z$.
    - In all cases, $xRz$ holds.
    - Thus, $R$ is transitive.

Since $R$ is reflexive, symmetric, and transitive, $R$ is an equivalence relation.

---

#### (ii) Find the equivalence classes of $\mathbb{Z}$ induced by $R$

The relation $xRy$ means that $x = y$ or $x = -y$. This implies that each integer $x$ is related to its additive inverse $-x$. Therefore:

- For $x = 0$, $R$ relates $0$ only to itself, so the equivalence class of $0$ is:  
    [0]={0}.[0] = \{0\}.
    
- For any positive integer $x > 0$, $R$ relates $x$ to $-x$, so the equivalence class of $x$ is:  
    [x]={x,−x}.[x] = \{x, -x\}.
    
- Similarly, for any negative integer $x < 0$, $R$ relates $x$ to $-x$, and this class is identical to the class of $-x$:  
    [x]=[∣x∣]={x,−x}.[x] = [|x|] = \{x, -x\}.
    

Thus, the equivalence classes are:

1. ${0}$ (the equivalence class of $0$),
2. ${x, -x}$ for every $x > 0$.

---

#### Final Answer

1. **Is $R$ an equivalence relation?**  
    Yes, $R$ is an equivalence relation.
    
2. **Equivalence classes of $\mathbb{Z}$ induced by $R$:**
    

| $x$      | $[x]$       |
| -------- | ----------- |
| $0$      | $\{0\}$     |
| $1$      | $\{1, -1\}$ |
| $2$      | $\{2, -2\}$ |
| $3$      | $\{3, -3\}$ |
| $\vdots$ | $\vdots$    |


For all $x \in \mathbb{Z}$, the equivalence class is:

[x]={{0},if x=0,{x,−x},if x≠0.[x] = \begin{cases} \{0\}, & \text{if } x = 0, \\ \{x, -x\}, & \text{if } x \neq 0. \end{cases}
## Question 3
### Question A
#### Steps to Solve Summation Problems Using Mathematical Induction

#### Step 1: Understand the Problem Statement

- Clearly identify the formula to be proved, such as: Summation Expression (LHS)=Closed-Form Expression (RHS).\text{Summation Expression (LHS)} = \text{Closed-Form Expression (RHS)}.

#### Step 2: Base Case

- Verify the formula for the smallest value of $n$ (typically $n = 1$).
- Substitute $n = 1$ into both the LHS (sum) and RHS (formula).
- Confirm that $\text{LHS} = \text{RHS}$ for the base case.

#### Step 3: Inductive Hypothesis

- Assume the formula holds for $n = k$. That is: 1p+2p+⋯+kp=RHS for k.1^p + 2^p + \dots + k^p = \text{RHS for } k.
- This assumption is called the **inductive hypothesis**.

#### Step 4: Inductive Step

- Prove that the formula holds for $n = k + 1$.
- Start with the LHS for $n = k + 1$: 1p+2p+⋯+kp+(k+1)p.1^p + 2^p + \dots + k^p + (k+1)^p.
- Use the inductive hypothesis to replace the summation up to $k$ with the RHS formula for $k$.

#### Step 5: Simplify and Match

- Simplify the expression for $n = k + 1$.
- Show that the simplified expression equals the RHS for $k + 1$.

#### Step 6: Conclusion

- Conclude that, by the principle of mathematical induction, the formula holds for all $n \geq 1$ (or the specified starting point).

---

#### Example Template

1. **Base Case:** Verify for $n = 1$: LHS=…,RHS=…,LHS=RHS.\text{LHS} = \dots, \quad \text{RHS} = \dots, \quad \text{LHS} = \text{RHS}.
    
2. **Inductive Hypothesis:** Assume the formula holds for $n = k$: 1p+2p+⋯+kp=RHS for k.1^p + 2^p + \dots + k^p = \text{RHS for } k.
    
3. **Inductive Step:** Prove for $n = k + 1$: LHS for k+1=(1p+2p+⋯+kp)+(k+1)p.\text{LHS for } k+1 = (1^p + 2^p + \dots + k^p) + (k+1)^p. Replace $1^p + 2^p + \dots + k^p$ using the inductive hypothesis: Simplify the expression to match the RHS for k+1.\text{Simplify the expression to match the RHS for } k+1.
    
4. **Conclude:** State that the formula holds for all $n \geq 1$ (or the starting point).

### QB ohdw ]--0awdoioahd;i;iuawhdiyiabwd
# References


###### Information
- date: 2024.11.25
- time: 03:37