---
Title: Web Programming Lecture 7
Status: 
marker: 
tags: 
Date: 2024.07.31
Time: 13:19
---
# Web Programming Lecture 7

# Main note
## What is CSS?

**CSS** stands for **Cascading Style Sheets**. It is a stylesheet language used to describe the presentation of a document written in HTML or XML. CSS defines how elements on a web page should be displayed, including layout, colors, fonts, and animations.

### Key Features of CSS

1. **Separation of Content and Presentation**:
   - HTML is used to define the structure and content of a web page.
   - CSS is used to define the visual style and layout of the web page.
   - This separation allows for easier maintenance and greater flexibility.

2. **Selectors and Properties**:
   - **Selectors** are patterns used to select the elements you want to style.
   - **Properties** are the aspects of the elements you want to change (e.g., color, font-size).

### Basic Syntax

A CSS rule consists of a selector and a declaration block:

```css
selector {
  property: value;
}
```

For example:
```css
h1 {
  color: blue;
  font-size: 24px;
}
```
This rule selects all `<h1>` elements and applies a blue color and a font size of 24 pixels to them.

### Types of CSS

1. **Inline CSS**:
   - CSS is applied directly within an HTML element using the `style` attribute.
   - Example:
     ```html
     <h1 style="color: blue; font-size: 24px;">Hello World</h1>
     ```

2. **Internal CSS**:
   - CSS is defined within the `<style>` tag in the `<head>` section of an HTML document.
   - Example:
     ```html
     <head>
       <style>
         h1 {
           color: blue;
           font-size: 24px;
         }
       </style>
     </head>
     ```

3. **External CSS**:
   - CSS is written in a separate file with a `.css` extension and linked to the HTML document using the `<link>` tag. check [[link tag html]].
   - Example:
     ```html
     <head>
       <link rel="stylesheet" href="styles.css">
     </head>
     ```

### CSS Box Model

The CSS box model describes the rectangular boxes generated for elements in the document tree and consists of:
1. **Content**: The actual content of the box, where text and images appear.
2. **Padding**: Clears an area around the content. The padding is transparent.
3. **Border**: A border that goes around the padding and content.
4. **Margin**: Clears an area outside the border. The margin is transparent.

## Background
### Background-Position

The `background-position` property in CSS sets the starting position of a background image within an element. This property allows you to control where the background image appears in relation to the element's dimensions.

### Background-Repeat

The `background-repeat` property defines how background images are repeated. By default, background images are repeated both horizontally and vertically. This property allows you to change this behavior to achieve the desired visual effect.

### Example Usage

The following example demonstrates how to use `background-position` and `background-repeat` properties to control the positioning and repetition of a background image.

```css
body {
  background-image: url('img_tree.png');
  background-repeat: no-repeat;
  background-position: center center;
  background-size: cover;
}
```

In this example:

- `background-image: url('img_tree.png');` sets the background image to `img_tree.png`.
- `background-repeat: no-repeat;` ensures that the background image does not repeat.
- `background-position: center center;` centers the background image both horizontally and vertically within the element.
- `background-size: cover;` makes the background image cover the entire element, scaling it as necessary.

### Detailed Explanation

#### Background-Position Values

The `background-position` property accepts various values:

- Keywords: `left`, `center`, `right`, `top`, `bottom`
- Length values: `px`, `em`, `%`
- Combinations of keywords and length values

**Examples**:

```css
/* Positioning with keywords */
background-position: top left;
background-position: bottom right;
background-position: center;

/* Positioning with length values */
background-position: 50px 100px;
background-position: 10% 20%;
background-position: 0 0;

/* Combination of keywords and length values */
background-position: left 20px top 10px;
```

#### Background-Repeat Values

The `background-repeat` property accepts the following values:

- `repeat`: Repeats the background image both horizontally and vertically (default).
- `repeat-x`: Repeats the background image only horizontally.
- `repeat-y`: Repeats the background image only vertically.
- `no-repeat`: Does not repeat the background image.
- `space`: Repeats the background image as much as possible without clipping, with space between repetitions.
- `round`: Repeats the background image as much as possible without clipping, scaling the images to fit.

**Examples**:

```css
/* Repeating the background image */
background-repeat: repeat;
background-repeat: repeat-x;
background-repeat: repeat-y;

/* No repeating */
background-repeat: no-repeat;

/* Special repeat modes */
background-repeat: space;
background-repeat: round;
```
## Link Transitions in CSS

Link transitions are used to define the appearance of links (`<a>` tags) in different states. Here are the primary states you can style:

1. **a:link** - Default state of an unvisited link.
2. **a:visited** - State of a visited link.
3. **a:hover** - State when a user mouses over the link.
4. **a:active** - State when the link is being clicked.

### Example

```css
/* Default state of an unvisited link */
a:link {
  color: blue;
  text-decoration: none;
}

/* State of a visited link */
a:visited {
  color: purple;
}

/* State when a user mouses over the link */
a:hover {
  color: red;
  text-decoration: underline;
}

/* State when the link is being clicked */
a:active {
  color: orange;
}
```

# Reference
- date: 2024.07.31
- time: 13:19