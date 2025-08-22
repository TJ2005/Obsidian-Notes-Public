---
Title: "Primitive DataTypes"
Status: 
marker: 
tags: 
Date: "2025.08.21"
Time: "19:30"
---
# Primitive DataTypes
This section was not covered in college lectures but it will be important for you to know this to understand what [[Data Structures & Algorithm]] is about.
Its an AI Gen Note but you should still read it.

---
## **Primitive Data Types: The Building Blocks of Programming**

### **What Are Primitive Data Types?**
Primitive data types are the **most basic data types** directly supported by a programming language and understood by the microprocessor. Just like **atoms** are the fundamental units of matter, primitive data types are the fundamental units of data in programming. Everything else is built using these primitives.

A microprocessor can only understand a **few basic data types** (like integers, floating-point numbers, and characters) at the hardware level. All other complex data types (like strings, arrays, or objects) are **constructed** using these primitives.

---

### **How Strings Are Built from Characters**
A **character (`char`)** is a primitive data type that represents a single symbol (like `'A'`, `'1'`, or `'$'`).
- When you **link multiple `char` values together**, you get a **string** (e.g., `"Hello"` is just `'H'`, `'e'`, `'l'`, `'l'`, `'o'` combined).
- This is similar to how **molecules** are formed by combining atoms.

---

## **List of Primitive Data Types**
The most common primitive data types in languages like C, Java, and Python are:

| Data Type  | Description                          | Example Values       |
|------------|--------------------------------------|----------------------|
| `int`      | Integer numbers (whole numbers)      | `5`, `-3`, `1000`    |
| `float`    | Floating-point numbers (decimals)    | `3.14`, `-0.001`    |
| `double`   | Double-precision floating-point      | `3.1415926535`       |
| `char`     | Single character                     | `'A'`, `'$'`, `'1'`  |
| `bool`     | Boolean (true/false)                 | `true`, `false`      |
| `void`     | Represents "no value" (used in functions) | `void`        |

---

## **How Users Create Their Own Data Types**
While primitives are the building blocks, programmers can **combine them** to create custom data types:

1. **Arrays:**
   - A collection of the same data type (e.g., `int[] numbers = {1, 2, 3};`).

2. **Structures (Structs):**
   - Group different data types under one name (e.g., a `Person` struct with `name` (string) and `age` (int)).

3. **Classes (OOP):**
   - Define objects with properties (data) and methods (functions).

4. **Enums:**
   - Define a set of named constants (e.g., `enum Color { RED, GREEN, BLUE }`).

5. **Pointers:**
   - Store memory addresses to reference other data.

### **Example: Creating a Custom Data Type**
```c
// Define a custom struct
struct Person {
    char name[50];  // String (array of chars)
    int age;         // Integer
    float height;    // Floating-point
};

// Usage
struct Person person1 = {"Alice", 25, 5.6};
```
Here, `Person` is a **user-defined data type** built using primitives (`char`, `int`, `float`).

---

### **Key Takeaway**
- **Primitives = Atoms** (basic, hardware-understood).
- **Custom data types = Molecules** (built by combining primitives).
- **Strings, arrays, and objects** are all just **organized collections of primitives**!

# References


###### Information
- date: 2025.08.21
- time: 19:30