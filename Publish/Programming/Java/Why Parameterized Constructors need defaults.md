### **Default Constructors**

In Java, when a class does not explicitly define any constructors, the Java compiler automatically provides a **default constructor** with no parameters. This constructor has an empty body, and its purpose is to initialize the object with default values.

#### **Implicit Default Constructor**

If you don't define any constructors in your class, the compiler will implicitly create a default constructor for you:

```java
class MyClass {
    int x;
    String name;
    
    // Implicitly defined default constructor
    // MyClass() { 
    //     // No code needed, just assigns default values like 0, null
    // }
}
```

In this case, `x` will be initialized to `0` (the default value for an integer), and `name` will be initialized to `null` (the default value for a String).

### **Why is it Compulsory to Define a Default Constructor When You Have a Parameterized Constructor?**

When you define a **parameterized constructor**, Java **does not provide a default constructor** anymore. This is because the presence of the parameterized constructor means you have explicitly defined how an object should be initialized. However, if you want to still allow the option of creating an object without passing parameters, you **must explicitly define the default constructor**.

Let’s break it down:

- **If you define only a parameterized constructor**, the Java compiler **will not provide a default constructor** because it assumes the object can only be created using that specific constructor.
    
    Example:
    
    ```java
    class MyClass {
        int x;
        
        MyClass(int newX) {
            x = newX;
        }
    }
    
    // You cannot create an object like this anymore:
    // MyClass obj = new MyClass();  // Error: no default constructor
    ```
    
- **If you want both options**: creating objects using a parameterized constructor **and** creating objects using a default constructor, you **must explicitly define the default constructor**:
    
    ```java
    class MyClass {
        int x;
        
        MyClass(int newX) {
            x = newX;
        }
        
        // Explicit default constructor
        MyClass() {
            x = 0;  // default value
        }
    }
    
    MyClass obj1 = new MyClass();      // Calls the default constructor
    MyClass obj2 = new MyClass(10);    // Calls the parameterized constructor
    ```
    

This is necessary because Java needs to know that if you want to create an object without any arguments (i.e., using the default constructor), you have provided a definition for it. Otherwise, the compiler assumes that you only want to use the parameterized constructor.

### **Summary:**

- If you define a **parameterized constructor**, the **default constructor is no longer automatically provided**.
- If you still want to use the default constructor, you **must define it explicitly**.