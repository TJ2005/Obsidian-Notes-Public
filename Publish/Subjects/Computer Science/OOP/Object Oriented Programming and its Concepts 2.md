---
Title: object oriented programming Lecture 4
Status: 
marker:
  - "[[Programming]]"
  - "[[Java]]"
  - "[[OOP]]"
tags: 
Date: 2025.01.20
Time: 08:08
---
[[Functions ( Methods ) in Java]]
## Convention
OOP is a *paradigm* or *Methodology* to design a program using [[classes]] and objects. It makes it easy to maintain and modify and cuts down the development time. We can simply inherit characteristics from existing ones. Control of variable flow. OOP also Dumps & Destroy unused object or classes freeing up system memory.

## POP v/s OOP

| **Procedural Oriented Programming**                                                            | **Object Oriented Programming**                                                                  |
| ---------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| In procedural programming, program is divided into small parts called **functions**.           | In object-oriented programming, program is divided into small parts called **objects**.          |
| Procedural programming follows **top-down approach**.                                          | Object-oriented programming follows **bottom-up approach**.                                      |
| There is **no access specifier** in procedural programming.                                    | Object-oriented programming provides access specifiers like **private, public, protected**, etc. |
| Procedural programming does not have any proper way for hiding data, so it is **less secure**. | Object-oriented programming provides data hiding, so it is **more secure**.                      |
| In procedural programming, **function is more important than data**.                           | In object-oriented programming, **data is more important than function**.                        |
| **Examples:** C, FORTRAN, Pascal, BASIC, etc.                                                  | **Examples:** C++, Java, Python, C#, etc.                                                        |
## Java & OOP Concepts
OOP Features available in Java:
- [[Classes]]
- [[Objects]]
- [[Instance]]
- [[Method]]
- [[Message Passing]]
- [[Encapsulation]]
- [[Polymorphism]]
- [[Inheritance]]
- [[Abstraction]]
---

## OOP Classes
Classes in Object-Oriented Programming (OOP) act as **templates** or **blueprints** that define the behavior and state that objects of a particular type will support. They serve as **constructs** that outline the structure of objects sharing the same characteristics.

A class consists of **variables**, which define the data fields, and **methods**, which define the behaviors. Additionally, classes provide special types of methods called **constructors**, which are invoked to create and initialize objects from the class.

#### **A blur definition**
To design a class, if we can identify a **noun** from a given problem statement and associate relevant attributes with it, we can implement it as a class in the program.

![[IMG-20250730000528968.png]]

### Example
```java
class Student {
    int id;
    String name;

    public static void main(String args[]) {
        Student s1 = new Student();
        System.out.println(s1.id);
        System.out.println(s1.name);
    }
}
```

### **Explanation:**
1. **Class Definition:**
    - A class named `Student` is defined with two instance variables:
        - `int id` (default value is `0` for integers in Java).
        - `String name` (default value is `null` for objects in Java).
2. **Object Creation:**
    - Inside the `main` method, an object `s1` of class `Student` is created using `new Student();`.
    - Since no values are assigned, the default values of instance variables will be used.
3. **Printing Values:** ^6c352c
    - `System.out.println(s1.id);` → Prints `0` because `int` variables in Java are initialized to `0` by default.
    - `System.out.println(s1.name);` → Prints `null` because `String` variables are object references and are initialized to `null` by default.
### **Output:**
```
0
null
```
### **Key Takeaways:**

^340711

- **Default Values in Java:**
    - Primitive data types (e.g., `int`, `float`) have default values (e.g., `0`, `0.0`).
    - Reference types (e.g., `String`, `Object`) default to `null`.
    - These objects have a default constructor to it that they are initialized to 0/Null.
- **Object Instantiation:**
    - When an object is created using the `new` keyword, memory is allocated, and default values are assigned to instance variables.
### **Example 2**
```java
class Student {
    int id;
    String name;
}

class TestStudent1 {
    public static void main(String args[]) {
        Student s1 = new Student();
        System.out.println(s1.id);
        System.out.println(s1.name);
    }
}
```

### **Explanation:**
1. **Class Definition (Student):**
    - A class `Student` is defined with two instance variables:
        - `int id;` → Default value: `0` (primitive type).
        - `String name;` → Default value: `null` (reference type).
2. **Separate Main Class (TestStudent1):**
    - In the `TestStudent1` class, the `main` method is defined.
    - An object `s1` of type `Student` is created using `new Student();`.
3. **Printing Values:**
    - `System.out.println(s1.id);` → Prints `0` as default for `int`.
    - `System.out.println(s1.name);` → Prints `null` as default for `String`.
### **Expected Output:**
```
0
null
```
### **Key Points:**
- **Class and Object Concept:**
    - A class acts as a blueprint, and objects are instances of the class.
    - When an object is created, its instance variables are assigned default values.
- **Default Values in Java:**
    - Primitive types (like `int`) are initialized to `0`.
    - Reference types (like `String`) are initialized to `null`.
- **File Naming Conventions**
	- A file can have multiple classes stored in it. 
	- But **ONLY ONE** of those class should have void main.
	- And the **ONE** with the void main should be the name of the file.

### **Example 4**
```java
class Student {
    int rollno;
    String name;

    void displayInformation() {
        System.out.println(rollno + " " + name);
    }
}

public static void main(String args[]) {
    Student s1 = new Student();
    s1.rollno = 54;
    s1.name = "Ram";
    s1.displayInformation();
}```
54 Ram
### **Explanation:**
1. **Class Definition (Student):**
    - The class `Student` contains two instance variables:
        - `int rollno;` → Stores the student's roll number.
        - `String name;` → Stores the student's name.
    - A method `displayInformation()` is defined to print the values of `rollno` and `name`.
2. **Object Creation and Data Assignment:**
    - In the `main` method, an object `s1` of type `Student` is created using `new Student();`.
    - The attributes of the object are assigned values:
        - `s1.rollno = 54;`
        - `s1.name = "Ram";`
    - The method `s1.displayInformation();` is called to print the values.
3. **Printing Values:**
    - The method prints the assigned values of `rollno` and `name` separated by a space.
### **Expected Output:**

### **Key Points:**
- **Object Initialization**
    - After creating an object, values can be assigned to instance variables directly.
- **Method Invocation:**
    - Methods in the class can be used to manipulate and display object data.
- **Encapsulation Best Practice:**
    - While this example directly accesses instance variables, it's generally recommended to use getter and setter methods to ensure [[data encapsulation]] in real-world applications.



---
# References


###### Information
- date: 2025.01.20
- time: 08:08