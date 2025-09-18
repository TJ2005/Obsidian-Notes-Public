---
Title: "Object Oriented Programming Lecture 12"
Status: 
marker: 
tags: 
Date: "2025.02.24"
Time: "08:12"
---
Continued from [[Unified Modelling Language]]
### Encapsulation & Data Hiding in Object-Oriented Programming

**Encapsulation** is a mechanism in object-oriented programming (OOP) where both the data (variables) and the methods that operate on the data are bundled together as a single unit. This principle ensures that an object's internal state is protected from unauthorized access or modification.

#### Key Concepts of Encapsulation:

- **Private Variables**: The class variables (also known as attributes or fields) are declared as `private`. This means they cannot be accessed directly from outside the class.
- **Getter and Setter Methods**: Access to these private variables is provided through **getter** and **setter** methods. These methods allow controlled access to the private data.

#### Getter and Setter Methods

- **Getter Method**: Used to retrieve the value of a private variable.
- **Setter Method**: Used to update the value of a private variable.

##### Naming Conventions:

- The getter and setter methods are generally named by prefixing the variable name with `get` and `set`, respectively.

Encapsulation is also known as **data hiding** because it hides the internal details of how the data is stored or modified, exposing only the necessary interface for interacting with the object.

---

### Example: Implementing Encapsulation in Java

```java
// Define the Person class
public class Person {
    // Declare private variable 'age'. This will not be directly accessible from outside the class
    private int age;

    // Getter method for the 'age' variable
    // This method allows external access to the value of 'age' in a controlled manner
    public int getAge() {
        return age; // Return the current value of 'age'
    }

    // Setter method for the 'age' variable
    // This method allows external code to modify the value of 'age' but with validation
    public void setAge(int age) {
        // Validation: Ensure the age is within a valid range (between 0 and 100)
        if (age >= 0 && age <= 100) {
            this.age = age; // If valid, set the value of 'age'
        } else {
            // If the age is not valid, print an error message
            System.out.println("Invalid age! Age must be between 0 and 100.");
        }
    }

    // Main method to demonstrate the use of encapsulation
    public static void main(String[] args) {
        // Create an object of the Person class
        Person person = new Person();

        // Set the 'age' value using the setter method
        person.setAge(25); // This is a valid age
        System.out.println("Age: " + person.getAge()); // Get the 'age' value using the getter method

        // Attempt to set an invalid age
        person.setAge(150); // This is an invalid age
        System.out.println("Age: " + person.getAge()); // The value of 'age' should remain unchanged
    }
}
```

**Explanation**:

- The `Person` class contains a private variable `age`, ensuring that it is protected from direct access from outside the class.
- The `getAge()` method is a getter method that allows other classes or code to retrieve the value of `age` in a controlled manner.
- The `setAge()` method is a setter method that allows modification of the `age` variable but includes validation to ensure that the age is within a valid range (between 0 and 100). If an invalid age is provided, an error message is printed, and the `age` remains unchanged.
- In the `main()` method, we create an instance of the `Person` class and demonstrate how the getter and setter methods work.

**Output**:

```plaintext
Age: 25
Invalid age! Age must be between 0 and 100.
Age: 25
```

---

### Nested Classes in Java

In Java, when a class is defined inside another class, it is known as a **nested class**. A nested class can be either **static** or **non-static** (inner class).

#### Static Nested Class

A static nested class is defined with the `static` keyword. Static nested classes can be instantiated without needing an instance of the outer class.

```java
// Define the Animal class
class Animal {
    // Static nested class Mammal
    static class Mammal {
        // Method to display information about mammals
        public void displayInfo() {
            System.out.println("I am a mammal");
        }
    }
}

// Main method to demonstrate the usage of static nested class
public class Main {
    public static void main(String[] args) {
        // Create an instance of the static nested class Mammal without an instance of Animal
        Animal.Mammal mammal = new Animal.Mammal();
        mammal.displayInfo(); // Calling the method to display info
    }
}
```

**Explanation**:

- The `Mammal` class is a static nested class inside the `Animal` class. Since it is static, we can instantiate it without needing an instance of `Animal`.
- In the `Main` class, we create an instance of `Mammal` using the syntax `Animal.Mammal` and call the `displayInfo()` method.

#### Non-Static Nested Class (Inner Class)

A non-static nested class, also known as an **inner class**, is defined inside an outer class and has access to the outer class's variables and methods, even if they are private.

```java
// Outer class
class Outer {
    // Inner class defined inside the Outer class
    class Inner {
        // Method inside the Inner class
        public void show() {
            System.out.println("In a nested class method");
        }
    }
}

// Main method to demonstrate the usage of inner class
public class MethodDemo {
    public static void main(String[] args) {
        // Create an instance of the Outer class
        Outer outer = new Outer();
        
        // Create an instance of the inner class by first creating the outer class instance
        Outer.Inner inner = outer.new Inner();
        
        // Call the method inside the Inner class
        inner.show();
    }
}
```

**Explanation**:

- The `Inner` class is defined inside the `Outer` class. To create an instance of the `Inner` class, we must first create an instance of the `Outer` class, as the inner class depends on the outer class's instance.
- In the `MethodDemo` class, we first instantiate the `Outer` class, then use that instance to create the `Inner` class instance. The `show()` method of the `Inner` class is called to display a message.

---

### Example 1: Nested Static and Non-Static Classes

```java
class Animal {
    // Static nested class Mammal
    static class Mammal {
        // Method to display info for Mammal
        public void displayInfo() {
            System.out.println("I am a mammal.");
        }
    }

    // Non-static nested class Reptile
    class Reptile {
        // Method to display info for Reptile
        public void displayInfo() {
            System.out.println("I am a reptile.");
        }
        
        // Method to eat for Reptile
        public void eat() {
            System.out.println("I eat food.");
        }
    }

    // Method to eat for Animal
    public void eat() {
        System.out.println("I eat food.");
    }
}

public class Main {
    public static void main(String[] args) {
        // Create an instance of Animal
        Animal animal = new Animal();
        
        // Create an instance of Reptile using the Animal instance
        Animal.Reptile reptile = animal.new Reptile();
        reptile.displayInfo();
        reptile.eat(); // Correct usage
        
        // Creating an instance of static nested class Mammal
        Animal.Mammal mammal = new Animal.Mammal();
        mammal.displayInfo();
        
        // Calling the eat() method from Animal
        animal.eat(); // Correct usage
    }
}
```

**Explanation**:

- The `Animal` class has both a static nested class `Mammal` and a non-static nested class `Reptile`.
- The `Mammal` class is static, so it can be instantiated without an `Animal` object.
- The `Reptile` class is non-static, so it requires an `Animal` instance to create a `Reptile` object.
- Both nested classes and the main class demonstrate the use of the `displayInfo()` and `eat()` methods.

### Example 2: Local Inner Classes (Non-Static)

```java
class Outer {
    // Method in the Outer class
    void outerMethod() {
        System.out.println("inside Outer class");

        // Inner class defined inside the outerMethod (Local inner class)
        class Inner {
            // Method in the Inner class
            void innerMethod() {
                System.out.println("inside Inner class");
            }
        }

        // Create an instance of Inner class
        Inner y = new Inner();
        y.innerMethod(); // Calls the method from Inner class
    }
}

public class MethodDemo {
    public static void main(String[] args) {
        // Create an instance of Outer class
        Outer x = new Outer();
        x.outerMethod(); // Calls the outer method

        // The following line would give an error because Inner class is local to outerMethod
        // Outer.Inner in = Outer.new Inner(); // Error: Cannot reference Inner from outside outerMethod
    }
}
```

**Explanation**:

- The `Inner` class is defined within the `outerMethod` of the `Outer` class. This makes it a **local inner class**, which can only be accessed within the method where it is defined.
- The `MethodDemo` class creates an instance of `Outer` and calls the `outerMethod()`. Inside `outerMethod()`, the `Inner` class is instantiated and its `innerMethod()` is called.

### Output for both examples:

```plaintext
Example 1:
I am a reptile.
I eat food.
I am a mammal.
I eat food.

Example 2:
inside Outer class
inside Inner class
```

### Advantages of Inner Classes in the Code:

```java
// Outer class that encapsulates data and functionality
class Outer {
    private int value;  // private member variable

    // Constructor to initialize the value
    public Outer(int value) {
        this.value = value;
    }

    // Getter method for 'value'
    public int getValue() {
        return value;
    }

    // Inner class that provides additional functionality
    class Inner {
        // Method in the inner class that accesses private members of the outer class
        public void show() {
            // Accessing the private member 'value' from the outer class
            System.out.println("The value is: " + value);
        }
    }

    // Method to demonstrate the encapsulation and organization
    public void demonstrateInnerClass() {
        // Creating an instance of the inner class and calling its method
        Inner inner = new Inner();
        inner.show();  // Calls the 'show' method of the inner class
    }
}

public class Main {
    public static void main(String[] args) {
        // Create an instance of the Outer class
        Outer outer = new Outer(10);
        
        // Access the outer class functionality and inner class functionality
        outer.demonstrateInnerClass();
    }
}
```


1. **Security with Private Data**
    - The `Inner` class has direct access to the private variables of the outer class (`value` in this case), making it possible to encapsulate sensitive data securely and expose it only to the inner class when needed.

2. **Packaging of the Class**:
    - The `Inner` class is closely tied to its outer class (`Outer`). This helps package related functionality together, keeping the logic of the application encapsulated within a specific outer class.

3. **Encapsulation**:
    - Inner classes help in encapsulating the functionality related to the outer class. The `Inner` class provides additional functionality while still being able to access the private members of the `Outer` class.

4. **Readable and Maintainable Code**:
    - By using inner classes, related functionality can be organized in a way that makes the code more readable and easier to maintain. The `Inner` class is used to encapsulate the code that is specific to the outer class but still logically part of the same context.


5. **Organize Package Structure**:
    - Inner classes help in keeping the related classes organized within the same file or package, which reduces the complexity and improves the package structure, especially when the inner class is tightly coupled with the outer class.


### Output:

```plaintext
The value is: 10
```
---

### Conclusion

Encapsulation and data hiding are powerful concepts that help secure and manage the internal state of objects. By using getter and setter methods, you can ensure that data is accessed and modified safely. Nested and inner classes allow you to organize code effectively, with static and non-static classes offering different levels of flexibility and access.


# References
- Continued to [[Inheritance]]


###### Information
- date: 2025.02.24
- time: 08:12