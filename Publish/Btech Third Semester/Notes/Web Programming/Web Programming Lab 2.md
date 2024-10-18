---
Title: Web Programming Lab 2
Status: 
marker:
  - "[[btech]]"
  - "[[Web Programming]]"
tags:
  - BTech
Date: 2024.07.24
Time: "{time:HH:mm}}"
---
# Web Programming Lab 2

## Index
- [Main Note](#main-note)
  - [Basic HTML Tutorial](#basic-html-tutorial)
  - [HTML Tables Tutorial](#html-tables-tutorial)
    - [Table Rows (`<tr>`)](#table-rows-tr)
    - [Table Data Cells (`<td>`)](#table-data-cells-td)
    - [Rowspan Attribute](#rowspan-attribute)
    - [Colspan Attribute](#colspan-attribute)
  - [HTML Lists Tutorial](#html-lists-tutorial)
    - [Unordered Lists (`<ul>`)](#unordered-lists-ul)
    - [Ordered Lists (`<ol>`)](#ordered-lists-ol)
    - [Nesting Lists](#nesting-lists)
    - [Customizing List Style](#customizing-list-style)
- [References](#references)

## Main Note

### Basic HTML Tutorial
HTML (HyperText Markup Language) is the standard language for creating web pages. It uses a series of elements and tags to structure content on the web.

#### Basic HTML Structure
Here is a simple HTML document:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My First HTML Page</title>
</head>
<body>
    <h1>Welcome to My Website</h1>
    <p>This is a paragraph of text.</p>
</body>
</html>
```

- `<!DOCTYPE html>`: Declares the document type and version of HTML.
- `<html>`: Root element of an HTML page.
- `<head>`: Contains meta-information about the document.
- `<title>`: Sets the title of the web page.
- `<body>`: Contains the content of the HTML document.
- `<h1>`: Represents a top-level heading.
- `<p>`: Represents a paragraph.

### HTML Tables Tutorial
HTML tables are used to display tabular data. A table is defined using the `<table>` tag, with rows created using `<tr>` (table row) and cells created using `<td>` (table data).

#### Table Rows (`<tr>`)
The `<tr>` tag defines a row in a table.

```html
<table>
    <tr>
        <td>Row 1, Cell 1</td>
        <td>Row 1, Cell 2</td>
    </tr>
    <tr>
        <td>Row 2, Cell 1</td>
        <td>Row 2, Cell 2</td>
    </tr>
</table>
```

#### Table Data Cells (`<td>`)
The `<td>` tag defines a cell in a table.

```html
<table>
    <tr>
        <td>Cell 1</td>
        <td>Cell 2</td>
    </tr>
</table>
```

#### Rowspan Attribute
The `rowspan` attribute allows a cell to span multiple rows.

```html
<table>
    <tr>
        <td rowspan="2">Cell spanning 2 rows</td>
        <td>Cell 2</td>
    </tr>
    <tr>
        <td>Cell 3</td>
    </tr>
</table>
```

#### Colspan Attribute
The `colspan` attribute allows a cell to span multiple columns.

```html
<table>
    <tr>
        <td colspan="2">Cell spanning 2 columns</td>
    </tr>
    <tr>
        <td>Cell 2</td>
        <td>Cell 3</td>
    </tr>
</table>
```

### Table Example in Markdown
Here's how the above table would look in Markdown format:

```markdown
| Cell spanning 2 columns |               |
|-------------------------|---------------|
| Cell 2                  | Cell 3        |
```

### Lists 

HTML provides two types of lists for organizing content: unordered lists and ordered lists.

#### Unordered Lists (`<ul>`)
Unordered lists are used to group a collection of items in no particular order. Each item in the list is represented using the `<li>` (list item) tag, and the entire list is wrapped in the `<ul>` (unordered list) tag.

Example:

```html
<ul>
    <li>Item 1</li>
    <li>Item 2</li>
    <li>Item 3</li>
</ul>
```

This will render as:
- Item 1
- Item 2
- Item 3

#### Ordered Lists (`<ol>`)
Ordered lists are used to group a collection of items in a specific order. Each item in the list is represented using the `<li>` (list item) tag, and the entire list is wrapped in the `<ol>` (ordered list) tag.

Example:

```html
<ol>
    <li>First item</li>
    <li>Second item</li>
    <li>Third item</li>
</ol>
```

This will render as:
1. First item
2. Second item
3. Third item

#### Nesting Lists
You can nest lists to create sublists within a list item. This can be done with both unordered and ordered lists.

Example of a nested list:

```html
<ul>
    <li>Item 1
        <ul>
            <li>Subitem 1.1</li>
            <li>Subitem 1.2</li>
        </ul>
    </li>
    <li>Item 2</li>
    <li>Item 3</li>
</ul>
```

This will render as:
- Item 1
  - Subitem 1.1
  - Subitem 1.2
- Item 2
- Item 3

#### Customizing List Style
The style of list items can be customized using CSS. You can change the list marker type, position, and even use custom images as list markers.

Example:

```html
<ul style="list-style-type: square;">
    <li>Square item 1</li>
    <li>Square item 2</li>
    <li>Square item 3</li>
</ul>
```

This will render as:
■ Square item 1  
■ Square item 2  
■ Square item 3

In CSS, the `list-style-type` property allows you to change the marker type (e.g., `disc`, `circle`, `square`, `decimal`, etc.). The `list-style-image` property allows you to use an image as a marker.

Example of using a custom image:

```html
<ul style="list-style-image: url('path/to/image.png');">
    <li>Custom image item 1</li>
    <li>Custom image item 2</li>
    <li>Custom image item 3</li>
</ul>
```

### Summary
- `<ul>`: Creates an unordered list.
- `<ol>`: Creates an ordered list.
- `<li>`: Defines a list item within `<ul>` or `<ol>`.
- `list-style-type`: CSS property to change list marker style.
- `list-style-image`: CSS property to use an image as a list marker.

By understanding these tags and their attributes, you can create well-organized and visually appealing lists in your HTML documents.

---

# Assignments 

## Question 1 :  Registration page (Without using form)

#### Code
```html
<!DOCTYPE html>

<html lang="en">

    <head>

        <meta charset="UTF-8">

        <meta name="viewport" content="width=device-width, initial-scale=1.0">

        <title></title>

    </head>

    <body>

        <h1>Registration Page</h1>

        <p>User Name:- ____________________</p>

        <p>First Name:- ____________________</p>

        <p>Last Name:- ____________________</p>

        <p>Your Mobile:- ___________________</p>

        <p>Your Email:- ____________________</p>

        <p>Password:- _____________________</p>

        <p>Password:- _____________________</p>

    </body>

</html>
```

#### Output
![[Pasted image 20240724104517.png]]

## Question 2 : Contact-us page 

#### Code 
```html
<!DOCTYPE html>

<html lang="en">

    <head>

        <meta charset="UTF-8">

        <meta name="viewport" content="width=device-width, initial-scale=1.0">

        <title>Contact Page</title>

    </head>

    <body>

        <h1>Contact Us</h1>

        <h4>Phone Number:- 987654321</h4>

        <h4>Email:- helo@bigfirm.org</h4>

        <h4>Address:- 123, Big Firm Lane, Big City, 123456</h4>

    </body>

</html>
```
#### Output
![[Pasted image 20240724105328.png]]

## Question 3 : Web Page of CV

#### Code
```html
<!DOCTYPE html>

<html lang="en">

    <head>

        <meta charset="UTF-8">

        <meta name="viewport" content="width=device-width, initial-scale=1.0">

        <title>Curriculum Vitae</title>

    </head>

    <body>

        <img src="./nmims.png" style="display: block; margin: 0 auto;">

        <p><strong>B. TECH. COMPUTER ENGINEERING<br>Name:- Kratos</strong></p>

        <p><strong><u>Objective</u><br>I am a passionate programmer</strong></p>

        <p><strong><u>Education</u><br></strong></p>

            <table border="1">

                <tr>

                    <th>Degree</th>

                    <th>Institute</th>

                    <th>CGPA/Percentage</th>

                    <th>Board/University</th>

                    <th>Year</th>

                </tr>

                <tr>

                    <td>B. Tech</td>

                    <td>NMIMS</td>

                    <td>NM</td>

                    <td>4/4</td>

                    <td>2023</td>

                </tr>

                <tr>

                    <td>12th</td>

                    <td>DPS</td>

                    <td>CBSE</td>

                    <td>82.02%</td>

                    <td>2019</td>

                </tr>

                <tr>

                    <td>10th</td>

                    <td>St Joseph</td>

                    <td>SSC</td>

                    <td>92%</td>

                    <td>2017</td>

                </tr>

            </table>

        <p><strong><u>Technical Skills</u></strong></p>

        <table border="1">

            <tr>

                <th>Domain</th>

                <th>Details</th>

            </tr>

            <tr>

                <td>Languages</td>

                <td>Js, NodeJS, Python, C++, C, Swift, Type Script, Java,C#</td>

            </tr>

  

            <tr>

                <td>Web Designing</td>

                <td>Js, HTML, CSS, React.JS, Bootstrap</td>

            </tr>

            <tr>

                <td>Software</td>

                <td>AutoDesk AutoCad, Blender, Figma, AE, PS, etc.</td>

            </tr>

            <tr>

                <td>DataBase</td>

                <td>MongoDB, MySQL, PHP, PostgreSQL</td>

            </tr>

            <tr>

                <td>Analytics</td>

                <td>Python, R, SQL, MATLAB</td>

            </tr>

            <tr>

                <td>Operating Systems</td>

                <td>Windows, Debian, Fedora, Arch, Parrot, Etc</td>

            </tr>

        </table>

        <p><strong><u>Key Projects</u></strong></p>

        <table border="1">

            <tr>

                <th>Project Title</th>

                <th>Duration</th>

                <th>Platform Used</th>

                <th>Brief Description</th>

            </tr>

            <tr>

                <td>Webpage for an import export firm</td>

                <td>4 Months</td>

                <td>HTML,CSS,BootStrap,Js,NodeJS,Figma</td>

                <td>Mostly Static Pages, A Contact me <br>page with active selections</td>

            </tr>

            <tr>

                <td>Exercise AI</td>

                <td>10 Months</td>

                <td>HTML,CSS,Bootstrap,Js,NodeJS,Figma,<br>Python,Java,TensorFlow,PyTorch</td>

                <td>A website that counted reps properly and assessed calories burned</td>

            </tr>

        </table>

    <p><strong><u>Technical Presentation/Workshops/Certificates</u></strong><br><ul><li>hackathon</li><li>hackathon UI</li><li>GDSC Relay Programming</li></ul></p>

    <p><strong><u>TECHNICAL –WORK EXPERIENCE / INTERNSHIPS:</u></strong><br><ul><li>Cisco</li><li>Dell</li><li>SenseBoard</li></ul></p>

    </body>

</html>
```
#### Output
![[Pasted image 20240724113540.png]]
![[Pasted image 20240724113521.png]]

## Submission PDF
![[Lab2.pdf]]

## References
- [W3Schools HTML Tutorial](https://www.w3schools.com/html/)
- [MDN Web Docs on HTML](https://developer.mozilla.org/en-US/docs/Web/HTML)

###### Information
- Date: 2024.07.24
- Time: 10:23