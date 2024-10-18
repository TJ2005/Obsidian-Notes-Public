---
Title: Web Programming Lecture 13
Status: 
marker:
  - "[[Web Programming]]"
  - "[[web development]]"
  - "[[HTML]]"
  - "[[JavaScript]]"
tags:
  - BTech
Date: 2024.08.28
Time: 13:14
---
# Web Programming - Lecture 13


## JavaScript
For some reason prebuilt functions are called **methods** here
### 1. Comparison Operators
- **Equality (`==`)**: Compares two values for equality, after converting both values to a common type.
- **Strict Equality (`===`)**: Compares two values for equality without converting their types.
- **Inequality (`!=`)**: Compares two values for inequality, after converting both values to a common type.
- **Strict Inequality (`!==`)**: Compares two values for inequality without converting their types.
- **Greater Than (`>`)**: Checks if the left value is greater than the right value.
- **Greater Than or Equal To (`>=`)**: Checks if the left value is greater than or equal to the right value.
- **Less Than (`<`)**: Checks if the left value is less than the right value.
- **Less Than or Equal To (`<=`)**: Checks if the left value is less than or equal to the right value.

### 2. Type of Function
- **`typeof` Operator**: Returns the type of the variable or expression. Common types include:
  - `"string"`
  - `"number"`
  - `"boolean"`
  - `"undefined"`
  - `"object"`
  - `"function"`
- **Example**:
```js
  console.log(typeof 42);           // "number"
  console.log(typeof "Hello");      // "string"
  console.log(typeof true);         // "boolean"
  console.log(typeof undefined);    // "undefined"
  console.log(typeof {key: "value"}); // "object"
  console.log(typeof function(){}); // "function"
  
 
```

### 3. `Number()` Method
- **Purpose**: Converts a value to the most logical number type variable.
- **Behavior**:
  - Converts strings that represent numbers to actual numbers.
  - Converts `false` to `0` and `true` to `1`.
  - If the value can't be converted to a number, it returns `NaN`.
- **Example**:
```js
  console.log(Number("42"));      // 42
  console.log(Number("42.5"));    // 42.5
  console.log(Number(true));      // 1
  console.log(Number(false));     // 0
  console.log(Number("Hello"));   // NaN
```
### 4. parseFloat()
- **Purpose:** Converts the closest 


### 5. parseInt()
- **Purpose**: Converts to the closest integer value that is a whole number
- **Behaviour**:
	- Converts any given float number to the nearest whole integer
	- Converts Binary to decimal if base is given. *( 2nd parameter )*
```js
console.log(parseInt("42"));       // 42
console.log(parseInt("42.7"));     // 42
console.log(parseInt("42px"));     // 42
console.log(parseInt("1010", 2));  // 10 (binary to decimal)
console.log(parseInt("Hello"));    // NaN

```

### 6. getElementByID()
- Syntax `document.getElementByID(id)`
- The function basically takes the id as a parameter and find that class in the html page and then select it.
- This is conventionally stored in a variable for further use of its subclass.
Refer [[JavaScript Basic Programming#getElementByID|getElementByID]]
## Assignment 4
- WAP to identify whether a visited user is eligible for e-voting. Criteria are as follows.
- Visited user should be more than 25 years
- If he is male print hello Mr.(name) else print Miss(Name)
- Else you are not entitled to visit this page
### Solution 
```html
<!DOCTYPE html>

<html lang="en">

<head>

<meta charset="UTF-8">

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>My Website</title>

</head>

<body>

<h1>Enter the details as the prompt says</h1>

<script src="script.js"></script>

</body>

</html>
```

```js
var gender = prompt("Enter your gender: ", "Gender").toLowerCase();

var age = prompt("Enter your age: ", "Age");

var name = prompt("Enter your name: ", "Name");

  

if (age < 25) {

document.write("Hello, " + name + "! You are not entitled to visit this page");

} else {

if (gender == "male") {

document.write("Hello, Mr. " + name + "! You are entitled to visit this page");

} else if (gender == "female") {

document.write("Hello, Mrs. " + name + "! You are entitled to visit this page");

} else {

document.write("Hello, You are not entitled to visit this page");

}

}
```

## Assignment 5
- Write a program to find the average of marks of n Subjects by using js
