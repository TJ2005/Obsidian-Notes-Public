---
Title: Web Programming Lecture 5
Status: 
marker: 
tags: 
Date: 2024.07.29
Time: 11:40
---
# Web Programming Lecture 5

# Main note



# References


###### Information
- date: 2024.07.29
- time: 11:40](<---
Title: Web Programming Lecture 5
Status: 
marker: 
tags: 
Date: 2024.07.29
Time: 11:40
---
# Web Programming Lecture 5

## Main Note

### CSS Basics

#### What is CSS?
- **CSS (Cascading Style Sheets)**: A style sheet language used to describe the presentation of a document written in HTML or XML.
  - **Syntax**: Consists of selectors and declarations.
    - **Selector**: Points to the HTML element you want to style.
    - **Declaration**: Block contains one or more declarations separated by semicolons.
      - **Property**: Specifies the aspect of the element to be styled (e.g., color, font-size).
      - **Value**: Specifies the value of the property (e.g., red, 16px).

#### Why CSS?
- **Separation of Content and Presentation**: Keeps HTML content separate from design and layout, making it easier to manage and maintain.
- **Consistency**: Ensures a consistent look across multiple web pages.
- **Efficiency**: Allows for faster page loading and easier design changes.
- **Accessibility**: Improves accessibility for different devices and screen sizes through responsive design.

#### How to Use CSS in HTML?
- **Inline CSS**: Directly within an HTML element using the `style` attribute.
  ```html
  %3Cp style="color: blue; font-size: 14px;"%3EThis is a paragraph.</p>
  ```
- **Internal CSS**: Within the `<style>` tag in the `<head>` section of an HTML document.
  ```html
  <head>
    <style>
      p {
        color: blue;
        font-size: 14px;
      }
    </style>
  </head>
  ```
- **External CSS**: In an external file linked to the HTML document using the `<link>` tag.
  ```html
  <head>
    <link rel="stylesheet" href="styles.css">
  </head>
  ```

### Detailed ID Selector Note
- **ID Selector**: Used to style a single, unique element. The ID selector is defined with a `#` followed by the ID name.
  - **Syntax**:
    ```css
    #unique-element {
      property: value;
    }
    ```
  - **Example**:
    ```html
    <div id="header">
      <h1>Welcome to My Website</h1>
    </div>
    ```
    ```css
    #header {
      background-color: lightblue;
      text-align: center;
    }
    ```

### Detailed Class Selector Note
- **Class Selector**: Used to style multiple elements with the same class. The class selector is defined with a `.` followed by the class name.
  - **Syntax**:
    ```css
    .classname {
      property: value;
    }
    ```
  - **Example**:
    ```html
    <p class="intro">This is the introduction paragraph.</p>
    <p class="intro">This is another introduction paragraph.</p>
    ```
    ```css
    .intro {
      color: green;
      font-weight: bold;
    }
    ```

## References

---

### Additional Information
- **Date**: 2024.07.29
- **Time**: 11:40>)