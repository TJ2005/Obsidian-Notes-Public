---
Title: object oriented programming Lecture 6
Status: 
marker:
  - "[[Programming]]"
  - "[[Java]]"
tags: 
Date: 2025.01.27
Time: 09:49
---
	Continued from [[Class & Objects in Java]]
# OOP Concepts - Final, Static Variables/Constants & Methods, Modifiers, and Packages

## Class:

- **Member Data and Member Function**
  - Constructors don’t have return types.
  - A class can have multiple constructors.

### 'Final' Keyword:
- The `final` keyword makes a variable constant. Once initialized, the value of that variable cannot be changed or reinitialized.

```java
public class MyClass{
    final double pi = 3.141592653589793;
    // pi cannot be modified after initialization
}
```

```java
final class Vehicle {
    // This class cannot be subclassed
}
```

You will learn about subclassing in future lecture.
### 'Static' Keyword:

- The `static` keyword can be used with variables and functions. Static variables/functions/methods are shared with all instances of the class. Every object or function can access static members.
    
- **Memory Handling:**    
    - Static functions/variables have a single copy in memory. Each object normally has its own storage, but static members share the same memory address across all objects.

- **Main Method:**
    - The `main()` function, being static, doesn't require an object to be invoked. The JVM starts execution from the `main()` function, without binding it to any class.

- **Static Classes**:
	- The [[Encapsulation & Data Hiding in Object-Oriented Programming#Nested Class|Nested Class]] can be instantiated without instantiating without its outer class. 
- Example:    
```java
class Student {
    int id;
    String name;
    static String collegeName; // Only one copy of the college name

    public static void main(String[] args) {
        Student s1 = new Student();
        Student s2 = new Student();
        Student s3 = new Student();

        Student.collegeName = "MPSTME"; // Same for all instances
        s1.id = 1;
        s1.name = "stud1";
        s2.id = 2;
        s2.name = "stud2";
    }
}
```

## Packages:

Packages group related types (classes, interfaces, etc.) providing access protection and namespace management.

### Types of Packages:

1. **Built-in Packages**
2. **User-defined Packages**

- The `package` keyword is used to create a package.
- The package declaration should only appear once at the top of the source code.

#### Example of Using Packages:

```java
// Giving authority to only all functions/class.
package A;

public class Calculator {
    public int add(int a, int b) {
        return a + b;
    }

    public static void main(String[] args) {
        Calculator obj = new Calculator();
        System.out.println(obj.add(10, 20));
    }
}
```

```java
// Giving authority to only one function/class (i.e., Demo).
package B;

import A.Calculator;

public class Demo {
    public static void main(String[] args) {
        Calculator obj = new Calculator();
        System.out.println(obj.add(100, 200));
    }
}
```

### Import Statement:

When you import a package, it allows you to access its classes, but you can also limit the scope of the import:

- `import abc.*;` – This imports all classes within the `abc` package, including sub-package classes.
- `import abc.foo.*;` – This imports only the classes from `foo` under `abc`.
- `import abc.bar.*;` – This imports only the classes from `bar` under `abc`.

#### Example of Importing Specific Classes:

```java
import abc.foo.Demo1;
import abc.foo.Demo2;
```

### Package Naming:

1. **Giving authority to all functions/classes:**
    
    ```java
    package A;
    ```
    
2. **Giving authority to a specific function/class (like Demo):**
    
    ```java
    package B;
    import A.Calculator;
    ```
    

By structuring your code this way, you can manage access to classes, functions, and variables effectively, and create a modular program where each component has well-defined responsibilities.

---
