---
Title: object oriented programming Lecture 3
Status: 
marker:
  - "[[OOP]]"
  - "[[Java]]"
  - "[[Programming]]"
tags: 
Date: 2025.01.16
Time: 10:09
---
[[Object Oriented Programming Lecture 2]]
# Functions

## Why Functions?

Functions help in structuring code by breaking down tasks into manageable parts. For example, consider summing a range of numbers with a loop:

### Without a Function:

```javascript
// Summing numbers from 1 to 10
let sum1 = 0;
for (let i = 1; i <= 10; i++) {
    sum1 += i;
}
console.log(sum1);

// Summing numbers from 20 to 30
let sum2 = 0;
for (let i = 20; i <= 30; i++) {
    sum2 += i;
}
console.log(sum2);
```

### Using a Function:

```javascript
function sumRange(start, end) {
    let sum = 0;
    for (let i = start; i <= end; i++) {
        sum += i;
    }
    return sum;
}

console.log(sumRange(1, 10)); // Output: 55
console.log(sumRange(20, 30)); // Output: 275
```

**Key Benefit**: The `sumRange` function abstracts the logic for summing a range of numbers, making the code cleaner, reusable, and easier to understand.

---

## Abstraction of Methods/Functions

Functions act as **black boxes**:

- **Concealment**: The inner workings are hidden from the user.
- **Revealing only necessary parts**: Users interact with functions through their interface (parameters and return values).

### Black Box Ideation

- Example: When using a function like `sumRange`, we don’t need to know how the summation works internally—we only need to provide the range.

---

## Benefits of Methods/Functions

1. **Write Once, Reuse Anywhere**
    - Code becomes reusable, reducing redundancy.
2. **Concealment of Code**
    - Only the function’s interface is exposed, hiding the implementation details.
3. **Reduce Complexity**
    - Large problems are broken into smaller, manageable tasks.
4. **Stepwise Refinement**
    - Tasks can be modularized and refined incrementally.

# Method Structure
![[IMG-20250730000528944.png]]

## Return Statement
A return statement is required for a value returning method. The methhod shown below in a logically correct has a compiler error because?
```java
public static int sign(int n){
	if(n>0)
		return 1;
	else if(n==0)
		return 0;
	else if(n<0)
		return -1;
}
```
should be
```java
public static int sign(int n){
	if(n>0)
		return 1;
	else if(n==0)
		return 0;
	else
		return -1;
}
```
## Passing parameters
There are two types of parameter passing.
### Pass by Value 
- The caller and callee operate on two different variables which are copies of each other
- Any changes to one variable don't modify the other
- In java everything is strictly **Pass By Value**
### Pass by reference
- The caller rand the callee operate on the **Same Object**
- Arrays are pass by reference by default

In Java there is no pass by reference because it is made with the idea of programming internet. The reference operators is mostly why most of the vulnerabilities exist.
Here’s the completed snippet with examples:

---

## Scopes of Variables

In programming, the **scope** of a variable defines where it can be accessed or modified.
- **Local Scope**: Variables declared inside a function or block and accessible only within that function or block.
- **Global Scope**: Variables declared outside of all functions and accessible anywhere in the program.
- **Block Scope** (in modern languages like Java, JavaScript): Variables declared inside a block `{}` using `let`, `const`, or `var`.

Example in Java:

```java
public class VariableScope {
    // Global variable
    static int globalVar = 10;

    public static void main(String[] args) {
        int localVar = 5; // Local variable
        System.out.println("Global Variable: " + globalVar);
        System.out.println("Local Variable: " + localVar);
        {
            int blockVar = 20; // Block variable
            System.out.println("Block Variable: " + blockVar);
        }
        // System.out.println(blockVar); // Error: blockVar is not accessible here
    }
}
```

---

## Overloading Methods
**Method Overloading** allows multiple methods in a class to have the same name but different parameter lists (function signatures).
### Rules for Overloading:
1. Methods must differ in the number of parameters, types of parameters, or both.
2. Overloading cannot differ only by the return type.
Example in Java:
```java
public class MethodOverloading {
    // Method with one parameter
    public static int add(int a) {
        return a + 10;
    }

    // Overloaded method with two parameters
    public static int add(int a, int b) {
        return a + b;
    }

    // Overloaded method with different parameter types
    public static double add(double a, double b) {
        return a + b;
    }

    public static void main(String[] args) {
        System.out.println(add(5));          // Calls add(int a), Output: 15
        System.out.println(add(5, 10));      // Calls add(int a, int b), Output: 15
        System.out.println(add(5.5, 4.5));   // Calls add(double a, double b), Output: 10.0
    }
}
```

---

## Ambiguous Invocations

Ambiguous invocation occurs when the compiler cannot determine which overloaded method to call because multiple methods match the provided arguments equally well. This leads to a **compiler error**.

### Causes of Ambiguity:

1. **Type Conversion**: When arguments can be implicitly converted into multiple types.
2. **Variable Arguments**: When a method with varargs matches multiple overloaded methods.

### Example in Java:

```java
public class AmbiguousInvocation {
    // Overloaded methods
    public static void printValue(int a, double b) {
        System.out.println("Method with int and double called.");
    }

    public static void printValue(double a, int b) {
        System.out.println("Method with double and int called.");
    }

    public static void main(String[] args) {
        // This call causes ambiguity because both methods match equally
        // printValue(10, 20); // Compiler error: ambiguous method call
    }
}
```

### Resolving Ambiguity:

1. **Explicit Casting**: Help the compiler by explicitly casting arguments.
    
    ```java
    printValue(10, 20.0); // Calls printValue(int, double)
    printValue(10.0, 20); // Calls printValue(double, int)
    ```
    
2. **Avoid Overlapping Signatures**: Design overloads carefully to avoid ambiguous cases.

---

Ambiguous invocations highlight the importance of clear method signatures and intentional casting when dealing with overloaded methods.

### References
- Continued to [[Object Oriented Programming and its Concepts]]
- **Date**: 2025.01.16
- **Time**: 10:09