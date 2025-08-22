---
Title: Data Structures
Status: true
marker:
  - "[[Data Structures & Algorithm]]"
tags:
  - BTech
Date: 2025.08.21
Time: 19:26
---

# Data Structures: Organizing Data Efficiently

---

## **Prerequisite: Understanding Primitive Data Types**
Before diving into data structures, you **must** understand what primitive data types are. As discussed in the [Primitive DataTypes](Primitive%20DataTypes.md) note, these are the basic building blocks that microprocessors directly understand. Everything else is constructed using these primitives.

---

## **What Are Data Structures?**
Data structures are ways to **organize, store, and manage data** efficiently. They allow us to perform operations like insertion, deletion, searching, and sorting in an optimized way.

---

## **Data Abstraction: Hiding Complexity**

### **What is Data Abstraction?**
Data abstraction refers to **hiding unnecessary details** and exposing only the essential features of the data. It focuses on **"what"** the data does, not **"how"** it does it.

- **Example:** When you use a function like `sort()`, you don’t need to know how the sorting algorithm works internally. You just need to know that it sorts the data.
- **Analogy:** Think of a car. You don’t need to know how the engine works to drive it. You just need to know how to use the steering wheel, accelerator, and brakes.

### **Why is Abstraction Important?**
- **Simplifies Complexity:** Allows programmers to focus on high-level logic without worrying about low-level implementation.
- **Modularity:** Encourages reusable and maintainable code.
- **Encapsulation:** Protects data integrity by hiding internal details.

---

## **Abstract Data Types (ADT)**

### **What is an Abstract Data Type?**
An **Abstract Data Type (ADT)** is a mathematical model for a data structure. It defines:
1. **Data Stored:** What kind of data it holds.
2. **Operations on the Data:** What actions can be performed (e.g., push, pop, insert, delete).
3. **Error Conditions:** How it handles errors (e.g., stack overflow, underflow).

### **Key Characteristics of ADTs**
- **Implementation-Independent:** The ADT defines **what** operations are possible, not **how** they are implemented.
- **Error Handling:** ADTs must specify how to handle errors (e.g., trying to pop from an empty stack).

### **Example: Stack ADT**
- **Data Stored:** A collection of elements.
- **Operations:**
  - `push(element)`: Adds an element to the top.
  - `pop()`: Removes and returns the top element.
- **Error Conditions:**
  - `Stack Overflow`: When trying to push an element into a full stack.
  - `Stack Underflow`: When trying to pop an element from an empty stack.

---

## **How to Create Your Own Data Structures**
Using primitive data types and abstraction, you can create custom data structures. For example:
- **Arrays:** A collection of elements of the same type.
- **Structs:** Group different data types under one name.
- **Classes:** Define objects with properties and methods.
- **Linked Lists:** A sequence of nodes where each node contains data and a reference to the next node.

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
Here, `Person` is a **user-defined data type** built using primitive data types (`char`, `int`, `float`).

---

## **Summary**
- **[Primitive Data Types](Primitive%20DataTypes.md)** are the foundation.
- **Data Abstraction** simplifies complexity by hiding implementation details.
- **Abstract Data Types (ADTs)** define what operations are possible and how errors are handled.
- **Custom Data Structures** are built using primitives and abstraction.

Understanding these concepts will help you design efficient and scalable solutions in programming.

###### Information
- date: 2025.08.21
- time: 19:26