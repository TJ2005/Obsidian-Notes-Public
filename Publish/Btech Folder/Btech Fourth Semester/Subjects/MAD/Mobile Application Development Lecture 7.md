---
Title: Mobile Application Development Lecture 5
Status: 
marker: 
tags: 
Date: 2025.01.23
Time: 13:14
---
# Lists
In Android development, **Lists** are a powerful and flexible way to display a collection of items in a user interface. Lists can be viewed using a **ListView**, which is a view that displays a vertically scrolling list of items. Each item in the list can be customized using an **ArrayAdapter**, a simple adapter that binds the data to the **ListView**.

### List View + Array Adapter

- **ListView:**
  - `ListView` is a UI component that displays a list of items in a vertical scrollable format.
  - It is an efficient way to display large data sets as it only creates and displays the visible items on the screen.

- **ArrayAdapter:**
  - `ArrayAdapter` is an adapter used to map an array of data (such as an array or a list of objects) to a `ListView`.
  - It provides a simple way to connect your data (e.g., strings or objects) with the layout you want to display in each item of the list.

### Example Usage:

```xml

```

Here’s a basic example of how to set up a `ListView` using an `ArrayAdapter`:

```java
// In your activity
ListView listView = findViewById(R.id.listView);
String[] items = {"Item 1", "Item 2", "Item 3", "Item 4"};
ArrayAdapter<String> adapter = new ArrayAdapter<>(this, android.R.layout.simple_list_item_1, items);
listView.setAdapter(adapter);
````

- **Explanation:**
    - `ListView` is the UI component that will display the list.
    - The `ArrayAdapter` takes the data (`items` array), and binds it to a simple layout (`android.R.layout.simple_list_item_1`) where each item is a single text view.

### Key Features of ArrayAdapter:

- **Customizing List Item Layouts:** If needed, you can create a custom layout for each item in the list by providing your own XML layout resource.
- **Efficiency:** It optimizes the performance by reusing the list items as you scroll.

---

# References

###### Information

- Date: 2025.01.23
- Time: 13:14
