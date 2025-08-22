---
Title: "Object Oriented Programming Lecture 10"
Status: 
marker: 
tags: 
Date: "2025.02.17"
Time: "08:08"
---
# Java String Class

The `String` class in Java is a fundamental part of the language, providing numerous built-in methods to manipulate and analyze string data. Below is an overview of some common `String` methods with examples.

## Character Access

### `charAt(int index)`
- **Description**: Returns the character at the specified index.
- **Example**:
  ```java
  String str = "Hello";
  char ch = str.charAt(1); // 'e'
  ```

## String Comparison

### `equals(Object anObject)`
- **Description**: Compares this string to the specified object.
- **Example**:
  ```java
  String str1 = "Hello";
  String str2 = "Hello";
  boolean isEqual = str1.equals(str2); // true
  ```

### `equalsIgnoreCase(String anotherString)`
- **Description**: Compares this string to another string, ignoring case considerations.
- **Example**:
  ```java
  String str1 = "Hello";
  String str2 = "hello";
  boolean isEqualIgnoreCase = str1.equalsIgnoreCase(str2); // true
  ```

## String Search

### `contains(CharSequence s)`
- **Description**: Returns true if and only if this string contains the specified sequence of char values.
- **Example**:
  ```java
  String str = "Hello World";
  boolean contains = str.contains("World"); // true
  ```

### `indexOf(int ch)`
- **Description**: Returns the index within this string of the first occurrence of the specified character.
- **Example**:
  ```java
  String str = "Hello";
  int index = str.indexOf('e'); // 1
  ```

### `indexOf(String str)`
- **Description**: Returns the index within this string of the first occurrence of the specified substring.
- **Example**:
  ```java
  String str = "Hello World";
  int index = str.indexOf("World"); // 6
  ```

### `lastIndexOf(String str)`
- **Description**: Returns the index within this string of the last occurrence of the specified substring.
- **Example**:
  ```java
  String str = "Hello World, World!";
  int index = str.lastIndexOf("World"); // 13
  ```

## String Modification

### `concat(String str)`
- **Description**: Concatenates the specified string to the end of this string.
- **Example**:
  ```java
  String str1 = "Hello";
  String str2 = "World";
  String result = str1.concat(str2); // "HelloWorld"
  ```

### `replace(char oldChar, char newChar)`
- **Description**: Returns a new string resulting from replacing all occurrences of `oldChar` in this string with `newChar`.
- **Example**:
  ```java
  String str = "Hello";
  String newStr = str.replace('l', 'L'); // "HeLLo"
  ```

### `substring(int beginIndex)`
- **Description**: Returns a new string that is a substring of this string.
- **Example**:
  ```java
  String str = "Hello World";
  String subStr = str.substring(6); // "World"
  ```

### `toLowerCase()`
- **Description**: Converts all of the characters in this `String` to lower case.
- **Example**:
  ```java
  String str = "Hello";
  String lowerStr = str.toLowerCase(); // "hello"
  ```

### `toUpperCase()`
- **Description**: Converts all of the characters in this `String` to upper case.
- **Example**:
  ```java
  String str = "Hello";
  String upperStr = str.toUpperCase(); // "HELLO"
  ```

### `trim()`
- **Description**: Returns a string whose value is this string, with any leading and trailing whitespace removed.
- **Example**:
  ```java
  String str = "  Hello World  ";
  String trimmedStr = str.trim(); // "Hello World"
  ```

## String Conversion

### `valueOf(Object obj)`
- **Description**: Converts different types of values into a string.
- **Example**:
  ```java
  String number = String.valueOf(19); // "19"
  ```

### `toString()`
- **Description**: Returns the string representation of the object.
- **Example**:
  ```java
  Integer num = 10;
  String str = num.toString(); // "10"
  ```

## String Concatenation

### Using `+` Operator
- **Description**: Concatenates two strings using the `+` operator.
- **Example**:
  ```java
  String str1 = "Hello";
  String str2 = "World";
  String result = str1 + str2; // "HelloWorld"
  ```

### Using `concat()` Method
- **Description**: Concatenates two strings using the `concat()` method.
- **Example**:
  ```java
  String str1 = "Hello";
  String str2 = "World";
  String result = str1.concat(str2); // "HelloWorld"
  ```

## String Splitting

### `split(String regex)`
- **Description**: Splits this string around matches of the given regular expression.
- **Example 1**:
  ```java
  String str = "Hello World";
  String[] result = str.split(" "); // ["Hello", "World"]
  ```
- **Example 2**:
  ```java
  String str = "apple,banana;cherry#grape$orange";
  String[] result = str.split("[,;#$]"); // ["apple", "banana", "cherry", "grape", "orange"]
  ```
- **Example 3**:
  ```java
  String str = "one:two:three:four";
  String[] result = str.split(":", 3); // ["one", "two", "three:four"]
  ```

## Retrieving Individual Characters in a String

- **Do not use**: `message[0]`
- **Use**: `message.charAt(index)`
- **Note**: Index starts from 0.
---
## Access Functions

- **String is an array of characters**, but we can't access it using `s[0]`.
- **Use**: `charAt(index)` function.
Certainly! The `toString()` method in Java is often overridden to provide a string representation of an object. This allows the object to be printed directly using `System.out.println()`, which internally calls the `toString()` method. Here's a corrected and improved version of your code snippet with an explanation:

```java
class Student {
    String name;
    int rollNo;

    // Constructor to initialize the Student object
    Student(String name, int rollNo) {
        this.name = name;
        this.rollNo = rollNo;
    }

    // Overriding the toString() method to provide a string representation of the Student object
    @Override
    public String toString() {
        return "Student{name=" + name + ", rollNo=" + rollNo + "}";
    }

    public static void main(String[] args) {
        // Creating instances of Student
        Student stu1 = new Student("xxx", 10);
        Student stu2 = new Student("yyy", 20);

        // Printing the Student objects directly, which calls the overridden toString() method
        System.out.println("Student 1: " + stu1);
        System.out.println("Student 2: " + stu2);
    }
}
```

### Explanation

- **`toString()` Method**: The `toString()` method is overridden in the `Student` class to return a string that represents the object's state. This method is called automatically when an object is passed to `System.out.println()`.

- **Direct Printing**: When `System.out.println("Student 1: " + stu1);` is executed, Java internally calls `stu1.toString()` to get the string representation of `stu1`. This allows the object to be printed directly without explicitly calling `toString()`.

- **Output**: The output of the above code will be:
  ```
  Student 1: Student{name=xxx, rollNo=10}
  Student 2: Student{name=yyy, rollNo=20}
  ```

This demonstrates how overriding `toString()` can be useful for providing meaningful string representations of objects, making it easier to print and debug object states.

## References

- **Authors**: 
- **Date**: 2025.02.17
- **Time**: 08:08

