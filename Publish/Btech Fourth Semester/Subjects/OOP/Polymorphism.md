---
Title: "Polymorphism"
Status: 
marker: 
tags: 
Date: "2025.03.06"
Time: "10:14"
---

### Polymorphism in Object-Oriented Programming

**Polymorphism** is derived from the Greek word "many shapes" or "many forms." In the context of **Object-Oriented Programming (OOP)**, polymorphism refers to the ability of an object to take on many forms. More specifically, polymorphism allows objects of different classes to be treated as objects of a common superclass, enabling code to be written in a more generalized way without needing to know the exact types of objects it is dealing with.

### Key Benefits of Polymorphism:

- **Code Reusability**: Write generalized code that can work with different types of objects.
- **Maintainability**: Makes the code easier to modify or extend because new classes can be added with minimal changes to existing code.
- **Flexibility**: Enables the use of dynamic method calls that depend on the actual type of the object at runtime.

### Types of Polymorphism

Polymorphism can be divided into **two primary categories**:

#### 1. **Compile-Time Polymorphism (Static Polymorphism)**:

This type of polymorphism is determined **at compile time**. The compiler knows which method to call based on the method signature (name, parameters, etc.) at the time of compilation.

**How does this work?**

- Compile-time polymorphism is typically achieved through **method overloading** or **operator overloading**.
- Method overloading occurs when multiple methods with the same name are defined in the same class but differ in their method signatures (different parameters).
- The compiler picks the correct method based on the method signature used at the time of the call.

Example:

```java
class MathOperations {
    int add(int a, int b) {
        return a + b;
    }
    
    double add(double a, double b) {
        return a + b;
    }
}

public class Main {
    public static void main(String[] args) {
        MathOperations obj = new MathOperations();
        System.out.println(obj.add(5, 3)); // Calls int version: Output 8
        System.out.println(obj.add(2.5, 3.5)); // Calls double version: Output 6.0
    }
}
```

In this example, the `add` method is overloaded. The compiler determines which version of the method to call at compile time based on the argument types passed to it.

#### 2. **Run-Time Polymorphism (Dynamic Polymorphism)**:

Run-time polymorphism occurs when the method to be called is determined **at runtime**, rather than at compile time. This is usually achieved through **method overriding** in a class hierarchy where a subclass provides a specific implementation for a method defined in the superclass.

**How does this work?**

- The actual object type (the subclass type) determines which version of a method to invoke, even if the reference variable is of the superclass type.
- Run-time polymorphism allows for **dynamic method dispatch**, where the method execution is decided at runtime based on the actual object type.

### Example of Run-Time Polymorphism

```java
class Base {
    void display() {
        System.out.println("Base class");
    }
}

class Child extends Base {
    void display() {
        System.out.println("Child class");
    }
}

public class Main {
    public static void main(String[] args) {
        Base obj = new Child();  // Polymorphic variable
        obj.display();  // Output: Child class
    }
}
```

#### Explanation:

- In this example, we have two classes: `Base` and `Child`, where `Child` extends `Base` and overrides the `display` method.
- The variable `obj` is of type `Base`, but it holds a reference to a `Child` object.
- When `obj.display()` is called, even though the reference is of type `Base`, the actual method called is from the `Child` class, because the object `obj` is pointing to a `Child` instance.
- This is **run-time polymorphism** because the method that gets called (`Child`'s version of `display`) is determined at runtime, based on the actual object type (`Child`).

### Advantages of Polymorphism:

1. **Simplifies Code**: You can use a single reference variable to refer to objects of different classes.
2. **Extensibility**: New classes can be added to a system without changing existing code. As long as the new classes adhere to the same interface or inherit from the same superclass, polymorphism will ensure that existing code continues to work seamlessly.
3. **Method Overriding**: Enables dynamic method calls, where a superclass reference can be used to call methods that are overridden in subclasses.

### References:

- Polymorphism is central to achieving the **Open/Closed Principle**, a key tenet of software design that states: _"Software entities (classes, modules, functions, etc.) should be open for extension, but closed for modification."_ Polymorphism allows you to add new functionality (by extending existing classes or interfaces) without modifying existing code.

---

I hope this explanation gives you a better understanding of polymorphism! Let me know if you need further clarification or more examples.