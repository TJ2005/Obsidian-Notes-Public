---
Title: "Object Oriented Programming Lecture 9"
Status: 
marker: 
tags: 
Date: "2025.02.13"
Time: "10:06"
---
z
# **Two-Dimensional Arrays in Java**

## **1. Declaring a 2D Array**

A two-dimensional array in Java is essentially an array of arrays. It can be declared as follows:

```java
dataType[][] arrayName = new dataType[rows][columns];
```

Example:

```java
int[][] matrix = new int[3][3];  // Declares a 3x3 integer matrix
```

---

## **2. Initializing a 2D Array**

You can initialize a 2D array at the time of declaration as shown:

```java
int[][] matrix = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};
```

---

## **3. Printing a 2D Array Using Nested Loops**

Use nested `for` loops to print a 2D array:

```java
public class TwoDArrayExample {
    public static void main(String[] args) {
        int[][] matrix = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };

        // Nested loops to print the 2D array
        for (int i = 0; i < matrix.length; i++) {  // Iterating over rows
            for (int j = 0; j < matrix[i].length; j++) {  // Iterating over columns
                System.out.print(matrix[i][j] + " ");
            }
            System.out.println();  // New line after each row
        }
    }
}
```

### **Output:**

```
1 2 3  
4 5 6  
7 8 9  
```

---

# **ArrayLists in Java**

## **What is an ArrayList?**

An **ArrayList** is a resizable array that grows and shrinks dynamically as elements are added or removed. It provides an easier and more flexible alternative to arrays.

---

## **Declaring a 2D ArrayList**

A 2D ArrayList is an `ArrayList` of `ArrayList`s:

```java
ArrayList<ArrayList<DataType>> listName = new ArrayList<>();
```

Example:

```java
ArrayList<ArrayList<Integer>> matrix = new ArrayList<>();
```

---

## **Initializing a 2D ArrayList**

Since an `ArrayList` is dynamically sized, you must manually add rows (sub-lists):

```java
import java.util.ArrayList;

public class TwoDArrayList {
    public static void main(String[] args) {
        ArrayList<ArrayList<Integer>> matrix = new ArrayList<>();

        // Adding rows
        for (int i = 0; i < 3; i++) {
            matrix.add(new ArrayList<>());
        }

        // Adding elements
        int value = 1;
        for (int i = 0; i < 3; i++) {
            for (int j = 0; j < 3; j++) {
                matrix.get(i).add(value++);  // Add values to each row
            }
        }

        // Printing the 2D ArrayList
        for (int i = 0; i < matrix.size(); i++) {  // Iterating over rows
            for (int j = 0; j < matrix.get(i).size(); j++) {  // Iterating over columns
                System.out.print(matrix.get(i).get(j) + " ");
            }
            System.out.println();  // New line after each row
        }
    }
}
```

---

## **Operations on ArrayList**

### **Common Operations:**

1. **Add Elements**:
    
    ```java
    matrix.get(0).add(10);  // Adds 10 to the first row
    ```
    
2. **Access Elements**:
    
    ```java
    int value = matrix.get(1).get(2);  // Access element at (row 1, column 2)
    ```
    
3. **Change Elements**:
    
    ```java
    matrix.get(2).set(1, 99);  // Change element at (row 2, column 1) to 99
    ```
    
4. **Remove Elements**:
    
    ```java
    matrix.get(1).remove(0);  // Removes element at (row 1, column 0)
    ```
    

---

# **Java ArrayList Functions**

|**Method**|**Description**|
|---|---|
|`void add(int index, E element)`|Inserts the specified element at the specified position in the list. Shifts elements to the right.|
|`boolean add(E element)`|Appends the specified element to the end of the list. Returns `true` if successful.|
|`void clear()`|Removes all elements from the list, making it empty.|
|`E get(int index)`|Returns the element at the specified index. Throws `IndexOutOfBoundsException` if out of range.|
|`boolean isEmpty()`|Returns `true` if the list contains no elements, otherwise `false`.|
|`int lastIndexOf(Object o)`|Returns the last occurrence index of the specified element, or `-1` if not found.|
|`boolean contains(Object o)`|Returns `true` if the list contains the specified element, otherwise `false`.|
|`int indexOf(Object o)`|Returns the index of the first occurrence of the specified element, or `-1` if not found.|
|`E remove(int index)`|Removes the element at the specified index and returns the removed element.|
|`int size()`|Returns the number of elements in the list.|

---

## **Example Usage**

```java
import java.util.ArrayList;

public class ArrayListFunctionsExample {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();

        // Adding elements
        list.add("Apple");
        list.add("Banana");
        list.add("Cherry");
        list.add(1, "Blueberry");  // Insert at index 1

        // Accessing elements
        System.out.println("Element at index 2: " + list.get(2));

        // Checking if list contains an element
        System.out.println("Contains 'Banana': " + list.contains("Banana"));

        // Finding index of an element
        System.out.println("Index of 'Cherry': " + list.indexOf("Cherry"));
        System.out.println("Last index of 'Banana': " + list.lastIndexOf("Banana"));

        // Removing an element
        System.out.println("Removed element: " + list.remove(1));

        // Checking if the list is empty
        System.out.println("Is list empty? " + list.isEmpty());

        // Getting the size of the list
        System.out.println("Size of list: " + list.size());

        // Clearing the list
        list.clear();
        System.out.println("List cleared. Is empty? " + list.isEmpty());
    }
}
```

---

# **Array of Objects in Java**

An array of objects can store references to instances of a class (object references). Here’s an example using a `Student` class:

## **Example:**

```java
// Student class with id and name
class Student {
    int id;
    String name;

    // Constructor to initialize Student object
    public Student(int id, String name) {
        this.id = id;
        this.name = name;
    }

    // Method to display student details
    public void display() {
        System.out.println("ID: " + id + ", Name: " + name);
    }
}

// Main class to demonstrate an array of Student objects
public class StudentArrayExample {
    public static void main(String[] args) {
        // Creating an array of Student objects
        Student[] students = new Student[3];

        // Initializing the array with Student objects
        students[0] = new Student(101, "Alice");
        students[1] = new Student(102, "Bob");
        students[2] = new Student(103, "Charlie");

        // Printing student details using a loop
        for (Student student : students) {
            student.display();
        }
    }
}
```

### **Output:**

```
ID: 101, Name: Alice
ID: 102, Name: Bob
ID: 103, Name: Charlie
```

---

# **Vector Class**

The **`Vector`** class implements a growable array of objects. It is thread-safe and can dynamically resize.

## **Constructors**

|**Constructor**|**Description**|
|---|---|
|`Vector()`|Creates a default vector with an initial capacity of **10**.|
|`Vector(int size)`|Creates a vector with an initial capacity specified by `size`.|
|`Vector(int size, int incr)`|Creates a vector with an initial capacity of `size` and a growth increment of `incr`.|
|`Vector(Collection<? extends E> c)`|Creates a vector containing the elements of the specified collection `c`.|

---

### **Incremental Logic in Vectors**

- **With `incr`**: The vector grows by the increment size (`incr`).
- **Without `incr`**: The vector doubles its capacity when resized.

---

### **Example Usage:**

```java
import java.util.*;

public class VectorExample {
    public static void main(String[] args) {
        // Default constructor (capacity = 10)
        Vector<Integer> v1 = new Vector<>();
        System.out.println("Capacity of v1: " + v1.capacity());

        // Constructor with initial size
        Vector<Integer> v2 = new Vector<>(5);
        System.out.println("Capacity of v2: " + v2.capacity());

        // Constructor
```

with initial size and increment Vector v3 = new Vector<>(5, 2); System.out.println("Capacity of v3: " + v3.capacity()); } }

```

---

