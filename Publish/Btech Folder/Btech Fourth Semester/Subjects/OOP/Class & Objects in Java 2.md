---
Title: Object Oriented Programming Lecture 5
Status: 
marker:
  - "[[Programming]]"
  - "[[OOP]]"
  - "[[Java]]"
tags:
  - BTech
Date: 2025.01.23
Time: 10:12
---
Continued from [[Object Oriented Programming and its Concepts]]

---
# **Class & Objects**

First, we take a look at the key points of the [**Classes**](https://chatgpt.com/c/object-oriented-programming-Lecture-4#OOP-Classes).

Also, note that the values are initialized to 0! [Reference](https://chatgpt.com/c/object-oriented-programming-Lecture-4#%5E6c352c)

---

### **Constructors in Java**

A constructor is used to initialize the variables in the class object. A **constructor** in Java is a special method that is used to initialize objects. The **constructor** is called when an object of a class is created.

#### **Types of Constructors:**

1. **No Argument Constructors:**
    
    - This constructor does not accept any arguments and initializes the object with default values.
    
    ```java
    Circle() {
        // no-argument constructor
    }
    ```
    
2. **Parameterized Constructors:**
    
    - This constructor accepts parameters, allowing for more flexible object initialization.
    
    ```java
    Circle(double newRadius) {
        radius = newRadius;
    }
    ```
    

#### **Constructor Rules:**

- **Constructors must have the same name as the class itself**.
- **Constructors do not have a return type**, not even `void`.
- Constructors can be invoked using the `new` operator when an object is created.

```java
Circle circle1 = new Circle(); // Calls the no-argument constructor
Circle circle2 = new Circle(5.0); // Calls the parameterized constructor
```

---
## Default Constructors
A class can also have no constructors. In such cases no arg constructor with an empty body is **Implicitly defined** in the class.
- When a class has a parameterized constructor then it is a compulsion to define a default non parameterized constructor. Read [[Why Parameterized Constructors need defaults|here]]
- Default Values

| Type                              | Value            |
| --------------------------------- | ---------------- |
| Reference                         | Null             |
| numeric                           | 0                |
| Boolean                           | False            |
| Char                              | u0000            |
| Local Variable<br>Inside a method | no Default value |

---
### **The `this` Operator in Java**
In Java, the `this` keyword refers to the **current instance** of a class. It is used primarily to resolve ambiguities when local variables (like method or constructor parameters) have the same name as instance variables (fields).

#### **Why Use `this`?**
When a constructor or method parameter has the same name as an instance variable, Java cannot distinguish between the two. Without `this`, it would refer to the local variable, not the class field, leading to incorrect behavior. The `this` keyword helps differentiate and ensures that the instance variable is accessed.

#### **Example:**
```java
class Student {
    int rollno;  // Instance variable

    // Constructor with a parameter having the same name
    Student(int rollno) {
        this.rollno = rollno;  // 'this.rollno' refers to the instance variable, while 'rollno' is the parameter
    }
}
```

Without `this`, the assignment `rollno = rollno;` would not modify the instance variable. Instead, it would assign the parameter `rollno` to itself.

#### **Other Uses of `this`:**

1. **Referring to the current object**: `this` can be used to pass the current object as an argument to other methods.
2. **Constructor chaining**: `this` can call another constructor in the same class.

---
### **Calling Another Constructor in the Same Class and Returning the Current Object**

In Java, the `this` keyword is used in two main scenarios: **constructor chaining** and **returning the current object**. Here's how both work together:

1. **Constructor Chaining**: This allows one constructor to call another constructor in the same class using `this()`. It helps in reusing constructor code and avoiding repetition.
    
2. **Returning the Current Object**: By using `this`, you can return the current object from a method, enabling **method chaining**, where multiple methods can be invoked on the same object in one statement.
    

#### **Example:**
```java
class Student {
    int rollno;
    String name;

    // Default constructor
    Student() {
        // Calls the parameterized constructor with default values
        this(0, "Unknown");
    }

    // Parameterized constructor
    Student(int rollno, String name) {
        this.rollno = rollno;
        this.name = name;
    }

    // Method to display student information and return the current object
    Student displayInfo() {
        System.out.println("Roll No: " + rollno);
        System.out.println("Name: " + name);
        return this;  // Returning the current object
    }
}

public class Main {
    public static void main(String[] args) {
        // Create a Student object using the default constructor
        Student s = new Student();

        // Call displayInfo() and chain the method call
        s.displayInfo().displayInfo();  // Method chaining
    }
}
```

### **Explanation:**

- **Constructor Chaining**: The `Student()` default constructor calls the `Student(int rollno, String name)` constructor using `this(0, "Unknown")`, initializing the object with default values.
- **Returning the Current Object**: The `displayInfo()` method returns `this`, enabling method chaining. After displaying the student details, the method call can be chained.

### **Output:**

```
Roll No: 0
Name: Unknown
Roll No: 0
Name: Unknown
```

#### **Summary:**
- **Constructor Chaining**: Achieved with `this()` to call another constructor in the same class.
- **Returning Current Object**: Using `this` to return the current instance for method chaining.
---

### **Summary of Key Concepts:**

- **Classes and Objects**:
    - A class defines the blueprint for objects, with variables and methods.
    - Instance variables are initialized to default values like `0`, `null`, etc.
- **Constructors**:
    - **No Argument Constructors**: Initializes objects with default values.
    - **Parameterized Constructors**: Allows custom initialization with parameters.
    - **Constructor Rules**: Must have the same name as the class, and no return type.
- **Default Constructors**:
    - Automatically provided by Java when no constructor is defined.
    - If a parameterized constructor exists, you must define a default constructor explicitly.
    - Instance variables get default values unless explicitly initialized.
- **The `this` Operator**:
    - Refers to the **current object**.
    - Resolves ambiguity between local variables and instance variables with the same name.
    - Used for **constructor chaining** and **method chaining**.
- **Constructor Chaining and Returning the Current Object**:
    - **Constructor Chaining**: Calling one constructor from another within the same class using `this()`.
    - **Returning the Current Object**: Method can return `this` for **method chaining**, enabling multiple method calls on the same object in one statement.
### **References**
- [Object Oriented Programming Lecture 4#OOP Classes](https://chatgpt.com/c/6791cae4-3b6c-8011-a7dc-960c3206154e#OOP-Classes)
- [Object Oriented Programming Lecture 4#^6c352c](https://chatgpt.com/c/6791cae4-3b6c-8011-a7dc-960c3206154e#%5E6c352c)
- Continued to [[OOP Concepts in Java - Final & Static Keywords, Modifiers, and Packages]]


---
