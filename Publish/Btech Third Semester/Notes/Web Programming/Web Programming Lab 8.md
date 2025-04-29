---
Title: Web Programming Lab 5
Status: 
marker:
  - "[[Web Programming]]"
  - "[[web development]]"
  - "[[HTML]]"
  - "[[CSS]]"
  - "[[Lab]]"
tags:
  - BTech
Date: 2024.08.28
Time: 10:37
---
# Web Programming Lab 5
###### Details
Roll Number : K057
Name : Tejas Kamal Sahoo
Branch : Btech Cyber Security
Year : 2nd
Semester : 2
Date & Time : 28-08-2024 11:21
## Question 1
Design a navigation bar in a web page using HTML and CSS using external CSS.
![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfVld1VuXrrPwpvltkRXnmzEynDu_kQ2wk1uxnH2k03dtMeCG643XmELBhriqkI8DP8LDv3f4JOMEcm_-WNNhzwJdL2-ZxFG9XdQ-7XBQDFlKPD8a6QRWUhtA9qfiAJuUTfKkVRZ3Yg2Qd728RVjM6ua34SIiqcPreYMd3Blw?key=aJyHTeT6e5MQd2BDVQ3Ouw)
Also create Home, Students, faculty and contact us pages separately.

Note: overflow: hidden property that prevents the list elements from going outside of the list, 
display: block property displays the links as the block elements and makes the entire link area clickable.
float: left property, which uses float for getting the block elements to slide them next to each other.

## Output
![[Pasted image 20240828110449.png]]

## Answer 1
```html
<!DOCTYPE html>

<html>

<head>

<title>My Website</title>

<link rel="stylesheet" href="style.css">

</head>

<body>

<nav>

<ul>

<li><a href="index.html">Home</a></li>

<li><a href="students.html">Students</a></li>

<li><a href="faculty.html">Faculty</a></li>

<li><a href="contact.html">Contact Us</a></li>

</ul>

</nav>

  

</body>

</html>
```

```css
nav ul {

list-style-type: none;

margin: 0;

padding: 0;

overflow: hidden;

background-color: #333;

}

  

nav ul li {

float: left;

}

  

nav ul li a {

display: block;

color: white;

text-align: center;

padding: 14px 16px;

text-decoration: none;

}

  

nav ul li a:hover {

background-color: #111;

}
```

## Question 2
Design a web page using box model using external CSS
Note: Only use inline style for the text “Thought of the day”.

## Output 2
![[Pasted image 20240828110420.png]]
## Answer 2
```html
<!DOCTYPE html>

<html>

<head>

<title>Thought of the Day</title>

<link rel="stylesheet" href="style1.css">

</head>

<body>

<h2 style="text-align: center;">Thought of the Day</h2>

<div class="big-container">

<div class="thought-container">

<h2>Good Morning</h2>

<p>Passion is about figuring out what you are great at and what you love to do!</p>

</div>

</div>

</body>

</html>
```

```css
.thought-container {

border: 2px solid #ffdddd;

padding: 50px;

background-color: #ffdddd;

}

.big-container{

border: #ff8b8b 40px solid;

padding: 70px;

margin: 20px auto;

width: 300px;

text-align: center;

background-color: aliceblue;

}
```

## Question 3
Design a web page to style a table using external CSS.

### Code 3
```html
<!DOCTYPE html>

<html lang="en">

<head>

<meta charset="UTF-8">

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<link rel="stylesheet" href="index2.css">

<title>Company Table</title>

</head>

<body>

  

<table>

<tr>

<th>Company</th>

<th>Contact</th>

<th>Country</th>

</tr>

<tr>

<td>OpenAI</td>

<td>Sam Altman</td>

<td>USA</td>

</tr>

<tr>

<td>Google</td>

<td>Sundar Pichai</td>

<td>USA</td>

</tr>

<tr>

<td>Microsoft</td>

<td>Satya Nadella</td>

<td>USA</td>

</tr>

<tr>

<td>Twitter</td>

<td>Elon Musk</td>

<td>USA</td>

</tr>

<tr>

<td>SpaceX</td>

<td>Elon Musk</td>

<td>USA</td>

</tr>

<tr>

<td>ITC</td>

<td>Sanjiv Puri</td>

<td>India</td>

</tr>

<tr>

<td>Cipla</td>

<td>Umang Vohra</td>

<td>India</td>

</tr>

</table>

  

</body>

</html>

```

```css
table {

width: 60%;

border-collapse: collapse;

margin: 50px auto;

}

  

th, td {

padding: 12px;

text-align: left;

border-bottom: 1px solid #ddd;

}

  

th {

background-color: #4CAF50;

color: white;

}

  

tr:nth-child(even) {

background-color: #f2f2f2;

}

  

tr:nth-child(odd) {

background-color: #e6e6e6;

}

  

tr:hover {

background-color: #efc0c0;

}
```
### Output 3
![[Pasted image 20240828112053.png]]
###### Information
- date: 2024.08.28
- time: 10:37


