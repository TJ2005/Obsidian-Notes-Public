---
Title: Infix to Postfix
Status: true
marker:
  - "[[Infix to Prefix]]"
  - "[[Data Structures & Algorithm]]"
tags:
  - BTech
Date: 2025.08.21
Time: 19:03
---
## Why Convert Infix to Prefix?
> [!Related Notes]
> - [[Infix to Postfix Conversion using STACK]]
### **Need for Prefix Notation**

* **Unambiguous Evaluation:** Prefix notation (also called Polish notation) eliminates the need for parentheses and makes the order of operations explicit.
* **Easier Parsing:** Prefix expressions are easier to parse and evaluate using a stack, since the operator always precedes its operands.
* **Efficient Computation:** Prefix notation allows for efficient evaluation, especially in recursive algorithms and functional programming.

---

## How to Convert Infix to Prefix

### **Steps for Conversion**

1. **Reverse the Infix Expression:**

   * Reverse the entire expression.
   * Replace `(` with `)` and `)` with `(` in the reversed expression.

2. **Convert the Reversed Infix to Postfix:**

   * Use the standard **infix-to-postfix** algorithm (stack-based).

3. **Reverse the Postfix Result:**

   * The reversed postfix is the **prefix expression**.

---

## Example: Convert `(A+B)*C+(D-E)/F+G` to Prefix

### **Step 1: Reverse the Infix Expression**

* Original Infix:

  ```
  (A+B)*C+(D-E)/F+G
  ```
* Reversed (with swapped parentheses):

  ```
  G+(F/(E-D))+C*(B+A)
  ```

---

### **Step 2: Convert the Reversed Infix to Postfix**

* Using infix → postfix rules, the result is:

  ```
  G F E D - / + C B A + * +
  ```

---

### **Step 3: Reverse the Postfix Result**

* Postfix:

  ```
  G F E D - / + C B A + * +
  ```
* Reversed (Prefix):

  ```
  + + * + A B C / - D E F G
  ```

---

### ✅ Final Answer

The **prefix notation** of `(A+B)*C+(D-E)/F+G` is:

```
+ + * + A B C / - D E F G
```

---

# References

* **Date:** 2025-08-21
* **Time:** 19:03