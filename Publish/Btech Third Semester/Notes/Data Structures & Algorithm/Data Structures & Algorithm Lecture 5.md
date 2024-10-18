---
Title: Data Structures & Algorithm Lecture 5
Status: 
marker: 
tags: 
Date: 2024.07.31
Time: 14:09
---
# Data Structures & Algorithm Lecture 5

# Main note
## Infix To Postfix Conversion

We are going to declare two variables. One will be infixVect which will be converted to postfixVect. Whenever operand is coming put it in the postfixVect.

We need to check what is in the stack. If stack has opening bracket we can push. If it is Empty we can push. If we have something in a stack. Precedence and Associativity Table.](<It sounds like your lecture is covering the algorithm for converting an infix expression (like `A + B`) to a postfix expression (like `AB+`). Let's break down the key points:

### Steps for Converting Infix to Postfix
1. **Declare Variables:**
   - `infixVect`: This will store the infix expression.
   - `postfixVect`: This will store the resulting postfix expression.

2. **Handling Operands:**
   - If the current character is an operand (e.g., `A`, `B`, `1`, `2`), directly add it to `postfixVect`.

3. **Handling Operators and Parentheses:**
   - **Opening Bracket (`(`):** Push it onto the stack.
   - **Closing Bracket (`)`):** Pop from the stack and add to `postfixVect` until you find an opening bracket.
   - **Operators (`+`, `-`, `*`, `/`):**
     - If the stack is empty, push the operator onto the stack.
     - If the stack is not empty, compare the precedence of the current operator with the operator on top of the stack.
       - If the current operator has higher precedence, push it onto the stack.
       - If the current operator has lower or equal precedence, pop from the stack and add to `postfixVect`, then push the current operator.

### Precedence and Associativity Table
- **Precedence** determines the order in which operators are processed:
  - `*`, `/` (higher precedence)
  - `+`, `-` (lower precedence)

- **Associativity** determines the order of operators with the same precedence:
  - Left-to-right (most arithmetic operators)
  - Right-to-left (assignment operators)

### Example
Let's convert the infix expression `A + B * C` to postfix.

1. **Initialize:**
   - `infixVect = ['A', '+', 'B', '*', 'C']`
   - `postfixVect = []`
   - `stack = []`

2. **Process each character:**
   - `A` is an operand, add to `postfixVect`: `postfixVect = ['A']`
   - `+` is an operator, push onto stack: `stack = ['+']`
   - `B` is an operand, add to `postfixVect`: `postfixVect = ['A', 'B']`
   - `*` is an operator, compare precedence with top of stack (`+`):
     - `*` has higher precedence, push onto stack: `stack = ['+', '*']`
   - `C` is an operand, add to `postfixVect`: `postfixVect = ['A', 'B', 'C']`

3. **Pop remaining operators from the stack:**
   - Pop `*` and add to `postfixVect`: `postfixVect = ['A', 'B', 'C', '*']`
   - Pop `+` and add to `postfixVect`: `postfixVect = ['A', 'B', 'C', '*', '+']`

So, the postfix expression is `ABC*+`.

### Summary
- **Operands:** Directly added to the postfix expression.
- **Operators:** Pushed onto the stack based on precedence and associativity rules.
- **Parentheses:** Used to manage order, with special handling for opening and closing brackets.

This process ensures that the resulting postfix expression can be evaluated without needing parentheses, following the correct order of operations.

#### When Exponents
When there is an exponents we go from right to left to calculate instead of the conventional right to left like how we do.


## Precedence Table
1) `^` Exponential
2) $\times$ , $/$ , %
3) +,-

# Problems

## Question 1
infixVect : 2\*3/(2-1)+5\*3

| Expression | Stack   | Output        |     |
| ---------- | ------- | ------------- | --- |
| 2          | empty   | 2             |     |
| *          | *       | 2             |     |
| 3          | *       | 23            |     |
| /          | /       | 23*           |     |
| (          | /,(     | 23*           |     |
| 2          | /,(     | 23*2          |     |
| -          | /,(,-   | 23*2          |     |
| 1          | /,(,-   | 23*21         |     |
| )          | /,(,-,) | 23*21-        |     |
| +          | /,+     | 23*21-        |     |
| 5          | /,+     | 23*21-5       |     |
| *          | /,*     | 23*21-5+      |     |
| 3          |         | 23\*21-5+3\*/ |     |

## Question 2
infixVect
`(a/(b-c+d))(e-a)*c`

#### Solution
| Expression | Stack | Output        |
| ---------- | ----- | ------------- |
| (          | (     |               |
| a          | (     | a             |
| /          | (,/   | a             |
| b          | (,/,  | ab            |
| -          | (,/,- | ab            |
| c          | (,/,- | abc           |
| +          | (,/,+ | abc-          |
| d          | (,/,+ | abc-d         |
| )          |       | abc-d+/       |
| )          |       |               |
| *          | *     | abc-d+/       |
| (          | *,(,  | abc-d+/       |
| e          | *,(,  | abc-d+/e      |
| -          | *,(,- | abc-d+/e      |
| a          | *,(,- | abc-d+/ea     |
| )          |       | abc-d+/ea-*   |
| /          | /     | abc-d+/ea-*   |
| *          | *     | abc-d+/ea-*/  |
| c          |       | abc-d+/ea-*/c |



### Question 3 

| Expression | Stack   | Output        |     |
| ---------- | ------- | ------------- | --- |
| 2          | empty   | 2             |     |
| -          | *       | 2             |     |
| 2          | *       | 23            |     |
| ^          | /       | 23*           |     |
| 3          | /,(     | 23*           |     |
| 2          | /,(     | 23*2          |     |
| -          | /,(,-   | 23*2          |     |
| 1          | /,(,-   | 23*21         |     |
| )          | /,(,-,) | 23*21-        |     |
| +          | /,+     | 23*21-        |     |
| 5          | /,+     | 23*21-5       |     |
| *          | /,*     | 23*21-5+      |     |
| 3          |         | 23\*21-5+3\*/ |     |
**

# References


###### Information
- date: 2024.07.31
- time: 14:09