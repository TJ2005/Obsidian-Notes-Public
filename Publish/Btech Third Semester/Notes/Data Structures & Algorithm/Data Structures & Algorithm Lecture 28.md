---
Title: Data Structures & Algorithm Lecture 2
Status: 
marker: 
tags: 
Date: 2024-07-19
Time: 09:24
---
# Data Structures & Algorithm Lecture 2

# Unit 1 Content

## Index
- [Arrays](#arrays)
  - [Array Characteristics](#array-characteristics)
  - [Array Declaration](#array-declaration)
  - [Using `#define` for Array Size](#using-define-for-array-size)
  - [Preferred Approach](#preferred-approach)
  - [Additional Notes](#additional-notes)
  - [Example](#example)
- [Storage Classes](#storage-classes)
  - [Common Storage Classes](#common-storage-classes)
  - [Additional Considerations](#additional-considerations)
- [Non Indexed](#non-indexed)
- [Recursion](#recursion)
- [References](#references)
- [Homework](#homework)

## Data Structures Chart

## Data Abstraction
Data Abstraction refers to providing only essential information about the data to the outside world, hiding the background details or implementation.
Abstraction focuses on "What" and not "how". When we declare a function with syntax it is considered as abstraction.

Ex:

## Abstract Data Type
ADT is an abstraction of a data structure. ADT will be fixed for data structure.
It offers
- Data Stored
- Operation on the data
- Error Conditions associated with the operations

ADT should handle errors too.
Ex: In stack, with respect to push and pop, when someone tries to push an element in an array with no more memory, it will throw a stack overflow error.

# Unit 2 Content


## Arrays

### Array Characteristics:

- **Homogeneous:** All elements must be of the same data type.
- **Contiguous Memory Allocation:** Elements are stored in consecutive memory locations.
- **Fixed Size:** The size of an array is determined at declaration and cannot be changed dynamically.
- **Access:** Elements are accessed using an index, which starts from 0.
- In CPP array index is never checked for validity.
- Array Boundaries is only checked in Java
- Memory representation of array
	- Depending on the priority given to the array for sequentially indexing its called row major or Column Major.
- Array Traversal
- ```
```cpp
int main(){
	const int SIZE = 5; // Defines the size N for 5 elements
	int i,A[SIZE]; // declares the arrays element as type integer
	cout<<"\n Enter Numbers:";
	for(int i;i<SIZE;i++){
		cin>>A[i];
	}
	cout<<"Array entered by you:";
	for(i=0;i<=SIZE;i++){            // This part is called Traversal
		cout<<A[i];
	}
}](<
   
```

# Data Structures & Algorithm Lecture 2

# Unit 1 Content

## Index
- [Data Structures Chart](#data-structures-chart)
- [Data Abstraction](#data-abstraction)
- [Abstract Data Type](#abstract-data-type)

## Data Structures Chart

## Data Abstraction
Data Abstraction refers to providing only essential information about the data to the outside world, hiding the background details or implementation.
Abstraction focuses on "What" and not "how". When we declare a function with syntax it is considered as abstraction.

Ex:
- Remote Device Interface
- Car interface

## Abstract Data Type
ADT is an abstraction of a data structure. ADT will be fixed for data structure.
It offers
- Data Stored
- Operation on the data
- Error Conditions associated with the operations

ADT should handle errors too.
Ex: In stack, with respect to push and pop, when someone tries to push an element in an array with no more memory, it will throw a stack overflow error.

# Unit 2 Content

## Index
- [Array](#arrays)
  - Traversal Insertion Deletion
  - Representation of it in memory
- [Stack](#stack)
  - Applications
  - Expression
  - Conversion
  - Evaluation (Polish Notation)
  - Recursion
- [Queue](#queue)

## Arrays

### Array Characteristics:

- **Homogeneous:** All elements must be of the same data type.
- **Contiguous Memory Allocation:** Elements are stored in consecutive memory locations.
- **Fixed Size:** The size of an array is determined at declaration and cannot be changed dynamically.
- **Access:** Elements are accessed using an index, which starts from 0.
- In CPP array index is never checked for validity.
- Array Boundaries is only checked in Java
- Memory representation of array
	- Depending on the priority given to the array for sequentially indexing its called row major or Column Major.
- Array Traversal
- ```
```cpp
int main(){
	const int SIZE = 5; // Defines the size N for 5 elements
	int i,A[SIZE]; // declares the arrays element as type integer
	cout%3C<"\n Enter Numbers:";
	for(int i;i<SIZE;i++){
		cin%3E>A[i];
	}
	cout<<"Array entered by you:";
	for(i=0;i<=SIZE;i++){            // This part is called Traversal
		cout<<A[i];
	}
}
```

### Array Declaration:


```cpp
data_type array_name[size];
```

- `data_type`: Specifies the data type of elements (e.g., int, float, char).
- `array_name`: Name given to the array.
- `size`: Number of elements the array can hold.

### Using `#define` for Array Size:

While using `#define` for array size can be convenient, it's generally not recommended in modern C++ due to potential issues like:

- **Readability:** Makes code less readable as the constant's meaning is not clear.
- **Flexibility:** Limits the array size to a fixed value, reducing adaptability.

### Preferred Approach:

- Use `const` variables for array sizes:
    
    
    ```cpp
    const int MAX_SIZE = 100;
    int myArray[MAX_SIZE];
    ```
    

### Additional Notes:

- **Array Bounds:** Accessing elements outside the array's bounds leads to undefined behavior.
- **Multidimensional Arrays:** Arrays can have multiple dimensions.
- **Array Initialization:** You can initialize arrays during declaration.

### Example:


```cpp
#include <iostream>

int main() {
    const int MAX_SIZE = 5;
    int numbers[MAX_SIZE] = {1, 2, 3, 4, 5};

    for (int i = 0; i < MAX_SIZE; ++i) {
        std::cout << numbers[i] << " ";
    }

    return 0;
}
```

## Storage Classes

Storage classes in programming define the lifetime, visibility, and storage location of variables. They influence how variables are managed within a program's memory.

**Key Points:**

- **Lifetime:** How long a variable exists during program execution.
- **Scope:** The region of the program where a variable can be accessed.
- **Storage Location:** Where the variable is stored in memory (e.g., registers, stack, heap, static data area).

### Common Storage Classes

1. **auto:** (default)
    
    - Lifetime: Exists within the block where it's declared.
    - Scope: Local to the block.
    - Storage: Typically on the stack.
    - Example:
        
        C++
        
        ```cpp
        void myFunction() {
            int x = 10; // auto by default
        }
        ```
        
2. **register:**
    
    - Lifetime: Same as auto.
    - Scope: Same as auto.
    - Storage: Suggests to the compiler to store the variable in a register for faster access. However, the compiler may ignore this request.
    - Example:
        
        ```cpp
        register int count = 0; // Request to store count in a register
        ```
        
3. **static:**
    
    - Lifetime: Exists throughout the program's execution.
    - Scope:
        - Within a function: Local to the function but retains its value between function calls.
        - Outside a function: Global variable with internal linkage (accessible only within the current file).
    - Storage: Static data area.
    - Example:
        ```cpp
        void myFunction() {
            static int count = 0; // Retains its value between calls
            count++;
        }
        ```
        
4. **extern:**
    
    - Lifetime: Exists throughout the program's execution.
    - Scope: Global variable with external linkage (accessible from other files).
    - Storage: Static data area.
    - Example:
        ```cpp
        // In file1.cpp
        extern int global_var; // Declare global_var
        
        // In file2.cpp
        int global_var = 42; // Define global_var
        ```
        

### Additional Considerations

- **Garbage Values:** Uninitialized variables typically contain random values (garbage) until assigned a proper value.
- **Scope Resolution Operator (::):** Used to access global variables or members of a class or namespace when there's a naming conflict.

### Non Indexed
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter the number of elements: ";
    cin >> n;

    int arr[n]; // Declare an array to store the elements

    // Loop to read n elements
    for (int i = 0; i < n; i++) {
        cout << "Enter value for index " << i << ": ";
        cin >> arr[i];
    }

    // Reading a new element (num)
    int num;
    cout << "Enter a new element: ";
    cin >> num;

    for (i = num; i >= n; i--) {
	    a[i+1] = a[i];
	}
}

```
## Recursion

# References

## Homework
- `int a[][] = {1,2,3,4}`
- `int a[][]={{1,2},{3,4}}`
- Deletion code

continued to [[Data Structures & Algorithm Lecture 3]]...