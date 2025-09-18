---
Title: Object Oriented Programming Lecture 7
Status: 
marker:
  - "[[Programming]]"
  - "[[Java]]"
tags: 
Date: 2025.01.30
Time: 10:10
---
Continued from [[Object Oriented Programming Lecture 7]]
# Access Modifiers
- Used for encapsulation
	- In java mostly everything is inside a class. That class encapsulates.
- Also called access specifiers, Visibility specifiers.
- Restricts the scope or visibility of a package, class, constructor, methods, variables or other data members.
- Access control for members of a class

![[IMG-20250730000528935.png]]
### 1. **Default Access Modifier** (Package-Private)

When no access modifier is specified, Java applies the **default access modifier**, which is also known as **package-private**. This means:

- **Accessible only within the same package**.
- Not accessible outside the package.

#### Example with Default Access Modifier:

##### `com/example/package1/ClassA.java`:

```java
package com.example.package1;

class ClassA {  // Default access modifier (package-private)
    void greet() {
        System.out.println("Hello from ClassA!");
    }
}

class ClassB {  // Default access modifier (package-private)
    void greet() {
        System.out.println("Hello from ClassB!");
    }
}
```

- Both `ClassA` and `ClassB` are **package-private**. They can be accessed **only within the same package**, i.e., `com.example.package1`.

##### `com/example/package2/TestAccess.java`:

```java
package com.example.package2;

// Import ClassA from package1 (this will work)
import com.example.package1.ClassA;

// Importing ClassB from package1 will cause an error because ClassB is package-private
// import com.example.package1.ClassB;  // Uncommenting this line will cause a compile-time error

public class TestAccess {
    public static void main(String[] args) {
        // This works because ClassA is imported (ClassA is in the same project but different package)
        ClassA classA = new ClassA();
        classA.greet();
        
        // This will fail if we uncomment the line that tries to import ClassB
        // ClassB classB = new ClassB();  // Compile-time error
    }
}
```

#### Explanation:

- **ClassA** can be imported and used in `TestAccess` because it is explicitly imported, even though it is in a different package.
- **ClassB** cannot be used in `TestAccess` because it is package-private, and the class is not accessible outside of its package (`com.example.package1`).

### 2. **Public Access Modifier**

A **public** class, method, or property is accessible from **any class in any package**. Public access allows the entity to be accessed universally.

#### Example with Public Access Modifier:

##### `com/example/package1/ClassA.java`:

```java
package com.example.package1;

public class ClassA {  // Public access modifier
    public void greet() {
        System.out.println("Hello from ClassA!");
    }
}
```

- `ClassA` is marked as `public`, so it can be accessed from anywhere.

##### `com/example/package2/TestAccess.java`:

```java
package com.example.package2;

// Importing ClassA from package1 (this works because ClassA is public)
import com.example.package1.ClassA;

public class TestAccess {
    public static void main(String[] args) {
        // This works fine because ClassA is public and accessible from any package
        ClassA classA = new ClassA();
        classA.greet();
    }
}
```

#### Explanation:

- **ClassA** is public, so it can be accessed and instantiated in `TestAccess` from a completely different package (`com.example.package2`).
- The `import` statement is used to bring `ClassA` into the `TestAccess` class so it can be used.

### 3. **Private Access Modifier**

The **private** access modifier restricts access to the class members (fields and methods) to the **same class only**. It **cannot** be used on a top-level class. Additionally, if a class has a private constructor, you cannot create an instance of the class from outside its own class.

#### Example with Private Access Modifier:

##### `com/example/package1/ClassA.java`:

```java
package com.example.package1;

public class ClassA {
    private String name = "ClassA";  // Private field

    private void greet() {  // Private method
        System.out.println("Hello from " + name);
    }

    // Constructor is private, so we cannot instantiate ClassA from outside
    private ClassA() {
        System.out.println("Private Constructor Called");
    }

    public static ClassA createInstance() {
        return new ClassA();  // Allowed within the class
    }
}
```

- The constructor is `private`, meaning you cannot instantiate `ClassA` directly from another class.
- The field `name` and the method `greet` are private, so they cannot be accessed outside the class.

##### `com/example/package2/TestAccess.java`:

```java
package com.example.package2;

import com.example.package1.ClassA;

public class TestAccess {
    public static void main(String[] args) {
        // Cannot create an instance of ClassA because the constructor is private
        // ClassA classA = new ClassA();  // Compile-time error

        // We need to use the public static method to create an instance of ClassA
        ClassA classA = ClassA.createInstance();  // This works because the method is public
        // However, we still can't access the private members like greet or name
    }
}
```

#### Explanation:

- **Private constructor** in `ClassA` prevents direct instantiation of `ClassA` outside its class. You can only create an instance through a **public method** (`createInstance()`).
- The `greet()` method and `name` field in `ClassA` are **private**, meaning they cannot be accessed from `TestAccess` in `com.example.package2`.

---

### Summary of Access Modifiers:

1. **Default Access (Package-Private)**:
    
    - Can be accessed only within the same package.
    - Cannot be accessed from a different package, even if they are part of the same project.
2. **Public Access**:
    
    - Can be accessed from **any class** in any package.
    - It must be imported if it's in a different package.
3. **Private Access**:
    
    - Can only be accessed within the **same class**.
    - Cannot be used on top-level classes (only fields, methods, and constructors).
    - Prevents direct instantiation if the constructor is private.

### Example Structure of the Files:

```
com/
  example/
    package1/
      ClassA.java
    package2/
      TestAccess.java
```


---
# Array
Is a data structures storing an array of elements of same type

### Declaration

- We initialized the array with the new parameter.
- This implies that the array is actually a class

```java
arrayRefVar=new datatype[arraySize];

//example
double[] myList; 

myList = new double[10];
```

### Parameterizing arrays

```java
public static void printArray(int[] array){
	for(int i=0;i<array.length;i++){
		System.out.print(array[i]+" ")
	}
}
```

```java
int[] list={1,2,3,4}
printArray(list)
```
#### Pass by Value

- Java **Pass by value** to pass parameters to a method
- For a parameter of a primitive type value, the actual value is passed.
- Changing the value of the local parameter inside the method does not affect the value of the variable outside the method.
- For passing an array type, the value contains a reference to the array. Any changes made to the array will affect the main array.

#### Returning Array Types
Since there is no Concept of pointers in java we simply return the array and just like the array was passed by reference so is the return type.

```java
public class ArrayDemo
{
	public static int[] getArray()
	{
		int[] arr={1,2,3,4,5,6}
		return arr
	}
	public static void main(string args[]){
		int arr[] = getArray();
		
	}
}
// theres no pointers concept
```

### Array (class) has Inbuilt functions
In [[#Declaration|Declaration]] part of this page we had analysed that the array is actually a class. This implies that there are multiple functions inbuilt for array.
```java
double[] numbers={1,2,3,4,7,8,2}
char[] chararray={'a','b','Z','D','d'}
```
#### For Sorting
The input parameter can be any type this is because the functions are [[Functions ( Methods ) in Java#Overloading Methods|overloaded]].

```java
Array.sort(numbers)
Array.sort(chararray)
```




# References
chatgpt for examples

###### Information
- date: 2025.01.30
- time: 10:10