---
Title: "Abstraction"
Status: 
marker: 
tags: 
Date: "2025.03.10"
Time: "08:16"
---
# Abstraction
Is the process of identifying the only required characteristics of an object and ignoring the irrelevant details. In Java, abstraction is achieved using Abstract classes and interfaces.
Main Goals of abstraction are protection against unwanted changes. It helps to reduce programming complexity and effort.
Data abstraction is the process of hiding certain details and showing only essential information to the user.

Encapsulation is data hiding (information hiding) while abstraction is detail hiding (implementation hiding).
Encapsulation groups together data and methods that act upon the data
Data abstraction deals with exposing the interface to the user.

### Advantages
- It reduces programming complexity and effort.
- Avoids code duplication and increases reusability.
- Helps increase security of an application or program as only important details are provided to the user.
- Helps to increase the speed of the application as only important details are provided to the user.

## **Abstract Class**
Is a restricted class that cannot be used to create objects (to access it, it must be inherited from another class). To declare an abstract class, use the abstract keyword. Inheritance is the key feature of an abstract class.
If there is a class person that student and teacher inherits, then person is an abstract class. It is a blueprint for other classes. 
##### Key Takeaways
- Abstract Class cannot be instantiated using `new` keyword directly.
- However it can be indirectly be created using polymorphism ( child class instantiates super class object).
- An abstract class can have both abstract and concrete (fully implemented) methods.
- An abstract class can also have constructors, static methods, and fields.
- - A class does not have to be inherited just to access an abstract class—it can still reference it through polymorphism.

### Reasons for making an Abstract Class
- Code Reusability
- Shared Fields
- Consistency
### Examples

```java
abstract class Person {
    Person() {
        System.out.println("Abstract Person class constructor called!");
    }

    abstract void displayRole();  // Abstract method
}

class Student extends Person {
    Student() {
        System.out.println("Student constructor called!");
    }

    @Override
    void displayRole() {
        System.out.println("I am a student.");
    }
}

public class Main {
    public static void main(String[] args) {
        Student s = new Student();  // Creating Student instance
        s.displayRole();
    }
}
```

Output:
```java
Abstract Person class constructor called!
Student constructor called!
I am a student.
```

```java

```


---

## **Abstract Method**

An abstract method is a method that is declared but does not have an implementation. It can only be used inside an abstract class. The subclass that inherits the abstract class **must override** and provide an implementation for the abstract method.

### **Key Takeaways**

- Declared using the `abstract` keyword.
- Does **not** have a method body.
- Must be implemented in the subclass unless the subclass is also abstract.
- Used to enforce a contract between the superclass and its subclasses.

### **Example: Abstract Method**

```java
abstract class Animal {
    // Abstract method (does not have a body)
    abstract void makeSound();

    // Concrete method (has a body)
    void sleep() {
        System.out.println("Sleeping...");
    }
}

class Dog extends Animal {
    // Implementing the abstract method
    @Override
    void makeSound() {
        System.out.println("Bark! Bark!");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.makeSound(); // Calls overridden method
        dog.sleep();     // Calls concrete method from superclass
    }
}
```

### **Output**

```
Bark! Bark!
Sleeping...
```

---



# References


###### Information
- date: 2025.03.10
- time: 08:16