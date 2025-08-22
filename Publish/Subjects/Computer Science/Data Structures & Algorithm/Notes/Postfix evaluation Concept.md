---
Title: Postfix evaluation Concept
Status: true
marker:
  - "[[Data Structures & Algorithm]]"
  - "[[Stack]]"
tags:
  - BTech
Date: 2025.08.21
Time: 18:59
---
# Postfix evaluation Concept
To solve this question refer [[Data Structures & Algorithm Lecture 5#Infix To Postfix Conversion|Infix To Postfix Conversion]]
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


# References


###### Information
- date: 2025.08.21
- time: 18:59