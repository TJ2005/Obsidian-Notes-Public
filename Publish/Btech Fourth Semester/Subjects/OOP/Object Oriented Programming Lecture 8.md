---
Title: Object Oriented Programming Lecture 7
Status: 
marker:
  - "[[Java]]"
  - "[[Programming]]"
tags: 
Date: 2025.01.30
Time: 10:13
---
Continued from [[OOP Concepts in Java - Final & Static Keywords, Modifiers, and Packages]]
Here is the content in markdown format, with an explanation of the `static` keyword:


# OOP - Final, Static Variables/Constants & Methods, Modifiers, and Packages

## Class:
- Member data, member function.
- Constructors don’t have return type.
- Can have multiple constructors.

### 'Final' Keyword:
The `final` keyword is used to make a variable constant. After initialization, the value of the variable cannot be changed or reinitialized.

```java
public class MyClass {
    final double pi = 3.141592653589793;
    // Other class members...
}
````

## 'Static' Keyword:

The `static` keyword can be used with variables and functions. Static variables/functions/methods are shared with all instances of the class, meaning every object, function, etc., can access the static members.

- **Static Variables:** When you have a static variable, there is a single copy of that variable in memory. All objects of the class will point to the same memory address for the static members.
- **Static Methods:** Similarly, static methods can be called without creating an instance of the class. These methods cannot access instance variables or methods because they are not tied to any specific object.

### Example:

```java
class Student {
    int id;
    String name;
    static String collegeName; // Only one copy of the college name
}

class StaticVar {
    public static void main(String[] args) {
        Student s1 = new Student();
        Student s2 = new Student();
        Student s3 = new Student();
        
        Student.collegeName = "MPSTME"; // All students share the same college name
    }
}
```

### Notes:

- The `main()` function starts executing from the main class. `static` is used to call the method without binding it to a specific class.
- The JVM will enter the control to static members when they are accessed.
- You can make a variable `static final`, which makes it both constant and shared across all instances.

## Packages:

A package groups related types (classes, interfaces, etc.), providing access protection and namespace management.

### Types of Packages:

- Built-in
- User-defined

### Example of a Package:

```java
// Package declaration at the top of the code
package A;

public class Calculator {
    public int add(int a, int b) {
        return a + b;
    }
}

// Import and use package in another class
package B;
import A.Calculator;

public class Demo {
    public static void main(String[] args) {
        Calculator obj = new Calculator();
        System.out.println(obj.add(10, 20));
    }
}
```

### Notes:

- When you write `import abc.*`, it imports all classes within the `abc` package.
- When you write `import abc.foo.*`, it only imports `Demo1` and `Demo2` from the `foo` subpackage.
- You can restrict access using specific imports, such as importing only one class from a package.

_(Source: Dhruv Rathod)_

### Explanation of Static:
In object-oriented programming, the `static` keyword is used to define class-level variables and methods. Unlike instance variables or methods, which belong to specific instances of the class, static variables and methods belong to the class itself, meaning they are shared across all instances of that class. 

- A `static` variable has only one copy in memory, regardless of how many objects are created from the class.
- A `static` method can be called without creating an instance of the class.
  
In the example provided, the `collegeName` variable is static. This means that it is shared by all `Student` objects, and the same value is used by every instance of the class.

Void main is always static because we don't want an object to be created.

# References


###### Information
- date: 2025.01.30
- time: 10:10