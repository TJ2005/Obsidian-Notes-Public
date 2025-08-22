---
Title: "Errors & Error Handling"
Status: 
marker: 
tags: 
Date: "2025.04.03"
Time: "10:16"
---
# Errors & Error Handling
An error is any unexpected Resul

write error handling short snippet

unepxpected outputs

good programmers dont forget to error handle

error types

syntax not been followed

logic doesnt perform the way it was intended to

runtime error detects an impossible operatio

runtime error

util scanners example

scanner takes an input but if u put a string or float in then runtime error

Exceptions are buuilt into the java language and are to programs
representation of error conditions
describes errors
errors can be caught and handled by program
isolate the code that deals with the error condition from regular program logic

## Common Exception
string s = null
s.length() gives an error nll point exception

int result = 30/0 arithmetic exception

arrayindexoutofboundsexceptions

for loop example of arrayindexoutofbounds and normal outofbounds

java.lang.arrayindexoutofbounds is a class in lang module of package java

## checked and unchecked exceptions
- Compiler forces the programmer to check and deal with the exception
	- Non fatal to program execution
	- file not found, arrayindoutofbounds, number format conv
	- checked exception must be handled in ur code
- Unchcked Excepition
	- Fatal to program execution
	- Cant do anything with an unchecked exception
	- Program terminates
	- Null Pointer example

### Coding Excetions
- Try Catch mechanism or by a throws clause in a declaration
- wherever the code triggers an exception the normal code logic is placed within the try block
- in the event of error the catch block is supposed to  be the code that executes instead of the try block which failed

```java
example of try catch
```

Other way to do is 
```java
throwsIOException{
normal code with some I/O
}
```

```java
throws illegalargumentException
throw new illegal argument exception("Radius cannot be negative")
```


# REVISED DRAFT
# Errors & Error Handling in Java

## What is an Error?

An error is any unexpected result in a program. Good programmers always handle errors properly to prevent unexpected failures and ensure smooth execution.

## Types of Errors

1. **Syntax Errors**: Occur when the syntax rules of Java are not followed, such as missing semicolons or incorrect method declarations.
    
2. **Logic Errors**: The program runs without crashing but does not produce the intended results due to incorrect logic.
    
3. **Runtime Errors**: Occur during execution when an impossible operation is detected, such as division by zero.
    

### Example: Runtime Error with Scanner

When using `Scanner` to take user input, entering an invalid type (e.g., providing a string when an integer is expected) can cause a `java.util.InputMismatchException`.

## Exceptions in Java

Exceptions are built into the Java language to represent error conditions. They:

- Describe errors encountered during execution.
    
- Can be caught and handled by the program.
    
- Allow isolating error-handling logic from regular program logic.
    

### Common Exceptions

```java
String s = null;
s.length();  // NullPointerException
```

```java
int result = 30 / 0;  // ArithmeticException
```

```java
int[] arr = new int[5];
arr[10] = 3;  // ArrayIndexOutOfBoundsException
```

### Example: ArrayIndexOutOfBoundsException

```java
int[] numbers = {1, 2, 3};
for (int i = 0; i <= numbers.length; i++) {  // This causes an error
    System.out.println(numbers[i]);
}
```

`java.lang.ArrayIndexOutOfBoundsException` belongs to the `java.lang` package.

## Checked and Unchecked Exceptions

### Checked Exceptions:

- The compiler forces the programmer to handle these exceptions.
    
- Non-fatal to program execution.
    
- Examples:
    
    - `FileNotFoundException`
        
    - `NumberFormatException`
        
- Checked exceptions must be handled in the code.
    

### Unchecked Exceptions:

- Fatal to program execution.
    
- Cannot be handled at runtime; the program terminates.
    
- Example:
    
    ```java
    String s = null;
    s.length(); // NullPointerException
    ```
    

## Exception Handling in Java

### Using Try-Catch

The `try` block contains the code that may throw an exception, while the `catch` block handles the error.

```java
try {
    int a = 30 / 0;
} catch (ArithmeticException e) {
    System.out.println("Cannot divide by zero!");
}
```

### Using `throws`

If a method may cause an exception, it can declare it using `throws`.

```java
public void readFile() throws IOException {
    // Code that may throw an IOException
}
```

### Throwing Exceptions Manually

Exceptions can be thrown explicitly using `throw`.

```java
if (radius < 0) {
    throw new IllegalArgumentException("Radius cannot be negative");
}
```

### Conclusion

Error handling is essential for writing robust programs. Java provides structured mechanisms like `try-catch`, `throws`, and `throw` to manage exceptions efficiently and prevent unexpected crashes.

###### Information
- date: 2025.04.03
- time: 10:16