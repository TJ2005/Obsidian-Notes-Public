---
Title: Web Programming Lecture 8
Status: 
marker:
  - "[[btech]]"
  - "[[Web Programming]]"
  - "[[HTML]]"
  - "[[CSS]]"
tags:
  - BTech
Date: 2024.08.05
Time: 11:14
---
# Web Programming Lecture 8

## Index
1. [Inline Styles](#inline-styles)
2. [Block Model for HTML](#block-model-for-html)
   - [Margin](#margin)
   - [Border](#border)
   - [Padding](#padding)
   - [Content](#content)

---

## 1. Inline Styles
Inline styles are CSS styles applied directly within HTML elements using the `style` attribute. They have the highest specificity and override styles defined in external or internal stylesheets. Here’s a basic example:

```html
<p style="color: blue; font-size: 16px;">This is a blue-colored text with a font size of 16px.</p>
```

### Pros of Inline Styles:
- Quick and easy to apply.
- Useful for testing or overriding other styles.

### Cons of Inline Styles:
- Not reusable.
- Can clutter HTML and make maintenance harder.
- Overwrites styles from external or internal stylesheets, making debugging difficult.

## 2. Block Model for HTML
The block model in HTML is essential for understanding layout and design. It consists of the following elements:

### 2.1 Margin
The margin is the space outside the border of an element. It creates distance between the element's border and the surrounding elements. Margins are transparent and do not affect the element's dimensions.

```css
.element {
    margin: 20px;
}
```


### 2.2 Border
The border surrounds the padding and content of an element. It’s used to define the element's edge and can have different styles, widths, and colors.

```css
.element {
    border: 2px solid black;
    /* 2px = size, solid = style, black = color here */
}
```

#### Border Styles
The `border-style` property defines how the border appears. Here are the different border styles you can use:

- **`solid`**: A continuous, solid line.
  ```css
  border-style: solid;
  ```
- **`dotted`**: A series of dots.
  ```css
  border-style: dotted;
  ```
- **`dashed`**: A series of short dashes.
  ```css
  border-style: dashed;
  ```
- **`double`**: Two solid lines with space between them.
  ```css
  border-style: double;
  ```
- **`groove`**: A 3D, carved appearance.
  ```css
  border-style: groove;
  ```
- **`ridge`**: A 3D, raised appearance.
  ```css
  border-style: ridge;
  ```
- **`inset`**: Appears as though the border is embedded into the page.
  ```css
  border-style: inset;
  ```
- **`outset`**: Appears as though the border is raised from the page.
  ```css
  border-style: outset;
  ```
- **`none`**: No border.
  ```css
  border-style: none;
  ```

You can combine these styles with `border-width` and `border-color` to fully customize the border of an element.

### 2.3 Padding
Padding is the space between the content of an element and its border. It creates an internal buffer within the element, affecting its total size.

```css
.element {
    padding: 15px;
}
```

### 2.4 Content
The content is the actual text or media within the element. It is the innermost part of the box model and is affected by the padding, border, and margin.

```css
.element {
    content: "Hello, World!";
}
```

### Example of Block Model
Here’s how the block model works in practice:

```html
<div class="box">
    Content here
</div>
```

```css
.box {
    margin: 10px;
    border: 5px solid black;
    padding: 20px;
    background-color: lightgray;
}
```

In this example:
- **Margin**: Adds space outside the border.
- **Border**: Adds a solid black border around the element.
- **Padding**: Adds space inside the border, around the content.
- **Content**: The actual text or elements inside the padding area.

## Forms
Forms make the HTML Dynamic because now we are inputting data from the user and now we have to handle it.
```html
<form action ="Script URL" method="GET|POST">
for elements like input, textarea etc.
</form>
```
There are two types of forms

##### Post
The post method is when an input is transferred from a page to another page and this information is in the encrypted form between the two pages.
##### Get
The get method is when the input information is completely available between the two pages. This input information is visible in the URL.

## Example

#### Example 1
```html
<head>
<style>
div.ex
{
width:500px;
padding:10px;
border:20px dotted blue;
margin:20px 100px;
}
</style>

```
## References
- For more details on inline styles, see [Inline Styles Documentation](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/style).
- For a deeper understanding of the block model, refer to [CSS Box Model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model).

---

**Information**
- Date: 2024.08.05
- Time: 11:14