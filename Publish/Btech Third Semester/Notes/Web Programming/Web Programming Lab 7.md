---
Title: Web Programming Lab 7
Status: 
marker:
  - "[[Web Programming]]"
  - "[[web development]]"
  - "[[JavaScript]]"
  - "[[CSS]]"
  - "[[HTML]]"
  - "[[Lab]]"
tags:
  - BTech
Date: 2024.09.28
Time: 11:15
---

---
## Details
Tejas Sahoo  
K044  
BTech Cybersecurity  

Lab 7  

---

**Q.1**: Write a program to search for the `@` position in the given mail ID on submit button event.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Email Position Finder</title>
</head>
<body>
    <div class="container">
        <h2>Find @ Position in Email</h2>
        <input type="text" id="email" placeholder="Enter your email">
        <button onclick="findAtPosition()">Submit</button>
    </div>

    <script>
        function findAtPosition() {
            const email = document.getElementById('email').value;
            const atPosition = email.indexOf('@');
            if (atPosition !== -1) {
                alert(`The '@' is at position: ${atPosition}`);
            } else {
                alert("The '@' symbol is not present in the email.");
            }
        }
    </script>
</body>
</html>
```
![[Pasted image 20240918114613.png]]

---

**Q.2**: Write a program to compare password and confirm password on mouse down event.

```html
	<!DOCTYPE html>
	<html>
	<head>
	    <title>Password Comparison</title>
	</head>
	<body>
	    <div class="container">
	        <h2>Compare Passwords</h2>
	        <input type="password" id="password" placeholder="Enter your password">
	        <input type="password" id="confirmPassword" placeholder="Confirm your password">
	        <button onmousedown="comparePasswords()">Submit</button>
	    </div>
	
	    <script>
	        function comparePasswords() {
	            const password = document.getElementById('password').value;
	            const confirmPassword = document.getElementById('confirmPassword').value;
	            if (password === confirmPassword) {
	                alert("Passwords match!");
	            } else {
	                alert("Passwords do not match.");
	            }
	        }
	    </script>
	</body>
	</html>
```
![[Pasted image 20240918114721.png]]


---

**Q.3**: Write a program to slice input text to show the first 3 characters.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Slice Input</title>
</head>
<body>
    <div class="container">
        <h2>Slice Input</h2>
        <form id="sliceForm">
            <input type="text" id="inputText" placeholder="Enter some text">
            <button type="submit">Submit</button>
        </form>
    </div>

    <script>
        document.getElementById('sliceForm').addEventListener('submit', function(event) {
            event.preventDefault();
            const inputText = document.getElementById('inputText').value;
            const slicedText = inputText.slice(0, 3);
            alert(`The first 3 characters are: ${slicedText}`);
        });
    </script>
</body>
</html>
```
![[Pasted image 20240918114809.png]]



---

**Q.4**: Write a program to extract and display the first name.

```html
<!DOCTYPE html>
<html>
<head>
    <title>First Name Extractor</title>
</head>
<body>
    <div class="container">
        <h2>First Name Extractor</h2>
        <input type="text" id="firstName" placeholder="Enter your first name">
        <input type="text" id="lastName" placeholder="Enter your last name">
        <button onclick="showFirstName()">Submit</button>
    </div>

    <script>
        document.getElementById('firstName').addEventListener('change', function() {
            const firstName = document.getElementById('firstName').value;
            alert(`First Name: ${firstName}`);
        });

        function showFirstName() {
            const firstName = document.getElementById('firstName').value;
            alert(`First Name: ${firstName}`);
        }
    </script>
</body>
</html>
```
![[Pasted image 20240918114847.png]]

---

**Q.5**: Write a program to replace the old password with the new password on button click and display output using alert.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Password Replacer</title>
</head>
<body>
    <div class="container">
        <h2>Password Replacer</h2>
        <input type="password" id="oldPassword" placeholder="Enter your old password">
        <input type="password" id="newPassword" placeholder="Enter your new password">
        <button onclick="replacePassword()">Submit</button>
    </div>

    <script>
        function replacePassword() {
            const oldPassword = document.getElementById('oldPassword').value;
            const newPassword = document.getElementById('newPassword').value;
            if (oldPassword && newPassword) {
                alert(`Old Password: ${oldPassword}\nNew Password: ${newPassword}`);
            } else {
                alert("Please enter both old and new passwords.");
            }
        }
    </script>
</body>
</html>
```
![[Pasted image 20240918114937.png]]

---

**Q.6**: Write a program to concatenate the user's first name and last name, convert it into uppercase on keydown & keyup event, and display it in a textbox.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Concatenate and Uppercase</title>
</head>
<body>
    <div class="container">
        <h2>Concatenate and Uppercase</h2>
        <input type="text" id="firstName" placeholder="Enter your first name" onkeydown="updateFullName()" onkeyup="updateFullName()">
        <input type="text" id="lastName" placeholder="Enter your last name" onkeydown="updateFullName()" onkeyup="updateFullName()">
        <input type="text" id="fullName" placeholder="Full name will appear here" readonly>
    </div>

    <script>
        function updateFullName() {
            const firstName = document.getElementById('firstName').value;
            const lastName = document.getElementById('lastName').value;
            const fullName = (firstName + " " + lastName).toUpperCase();
            document.getElementById('fullName').value = fullName;
        }
    </script>
</body>
</html>
```
![[Pasted image 20240918115030.png]]

---

**Q.7**: Write a program to validate an HTML form using JavaScript with the following requirements:
1. User Name should be 10 characters long.
2. Age should be between 21 and 89.
3. Phone Number should be 10 digits long.
4. Email should be valid.
5. No field should be left blank.

```html
<!DOCTYPE html>
<html>
<head>
    <title>Form Validation</title>
</head>
<body>
    <div class="container">
        <h2>Form Validation</h2>
        <form id="userForm">
            <input type="text" id="userName" placeholder="Enter your name">
            <input type="number" id="userAge" placeholder="Enter your age">
            <input type="text" id="userPhone" placeholder="Enter your phone number">
            <input type="email" id="userEmail" placeholder="Enter your email">
            <button type="submit">Submit</button>
            <div id="errorMessage"></div>
        </form>
    </div>
    <script>
        document.getElementById('userForm').addEventListener('submit', function(event) {
            event.preventDefault();
            const userName = document.getElementById('userName').value;
            const userAge = document.getElementById('userAge').value;
            const userPhone = document.getElementById('userPhone').value;
            const userEmail = document.getElementById('userEmail').value;
            const errorMessage = document.getElementById('errorMessage');

            let errors = [];

            if (!userName || !userAge || !userPhone || !userEmail) {
                errors.push("All fields are required.");
            }

            if (userName.length !== 10) {
                errors.push("User name must be 10 characters long.");
            }

            if (userAge <= 20 || userAge >= 90) {
                errors.push("User age must be between 21 and 89.");
            }

            if (userPhone.length !== 10) {
                errors.push("Phone number must be 10 digits long.");
            }

            const emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
            if (!emailPattern.test(userEmail)) {
                errors.push("Invalid email format.");
            }

            if (errors.length > 0) {
                errorMessage.innerHTML = errors.join('<br>');
            } else {
                errorMessage.innerHTML = "Form submitted successfully!";
            }
        });
    </script>
</body>
</html>
```
![[Pasted image 20240918115116.png]]

---

