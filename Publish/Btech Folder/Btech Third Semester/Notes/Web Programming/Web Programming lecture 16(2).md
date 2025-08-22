---
Title: Web Programming lecture 16
Status: 
marker:
  - "[[Web Programming]]"
  - "[[web development]]"
  - "[[Forms]]"
  - "[[JavaScript]]"
tags:
  - BTech
Date: 2024.09.09
Time: 11:13
---


### Code Breakdown:
```html
<form name="alertform">
    Enter Your Name:
    <input type="text" name="yourname">
    <input type="button" value="Go" onClick="window.alert('hellow'+document.alertform.yourname.value)">
</form>
```

### Explanation:

1. **Form**:
   - The form is named `"alertform"`, which means that it can be accessed via JavaScript using `document.alertform`.
   
2. **Input Fields**:
   - There are two input fields in this form:
     - The first is a `text` input with the `name="yourname"`. The user enters their name here.
     - The second is a `button` input with the `value="Go"`. When clicked, this button will trigger the `onClick` JavaScript event.

3. **JavaScript Functionality**:
   - The `onClick` attribute attached to the button triggers the JavaScript `window.alert()` function.
   - `window.alert()` is a method that displays an alert dialog with the message passed to it.
   - In this case, the message is concatenated using the string `'hellow'` and the value from the form's input field (which is accessed by `document.alertform.yourname.value`).
   - `document.alertform` refers to the form, and `.yourname.value` refers to the value entered into the text input field named `"yourname"`.

### What Happens When You Click the Button:
1. The user enters their name in the text input field.
2. When the button labeled "Go" is clicked, the `onClick` function is triggered.
3. The alert displays a message starting with `"hellow"`, followed by the name the user entered in the text field.
   - For example, if the user entered "Alice", the alert would show: `hellow Alice`.

### Example Flow:
- User enters: **"John"**.
- User clicks the "Go" button.
- An alert appears displaying: `"hellow John"`.

This example demonstrates basic form handling in HTML combined with JavaScript to dynamically show user input in a simple alert box. It's a good introductory example for handling user input and showing it back to the user via JavaScript.

### Improvements:
- The form could be improved by validating the input to ensure the user has entered a name before showing the alert.
- Correcting the spelling in the message would make it more user-friendly (`"hello"` instead of `"hellow"`).

### Example with Validation:
```html
<form name="alertform">
    Enter Your Name:
    <input type="text" name="yourname">
    <input type="button" value="Go" onClick="validateInput()">
</form>

<script>
    function validateInput() {
        var name = document.alertform.yourname.value;
        if (name) {
            window.alert('Hello ' + name);
        } else {
            window.alert('Please enter your name');
        }
    }
</script>
```

## Validation 
Here is the updated note, incorporating both examples:

### HTML Forms with JavaScript Interaction and Validation

#### 1. **Example 1: HTML Form with JavaScript Alert**

In this example, a basic HTML form allows the user to input their name, and when the "Go" button is clicked, a JavaScript `alert` message greets the user by name.

##### HTML Form:
```html
<form name="alertform">
    Enter your name:
    <input type="text" name="yourname">
    <input type="button" value="Go" 
           onClick="window.alert('Hello ' + document.alertform.yourname.value);">
</form>
```

##### Key Points:
- The form uses the `name` attribute `"alertform"` to be referenced in the JavaScript.
- A text input field named `"yourname"` is used to collect the user's input.
- The "Go" button triggers the `onClick` event, which calls `window.alert`. This alert displays the message `"Hello"` followed by the value entered in the text input.
- The `document.alertform.yourname.value` retrieves the text entered by the user in the input field.

This example demonstrates how to create a simple interactive form in HTML with a JavaScript pop-up message.

#### 2. **Example 2: HTML Form with Validation Using JavaScript**

In the second example, a form requires the user to input their name. JavaScript is used to validate the input before submission. If the field is left blank, the form will not be submitted, and an alert will appear.

##### HTML Form:
```html
<form name="myForm" onsubmit="return validateForm()">
  Name: <input type="text" name="fname">
  <input type="submit" value="Submit">
</form>
```

##### Key Points:
- The form uses the `name` attribute `"myForm"`. The `onsubmit` event triggers the `validateForm()` function to check the input before the form is submitted.
- A text input field named `"fname"` is used to collect the user's name.
- The submit button calls the validation function when clicked. The form will only be submitted if the function returns `true`.

##### JavaScript Validation Function:
```javascript
function validateForm() {
  var x = document.forms["myForm"]["fname"].value;
  if (x == "") {
    alert("Name must be filled out");
    return false;
  }
}
```

- **Function Explanation**:
  - The function retrieves the value of the `fname` input field using `document.forms["myForm"]["fname"].value`.
  - It checks if the input field is empty (`x == ""`).
  - If empty, an alert message "Name must be filled out" is shown, and the form submission is stopped by returning `false`.

##### Purpose:
- This function ensures that the form is not submitted with an empty "Name" field.
- It enhances the user experience by providing immediate feedback if they forget to fill in their name.

#### Conclusion:
These examples demonstrate two common uses of JavaScript with HTML forms:
1. Creating interactive forms that provide instant feedback using `alert` messages.
2. Implementing client-side validation to ensure required fields are filled out before form submission.

Both examples highlight the importance of using JavaScript to enhance the functionality and user experience of web forms.

Would you like to explore more advanced JavaScript form handling techniques or dive into other web development topics?

In this improved version, if the user doesn't enter a name, an alert will prompt them to enter it.

## Assignment
- write a program to accept user name, user age, user phone number.
- Check no uesr input is left or blank
- User Name length should be 10 char long
- user age should be more than 20 and less than 90
- User Phone length should be 10 digit long
- 