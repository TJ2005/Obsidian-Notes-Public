---
Title: Web Programming Lecture 12
Status: 
marker:
  - "[[Web Programming]]"
  - "[[web development]]"
  - "[[JavaScript]]"
  - "[[HTML]]"
tags:
  - BTech
Date: 2024.08.26
Time: 11:09
---
[[Web Programming]] [[Web]]
---
# Web Programming Lecture 12

## Continuation from Java
We began discussing Java in Lecture [Web Programming Lecture 11]. This lecture continues with JavaScript.

## JavaScript Overview
JavaScript is a high-level, dynamic programming language primarily used for web development. It is known for being:
- **Untyped**: JavaScript does not require explicit type declarations for variables. Instead, it is flexible with variable types, which can hold values of any type.

## JavaScript within HTML

### Internal JavaScript
Internal JavaScript is similar to internal CSS in that it is embedded directly within an HTML file using the `<script>` tag:
```html
<script type="text/javascript">
    var money;
</script>
```

### Selecting Elements
JavaScript can interact with HTML elements using methods such as `document.write()` to dynamically insert content into a web page:
```html
<html>
<head>
    <title>My Page</title>
</head>
<body>
    <script type="text/javascript">
        document.write('<h1>This is my first JavaScript page</h1>');
    </script>
</body>
</html>
```
In this example, `document.write()` is used to add an `<h1>` heading to the web page.

## Pure JavaScript

### Data Types
In JavaScript, variables are declared without specifying their type. For example:
```js
var variable_name = "value";
```
Here, `variable_name` can hold any type of value, including strings, numbers, objects, etc.

### Concatenation
To demonstrate string concatenation and dynamic HTML content insertion:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript Page</title>
    <script type="text/javascript">
        // JavaScript to write "Hello World" into a <p> element
        function writeHelloWorld() {
            document.write('<p>Hello World</p>');
        }
        
        // JavaScript to write "How are you?" and concatenate with a <br> and another <p> element
        function writeHowAreYou() {
            document.write('<p>How are you?<br></p>' + '<p>This is concatenated text.</p>');
        }
    </script>
</head>
<body onload="writeHelloWorld(); writeHowAreYou();">
    <!-- Content will be inserted here by JavaScript -->
</body>
</html>
```
In this example, `writeHelloWorld()` adds a paragraph with "Hello World," and `writeHowAreYou()` adds a paragraph with "How are you?" followed by a line break and additional text.

## Alerts and Prompts

### Displaying Output Using Alerts
Alerts are used to display messages in a pop-up dialog box. Here’s an example:
```html
<html>
<head><title>Alert Example</title></head>
<body>
<p>
<a href="myfile.html">My Page</a>
<br>
<a href="myfile.html" onMouseover="window.alert('Hello');">
my page
</a>
</p>
</body>
</html>
```
In this example, an alert box will appear with the message "Hello" when the mouse is hovered over the link.

### Prompt Function
The `prompt()` function is used to display a dialog box that prompts the user for input. Here’s the syntax:
```javascript
var retVal = prompt("Label", "PlaceHolder Text");
```
- **Label**: Text that appears next to the text box.
- **PlaceHolder Text**: Text that appears inside the text box before the user types anything.

Example usage:
```html
<head>
<script type="text/javascript">
    var retVal = prompt("Enter your name:", "Your name here");
    alert("You have entered: " + retVal);
</script>
</head>
```
In this example, a prompt asks the user to enter their name. After entering the name, an alert displays the entered value.

## Variables in JavaScript

### Local Variables
Local variables are declared within a function or block and are only accessible within that function or block. They are created using `var`, `let`, or `const`.

**Example:**
```html
<script type="text/javascript">
    function localExample() {
        var localVar = "I am local";
        alert(localVar); // Alerts: I am local
    }
    localExample();
    alert(localVar); // Error: localVar is not defined
</script>
```
In this example, `localVar` is only accessible within the `localExample` function.

### Global Variables
Global variables are declared outside any function and are accessible from any function or block within the same scope. They are created using `var`, `let`, or `const` outside of any function.

**Example:**
```html
<script type="text/javascript">
    var globalVar = "I am global";
    
    function globalExample() {
        alert(globalVar); // Alerts: I am global
    }
    
    globalExample();
    alert(globalVar); // Alerts: I am global
</script>
```
In this example, `globalVar` is accessible both inside and outside the `globalExample` function.

## Assignment 2
- Display Name
- College Name
- College Site

## References
- **Date**: August 26, 2024
- **Time**: 11:09

---
