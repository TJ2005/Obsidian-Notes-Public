---
Title: JavaScript Basic Programming
Status: 
marker: 
tags: 
Date: 2024.08.15
Time: 16:09
---
Here is an updated version with additional relevant information:

# JavaScript Main Use
JavaScript is primarily used in a browser environment to interact with HTML elements and manipulate CSS styles dynamically. It helps create responsive and interactive web pages by controlling the Document Object Model (DOM). Therefore, our focus will be on how to use JavaScript to select and manipulate HTML elements effectively.

# Item Selector
Before manipulating any HTML element, you first need to select it. JavaScript provides various methods to target elements within the DOM using attributes like IDs, classes, and tags.

## getElementByID
The `getElementById` method is used to select an element with a specific ID. This is one of the most commonly used methods because it selects a single, unique element based on its `id` attribute.

### Syntax
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JavaScript Example</title>
    <!-- Link to the external JavaScript file -->
    <script src="script.js" defer></script>
</head>
<body>
    <h1>JavaScript Update Example</h1>
    <p id="demo">This text will be changed by JavaScript.</p>
    <button onclick="updateText()">Click me to change text</button>
</body>
</html>
```

### JavaScript:
```js
function updateText() {
    document.getElementById('demo').innerHTML = 'Hello JavaScript';
}
```
**[Try it Yourself »](https://www.w3schools.com/js/tryit.asp?filename=tryjs_intro_inner_html_quotes)**

### Process Explanation:
1. **Step 1**: JavaScript searches for an element with the `id` "demo".
2. **Step 2**: Once found, the `innerHTML` property of the element is accessed.
3. **Step 3**: The content of the `innerHTML` is then updated to "Hello JavaScript".
4. **Step 4**: The new text is reflected immediately in the browser.

## Additional Element Selectors
While `getElementById` is very useful, other methods can be used to select elements in various ways:

### 1. `getElementsByClassName`
Selects all elements with the specified class name and returns an array-like object (HTMLCollection).
```js
var elements = document.getElementsByClassName('myClass');
elements[0].style.color = 'blue'; // Modifies the first element with class 'myClass'
```

### 2. `getElementsByTagName`
Selects all elements with a specific tag name.
```js
var paragraphs = document.getElementsByTagName('p');
paragraphs[0].style.fontSize = '18px'; // Changes font size of the first paragraph
```

### 3. `querySelector` & `querySelectorAll`
These are more flexible as they allow for more complex CSS-like selectors.
- `querySelector`: Selects the first element that matches the selector.
- `querySelectorAll`: Selects all elements that match the selector.
```js
var firstParagraph = document.querySelector('p'); // Selects the first <p> element
var allParagraphs = document.querySelectorAll('p'); // Selects all <p> elements
```

### Examples:
```html
<p class="myClass">Paragraph 1</p>
<p class="myClass">Paragraph 2</p>
```

```js
// Select elements by class name
var elements = document.getElementsByClassName('myClass');
elements[0].style.color = 'red'; // Changes the color of the first paragraph with class 'myClass'
```

# Event Handling
JavaScript can also listen for and respond to user actions such as clicks, form submissions, and key presses.

### Adding an Event Listener
```js
document.getElementById('demo').addEventListener('click', function() {
    alert('Element clicked!');
});
```

# References

- **JavaScript Documentation**: [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
- **JavaScript Tutorials**: [W3Schools JavaScript](https://www.w3schools.com/js/)
- **DOM Manipulation**: [JavaScript DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)

###### Information
- **Date**: 2024.08.15
- **Time**: 16:09
- **Updated By**: [Your Name or Contributor] 
- **Relevance**: JavaScript DOM manipulation is essential for building interactive and dynamic websites. Mastering selectors and event handling forms the foundation for more advanced client-side development.
