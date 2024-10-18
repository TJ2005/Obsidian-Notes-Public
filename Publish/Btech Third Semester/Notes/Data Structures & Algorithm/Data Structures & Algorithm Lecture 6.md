---
Title: Data Structures & Algorithm Lecture 6
Status: 
marker: 
tags: 
Date: 2024.08.02
Time: 09:17
---
# Data Structures & Algorithm Lecture 6

# Main note

To solve this question refer [[Data Structures & Algorithm Lecture 5#Infix To Postfix Conversion|Infix To Postfix Conversion]]
## Questions

#### Question 1
Input : infixVect = `1-2^3^3-(4+5*6)*7

| Expression | Stack | Output            |
| ---------- | ----- | ----------------- |
| 1          | empty | 1                 |
| -          | -     | 1                 |
| 2          | -     | 12                |
| ^          | -^    | 12                |
| 3          | -^    | 123               |
| ^          | -^    | 123^              |
| 3          | -^    | 123^3             |
| ^          | -^    | 123^3^            |
| -          | -     | 123^3^-           |
| (          | -(    | 123^3^-           |
| 4          | -(    | 123^3^-4          |
| +          | -(+   | 123^3^-4          |
| 5          | -(+   | 123^3^-45         |
| *          | -(+*  | 123^3^-45         |
| 6          | -(+*  | 123^3^-456        |
| )          | -     | 123^3^-456*+      |
| *          | -*    | 123^3^-456*+      |
| 7          | Empty | 123^3^-456\*+7\*- |
Answer : 123^3^-456\*+7\*-

#### Question 2
`(A+B)*C+(D-E)/F+G`

| Expression | Stack | Output        |
| ---------- | ----- | ------------- |
| (          | (     |               |
| A          | (     | A             |
| +          | (+    | A             |
| B          | (+    | AB            |
| )          | )     | AB+           |
| *          | *     | AB+           |
| C          | *     | AB+C          |
| +          | +     | AB+C*         |
| (          | +(    | AB+C*         |
| D          | +(    | AB+C*D        |
| -          | +(-   | AB+C*D-       |
| E          | +(-   | AB+C*D-E      |
| )          | +     | AB+C*D-E-     |
| /          | +/    | AB+C*D-E      |
| F          | +/    | AB+C*D-EF     |
| +          | +     | AB+C*D-EF/+   |
| G          |       | AB+C*D-EF/+G+ |
|            |       |               |

### Postfix Evaluation Example

Sure! Here is a properly formatted markdown table detailing the steps for evaluating the postfix expression `234*-5+`:

| Step | Symbol | Operand1 | Operand2 | Value | Operand Stack |
|------|--------|----------|----------|-------|---------------|
| 1    | 2      |          |          |       | 2             |
| 2    | 3      |          |          |       | 2, 3          |
| 3    | 4      |          |          |       | 2, 3, 4       |
| 4    | *      | 3        | 4        | 12    | 2, 12         |
| 5    | -      | 2        | 12       | -10   | -10           |
| 6    | 5      |          |          |       | -10, 5        |
| 7    | +      | -10      | 5        | -5    | -5            |

Thus, the total answer is `-5`.

For the second example `623+-382/+*2^3+`, the steps are more complex. Here is a markdown table for that:

| Step | Symbol | Operand1 | Operand2 | Value | Operand Stack     |
|------|--------|----------|----------|-------|-------------------|
| 1    | 6      |          |          |       | 6                 |
| 2    | 2      |          |          |       | 6, 2              |
| 3    | 3      |          |          |       | 6, 2, 3           |
| 4    | +      | 2        | 3        | 5     | 6, 5              |
| 5    | -      | 6        | 5        | 1     | 1                 |
| 6    | 3      |          |          |       | 1, 3              |
| 7    | 8      |          |          |       | 1, 3, 8           |
| 8    | 2      |          |          |       | 1, 3, 8, 2        |
| 9    | /      | 8        | 2        | 4     | 1, 3, 4           |
| 10   | +      | 3        | 4        | 7     | 1, 7              |
| 11   | *      | 1        | 7        | 7     | 7                 |
| 12   | 2      |          |          |       | 7, 2              |
| 13   | ^      | 7        | 2        | 49    | 49                |
| 14   | 3      |          |          |       | 49, 3             |
| 15   | +      | 49       | 3        | 52    | 52                |

Thus, the total answer is `52`.

## Algorithm for evaluation
Evaluating a postfix expression (Reverse Polish Notation) involves using a stack to store operands and apply operators. Here is an algorithm to evaluate a postfix expression:

1. Initialize an empty stack.
2. Traverse the postfix expression from left to right for each symbol:
   a. If the symbol is an operand, push it onto the stack.
   b. If the symbol is an operator, pop the top two operands from the stack. Apply the operator to these two operands. Push the result back onto the stack.
3. After the entire expression has been traversed, the result of the expression will be the only value remaining in the stack. Pop and return this value.

Here is the algorithm in pseudocode:

```
function evaluatePostfix(expression):
    create an empty stack
    
    for each symbol in expression:
        if symbol is an operand:
            push symbol onto the stack
        else if symbol is an operator:
            operand2 = pop from the stack
            operand1 = pop from the stack
            result = apply the operator to operand1 and operand2
            push result onto the stack
    
    result = pop from the stack
    return result
```

Here is a Python implementation of the algorithm:

```python
def evaluate_postfix(expression):
    stack = []
    
    for symbol in expression:
        if symbol.isdigit():  # If the symbol is an operand (assuming single-digit for simplicity)
            stack.append(int(symbol))
        else:  # If the symbol is an operator
            operand2 = stack.pop()
            operand1 = stack.pop()
            
            if symbol == '+':
                result = operand1 + operand2
            elif symbol == '-':
                result = operand1 - operand2
            elif symbol == '*':
                result = operand1 * operand2
            elif symbol == '/':
                result = operand1 / operand2
            elif symbol == '^':
                result = operand1 ** operand2
            
            stack.append(result)
    
    return stack.pop()

# Example usage:
expression = "623+-382/+*2^3+"
print(evaluate_postfix(expression))  # Output: 52
```

In this implementation:
- The `isdigit()` function is used to check if a symbol is an operand.
- The stack is used to store operands and intermediate results.
- Operators are applied to the top two elements of the stack, and the result is pushed back onto the stack.
- After processing the entire expression, the result is the only remaining element in the stack.

## Infix To Prefix
First step is reversing

#### Example 
`(A+B)+C-(D-E)^F`
###### Solution
First F^)E-D(-C+)B+A(

#### Homework
`K+L-M-N+O^P^Q*W/U+V*T+Q`
To convert the infix expression `(A+B)*C+(D-E)/F+G` to prefix notation, follow these steps:

1. **Reverse the String:**
   - Original Infix: `(A+B)*C+(D-E)/F+G`
   - Reversed: `G+F/D-(E-D)*C+(B+A)`

2. **Convert the Reversed String to Postfix:**
Here's the table with the steps to convert `(A+B)*C+(D-E)/F+G` to postfix 

| Expression | Stack | Output          |
| ---------- | ----- | --------------- |
| G          |       | G               |
| +          | +     | G               |
| F          | +     | GF              |
| /          | /     | GF+             |
| D          | /     | GF+D            |
| -          | -     | GF+D/           |
| (          | - (   | GF+D/           |
| E          | - (   | GF+D/E          |
| -          | -     | GF+D/E          |
| D          | -     | GF+D/E-D        |
| )          | -     | GF+D/E-D-       |
| *          | *     | GF+D/E-D-       |
| C          | *     | GF+D/E-D-C*     |
| +          | +     | GF+D/E-D-C*+    |
| (          | + (   | GF+D/E-D-C*+    |
| B          | + (   | GF+D/E-D-C*+B   |
| +          | +     | GF+D/E-D-C*+B   |
| A          | +     | GF+D/E-D-C*+BA  |
| )          |       | GF+D/E-D-C*+BA+ |


4. **Reverse the Postfix Result to Get Prefix:**

   - Postfix Result: `GF+D/E-D-C*+BA+`
   - Reversed Prefix: `+A+B-C*DE/F+G`

   Thus, the prefix notation of the infix expression `(A+B)*C+(D-E)/F+G` is `+ + A B / - D E F G`.

# References

###### Information
- date: 2024.08.02
- time: 09:17