---
Title: Web Programming Lecture 17
Status: 
marker:
  - "[[Web Programming]]"
  - "[[web development]]"
  - "[[JavaScript]]"
  - "[[HTML]]"
  - "[[DOM]]"
tags: 
Date: 2024.09.16
Time: 11:13
---
# Web Programming Lecture 17

## CSS PSeudo Selectors
## Constraint Validation DOM Properties
DOM Html Validation

```html
<input id="id1" type="number" min="100" max="300" required>
<button onclick="myFunction()">OK</button>
<p id="demo">
<script>
function myFunction(){
	var inpObj = document.getElementById("id1);
	if (!inpObj.checkValidity()){
		document.getElementById("demo").innerHTML=innerObj.validationMessage;
		
	}
	else{
		document.getElementById("demo").innerHTML="input OK";
	}
}
</script>
```

# Assignments
### Write a program to search for the @ position in the given mail id on submit event.
```html
<html>
<body></body>
<script>

</script>
</html>
```

# References


###### Information
- date: 2024.09.16
- time: 11:13