---
Title: Mobile Application Development Lab 2
Status: 
marker:
  - "[[Android]]"
  - "[[Mobile Application Development Lab 1]]"
tags: 
Date: 2025.01.14
Time: 12:43
---
# Structure
Android Studio is an Integrated Development Environment (IDE) used for developing Android apps. It is based on IntelliJ IDEA and provides a complete suite of tools for building, debugging, and testing Android applications. Here's an overview of the structure of Android Studio:

---

### **1. Project Structure**
Android Studio organizes your app's files into a **project structure** that follows Android's build system (Gradle). Here are the key components:

#### **a. `app/` Module**

The `app` module is the core of your project, containing the code and resources for your Android app. Key directories include:

- **`java/` or `kotlin/`**: Contains your Java or Kotlin source code, organized by package name. Example:
    
    - `com.example.mycalculator` (Main activity, classes, etc.)
- **`res/`**: Holds your app's resources, such as:
    
    - **`layout/`**: XML files defining UI layouts (e.g., `activity_main.xml`).
    - **`drawable/`**: Graphics, icons, and other images.
    - **`values/`**: XML files for string resources, colors, styles, and dimensions (e.g., `strings.xml`, `colors.xml`).
    - **`mipmap/`**: App icons for different screen resolutions.
- **`AndroidManifest.xml`**: Describes essential information about the app, such as activities, permissions, and app metadata.
    

#### **b. Gradle Scripts**

Build configuration files written in Groovy or Kotlin for managing dependencies, build types, and plugins:

- **`build.gradle (Module: app)`**: Contains app-specific configurations like dependencies, compile SDK version, etc.
- **`build.gradle (Project)`**: Contains project-wide settings, including Gradle version and plugin configuration.

---

### **2. Android Studio Components**

#### **a. Editor Window**

The main area where you write and edit code, design layouts, or debug your app. It adapts based on the selected file type:
- XML files open the **Layout Editor** with Design and Code views.
- Kotlin or Java files open in the Code Editor.
#### **b. Project View**
Displays the project structure in a hierarchical tree. Common views include:
- **Android View**: Groups files logically (default view).
- **Project View**: Shows the actual file structure.

#### **c. Tool Windows**
Android Studio provides multiple tool windows for different tasks:
- **Logcat**: Displays runtime logs for debugging.
- **Device Manager**: Manage emulators or connected devices.
- **Build Output**: Shows build progress and errors.
- **Terminal**: Command-line interface for running shell commands.

---

### **3. Key Features for Development**

#### **a. Layout Editor**
- **Design View**: Drag-and-drop UI components.
- **Code View**: Edit XML code directly.
- **Component Tree**: View and edit the hierarchy of UI elements.

#### **b. Code Editor**
- **Auto-Completion**: Suggests code as you type.
- **Refactoring Tools**: Simplify code modification (e.g., rename variables, extract methods).
- **Lint Checks**: Static analysis to detect potential bugs and improve performance.

#### **c. Build System**
Android Studio uses Gradle for:
- Dependency management.
- Defining build types (e.g., debug, release).
- Managing app flavors (e.g., free, paid versions).

#### **d. Emulator and Debugger**
- Test your app on virtual devices or physical hardware.
- Debug apps using breakpoints, inspect variables, and analyze app performance.

---

### **4. Creating a Calculator App**
For a calculator app, the key components are:
- **MainActivity** (Java/Kotlin): Logic for button clicks and calculations.
- **`activity_main.xml`**: UI layout with buttons and text fields.
- **Drawable resources**: Icons or backgrounds for your app.

Would you like a more detailed explanation of any specific component or help with coding parts of your calculator app?


# CODE

## XML
```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"  
    xmlns:app="http://schemas.android.com/apk/res-auto"  
    xmlns:tools="http://schemas.android.com/tools"  
    android:layout_width="match_parent"  
    android:layout_height="match_parent"  
    tools:context=".MainActivity"  
    android:background="@color/white"  
    android:padding="30dp"  
    android:orientation="vertical"  
    android:layout_marginTop="0dp">  
  
    <TextView        android:id="@+id/textView2"  
        android:layout_width="match_parent"  
        android:layout_height="wrap_content"  
        android:text="Calculator"  
        android:textSize="60dp" />  
  
    <TextView        android:layout_width="wrap_content"  
        android:layout_height="wrap_content"  
        android:textSize="30dp"  
        android:text="Enter the numbers below"  
        android:layout_marginBottom="10dp"/>  
  
  
    <EditText        android:id="@+id/FirstNumber"  
        android:layout_width="match_parent"  
        android:layout_height="wrap_content"  
        android:ems="10"  
        android:inputType="numberDecimal"  
        android:hint="Enter First number" />  
  
    <EditText        android:id="@+id/SecondNumber"  
        android:layout_width="match_parent"  
        android:layout_height="wrap_content"  
        android:ems="10"  
        android:inputType="numberDecimal"  
        android:hint="Enter Second number" />  
    <LinearLayout        android:layout_width="wrap_content"  
        android:layout_height="wrap_content"  
        android:orientation="horizontal"  
        android:gravity="center"  
        android:layout_marginBottom="10dp"  
        android:layout_gravity="center"  
        >  
  
    >  
        <Button  
            android:id="@+id/addButton"  
            android:layout_width="100dp"  
            android:layout_height="60dp"  
            android:text="+"  
            android:layout_marginEnd="10dp" />  <!-- 10dp gap between buttons -->  
        <Button  
            android:id="@+id/subtractButton"  
            android:layout_width="100dp"  
            android:layout_height="60dp"  
            android:text="-"  
            android:layout_marginEnd="10dp" />  <!-- 10dp gap between buttons -->  
        />  
        <Button  
            android:id="@+id/divideButton"  
            android:layout_width="100dp"  
            android:layout_height="60dp"  
            android:text="/"  
            android:layout_marginEnd="10dp" />  <!-- 10dp gap between buttons -->  
        />  
        <Button  
            android:id="@+id/multiplyButton"  
            android:layout_width="100dp"  
            android:layout_height="60dp"  
            android:text="x"  
            android:layout_marginEnd="10dp" />  <!-- 10dp gap between buttons -->  
        />  
    </LinearLayout>  
</LinearLayout>
```

## MainActivity.Java
```java
package com.example.myapplication;  
import android.os.Bundle;  
import android.view.View;  
import android.widget.Button;  
import android.widget.EditText;  
import android.widget.Toast;  
import androidx.appcompat.app.AppCompatActivity;  
  
public class MainActivity extends AppCompatActivity {  
  
    // Declare the UI elements as variables. These will be used to refer to the respective views in the layout file.  
    EditText editTextFirst, editTextSecond;  // EditTexts for the first and second numbers  
    Button buttonAdd, buttonSubtract, buttonDivide, buttonMultiply;  // Buttons for the four operations  
  
    @Override  
    protected void onCreate(Bundle savedInstanceState) {  
        super.onCreate(savedInstanceState);  
        setContentView(R.layout.activity_main);  // Set the layout for the activity  
  
        // Bind the views (UI elements) to the Java variables        editTextFirst = findViewById(R.id.FirstNumber);  // Find the EditText where the first number will be entered  
        editTextSecond = findViewById(R.id.SecondNumber);  // Find the EditText where the second number will be entered  
  
        buttonAdd = findViewById(R.id.addButton);  // Find the button for addition  
        buttonSubtract = findViewById(R.id.subtractButton);  // Find the button for subtraction  
        buttonDivide = findViewById(R.id.divideButton);  // Find the button for division  
        buttonMultiply = findViewById(R.id.multiplyButton);  // Find the button for multiplication  
  
        // Set up listeners for the buttons. When a button is clicked, the corresponding operation is triggered.  
        // For the "Add" button, when clicked, it calls the handleOperation method with the "+" operation.        buttonAdd.setOnClickListener(new View.OnClickListener() {  
  
            // We use override  
            @Override  
            public void onClick(View v) {  
                handleOperation("+");  // "+" operation for addition  
            }  
        });  
  
        // For the "Subtract" button, when clicked, it calls the handleOperation method with the "-" operation.  
        buttonSubtract.setOnClickListener(new View.OnClickListener() {  
            @Override  
            public void onClick(View v) {  
                handleOperation("-");  // "-" operation for subtraction  
            }  
        });  
  
        // For the "Divide" button, when clicked, it calls the handleOperation method with the "/" operation.  
        buttonDivide.setOnClickListener(new View.OnClickListener() {  
            @Override  
            public void onClick(View v) {  
                handleOperation("/");  // "/" operation for division  
            }  
        });  
  
        // For the "Multiply" button, when clicked, it calls the handleOperation method with the "x" operation.  
        buttonMultiply.setOnClickListener(new View.OnClickListener() {  
            @Override  
            public void onClick(View v) {  
                handleOperation("x");  // "x" operation for multiplication  
            }  
        });  
    }  
  
    // Method to handle arithmetic operations. It takes the operation symbol as a parameter.  
    private void handleOperation(String operation) {  
        // Get the text entered by the user in the first and second EditTexts  
        String inputFirst = editTextFirst.getText().toString();  
        String inputSecond = editTextSecond.getText().toString();  
  
        // Check if either of the inputs is empty  
        if (inputFirst.isEmpty() || inputSecond.isEmpty()) {  
            // If either input is empty, show a toast message asking the user to enter both numbers  
            Toast.makeText(MainActivity.this, "Please enter both numbers", Toast.LENGTH_SHORT).show();  
            return;  // Exit the method if inputs are empty  
        }  
  
        // Convert the input strings into double values to perform arithmetic operations  
        double num1 = Double.parseDouble(inputFirst);  // Parse the first number  
        double num2 = Double.parseDouble(inputSecond);  // Parse the second number  
        double result = 0;  // Variable to store the result of the operation  
  
        // Perform the selected arithmetic operation        switch (operation) {  
            case "+":  
                result = num1 + num2;  // Addition  
                break;  
            case "-":  
                result = num1 - num2;  // Subtraction  
                break;  
            case "/":  
                // If the user attempts to divide by zero, show an error message  
                if (num2 == 0) {  
                    Toast.makeText(MainActivity.this, "Cannot divide by zero", Toast.LENGTH_SHORT).show();  
                    return;  // Exit the method if division by zero is attempted  
                }  
                result = num1 / num2;  // Division  
                break;  
            case "x":  
                result = num1 * num2;  // Multiplication  
                break;  
        }  
  
        // After performing the operation, display the result in a toast message  
        Toast.makeText(MainActivity.this, "Result: " + result, Toast.LENGTH_SHORT).show();  
    }  
}
```

# Output
![[IMG-20250730000528593.png]]
# Explanation of code
## XML
### 1. **Root `LinearLayout`**:

```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity"
    android:background="@color/white"
    android:padding="30dp"
    android:orientation="vertical"
    android:layout_marginTop="0dp">
```

- **`xmlns:android`**: Specifies the XML namespace for Android attributes. Required for every Android XML layout.
- **`xmlns:app`**: This is for custom attributes and resources. It is not used in your layout, but it’s commonly included.
- **`xmlns:tools`**: This is used for tools-specific attributes (e.g., for preview in Android Studio). It won't appear in the final app but is used for development.
- **`android:layout_width="match_parent"`**: The layout will take the full width of the parent.
- **`android:layout_height="match_parent"`**: The layout will take the full height of the parent.
- **`tools:context=".MainActivity"`**: Specifies the context for tools (used by Android Studio for layout previews).
- **`android:background="@color/white"`**: Sets the background color to white. The `@color/white` refers to a color resource defined in `res/values/colors.xml`.
- **`android:padding="30dp"`**: Adds padding of 30dp around all sides inside the layout.
- **`android:orientation="vertical"`**: Defines the direction of the layout's child elements; here, they will be stacked vertically.
- **`android:layout_marginTop="0dp"`**: Sets the top margin to 0, i.e., no space above the layout.

### 2. **`TextView` for Title ("Calculator")**:

```xml
<TextView
    android:id="@+id/textView2"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:text="Calculator"
    android:textSize="60dp" />
```

- **`android:id="@+id/textView2"`**: The ID for the `TextView`, used for referencing it programmatically.
- **`android:layout_width="match_parent"`**: The width of the `TextView` will stretch to fill the entire width of its parent.
- **`android:layout_height="wrap_content"`**: The height will adjust based on the content inside the `TextView` (in this case, the text).
- **`android:text="Calculator"`**: The text displayed inside the `TextView`.
- **`android:textSize="60dp"`**: The font size for the text is set to 60 density-independent pixels (dp).

### 3. **`TextView` for Instructions ("Enter the numbers below")**:

```xml
<TextView
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:textSize="30dp"
    android:text="Enter the numbers below"
    android:layout_marginBottom="10dp"/>
```

- **`android:layout_width="wrap_content"`**: The width will adjust to the content of the `TextView`.
- **`android:layout_height="wrap_content"`**: The height will adjust to the content inside.
- **`android:textSize="30dp"`**: The font size is set to 30dp.
- **`android:text="Enter the numbers below"`**: The text displayed inside the `TextView`.
- **`android:layout_marginBottom="10dp"`**: Adds a margin of 10dp below the `TextView`, separating it from other elements.

### 4. **First `EditText` (Input Field for First Number)**:

```xml
<EditText
    android:id="@+id/FirstNumber"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:ems="10"
    android:inputType="numberDecimal"
    android:hint="Enter First number" />
```

- **`android:id="@+id/FirstNumber"`**: The ID for the `EditText`, allowing you to reference it programmatically.
- **`android:layout_width="match_parent"`**: The width will stretch to fill the available space of the parent.
- **`android:layout_height="wrap_content"`**: The height adjusts to fit the content.
- **`android:ems="10"`**: Defines the width of the input field in terms of character widths (i.e., it will be wide enough to accommodate 10 characters).
- **`android:inputType="numberDecimal"`**: Specifies the input type for the `EditText`, in this case, numbers with decimal points (e.g., for entering decimal numbers).
- **`android:hint="Enter First number"`**: A hint that shows inside the `EditText` before the user types anything.

### 5. **Second `EditText` (Input Field for Second Number)**:

```xml
<EditText
    android:id="@+id/SecondNumber"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:ems="10"
    android:inputType="numberDecimal"
    android:hint="Enter Second number" />
```

- Similar to the first `EditText`, this field allows the user to input the second number.

### 6. **`LinearLayout` for Buttons**:

```xml
<LinearLayout
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:orientation="horizontal"
    android:gravity="center"
    android:layout_marginBottom="10dp"
    android:layout_gravity="center">
```

- **`android:layout_width="wrap_content"`**: The width will adjust to the size of its content (the buttons).
- **`android:layout_height="wrap_content"`**: The height will adjust to the content inside (the buttons).
- **`android:orientation="horizontal"`**: The child elements (buttons) will be arranged horizontally.
- **`android:gravity="center"`**: Aligns the content (buttons) within the `LinearLayout` to the center horizontally and vertically.
- **`android:layout_marginBottom="10dp"`**: Adds a bottom margin of 10dp, separating it from elements below.
- **`android:layout_gravity="center"`**: Centers the `LinearLayout` within its parent container.

### 7. **Buttons for Operations**:

```xml
<Button
    android:id="@+id/addButton"
    android:layout_width="100dp"
    android:layout_height="60dp"
    android:text="+"
    android:layout_marginEnd="10dp" />
<Button
    android:id="@+id/subtractButton"
    android:layout_width="100dp"
    android:layout_height="60dp"
    android:text="-"
    android:layout_marginEnd="10dp" />
<Button
    android:id="@+id/divideButton"
    android:layout_width="100dp"
    android:layout_height="60dp"
    android:text="/"
    android:layout_marginEnd="10dp" />
<Button
    android:id="@+id/multiplyButton"
    android:layout_width="100dp"
    android:layout_height="60dp"
    android:text="x"
    android:layout_marginEnd="10dp" />
```

- **`android:id="@+id/[buttonName]"`**: IDs for each button, used for referencing in the code.
- **`android:layout_width="100dp"`**: Specifies the width of each button to be 100dp.
- **`android:layout_height="60dp"`**: Specifies the height of each button to be 60dp.
- **`android:text="[operator]"`**: Text displayed on the button (e.g., "+" for the addition button).
- **`android:layout_marginEnd="10dp"`**: Adds a 10dp margin between the buttons to separate them.

### Summary:

- **LinearLayout** is used to arrange UI elements vertically or horizontally.
- **TextViews** display static information like the title and instructions.
- **EditTexts** allow user input for numbers, and each has a `hint` to guide the user.
- **Buttons** allow the user to trigger actions (e.g., arithmetic operations), and their appearance is customized using `layout_width`, `layout_height`, and `text`.

## Java File
This code represents a simple Android Calculator app, where users can perform basic arithmetic operations (addition, subtraction, multiplication, and division). Here's a breakdown of how the code works:

### Class Declaration

```java
public class MainActivity extends AppCompatActivity {
```

This declares the `MainActivity` class that extends `AppCompatActivity`, which is a subclass of Android's `Activity` class. This is the main entry point of the app, which manages the UI and user interactions.

### Variable Declarations

```java
EditText editTextFirst, editTextSecond;
Button buttonAdd, buttonSubtract, buttonDivide, buttonMultiply;
```

- **`EditText`**: Used for user input (two EditTexts here for entering the numbers).
- **`Button`**: Buttons for triggering different arithmetic operations (+, -, x, /).

### `onCreate()` Method

```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_main);  // Set the layout for the activity
```

This method is called when the activity is created. It sets the layout for the activity from the XML file `activity_main.xml`.

### Binding Views

```java
editTextFirst = findViewById(R.id.FirstNumber);
editTextSecond = findViewById(R.id.SecondNumber);
buttonAdd = findViewById(R.id.addButton);
buttonSubtract = findViewById(R.id.subtractButton);
buttonDivide = findViewById(R.id.divideButton);
buttonMultiply = findViewById(R.id.multiplyButton);
```

Here, the UI components (EditText and Button) defined in the XML layout are bound to the variables in the Java code using their respective IDs (`R.id.FirstNumber`, `R.id.addButton`, etc.).

### Setting Button Listeners

Each button (addition, subtraction, multiplication, and division) has an `OnClickListener` attached. When a button is clicked, it calls the `handleOperation()` method with the corresponding operation symbol:

```java
buttonAdd.setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View v) {
        handleOperation("+");
    }
});
```

Similar listeners are set for the other buttons (subtract, divide, multiply), each passing its respective operator to the `handleOperation()` method.

### `handleOperation()` Method

```java
private void handleOperation(String operation) {
    String inputFirst = editTextFirst.getText().toString();
    String inputSecond = editTextSecond.getText().toString();
```

- First, the method retrieves the text entered in the two `EditText` fields (`inputFirst` and `inputSecond`).

```java
if (inputFirst.isEmpty() || inputSecond.isEmpty()) {
    Toast.makeText(MainActivity.this, "Please enter both numbers", Toast.LENGTH_SHORT).show();
    return;  // Exit the method if inputs are empty
}
```

- It checks if any of the inputs are empty. If either is empty, a `Toast` message is displayed, prompting the user to enter both numbers. The method exits early.

```java
double num1 = Double.parseDouble(inputFirst);  
double num2 = Double.parseDouble(inputSecond);
```

- The inputs are converted from `String` to `double` to perform arithmetic operations.

```java
double result = 0;  // Variable to store the result of the operation
```

- A variable `result` is declared to store the outcome of the arithmetic operation.

### Switch Statement for Operations

```java
switch (operation) {
    case "+":
        result = num1 + num2;  // Addition
        break;
    case "-":
        result = num1 - num2;  // Subtraction
        break;
    case "/":
        if (num2 == 0) {
            Toast.makeText(MainActivity.this, "Cannot divide by zero", Toast.LENGTH_SHORT).show();
            return;  // Exit the method if division by zero is attempted
        }
        result = num1 / num2;  // Division
        break;
    case "x":
        result = num1 * num2;  // Multiplication
        break;
}
```

- The `switch` statement checks which operation was passed (addition, subtraction, multiplication, or division).
- Each case performs the respective operation (`+`, `-`, `x`, `/`) and stores the result.
- For division, it also checks if the second number is zero, as dividing by zero would result in an error. If so, a toast message is displayed, and the method returns early.

### Displaying the Result

```java
Toast.makeText(MainActivity.this, "Result: " + result, Toast.LENGTH_SHORT).show();
```

- After the operation is performed, the result is displayed using a `Toast` message to show the calculated value.

### Summary

This code represents an Android calculator that performs four basic arithmetic operations. It:

- Binds UI components (EditText and Button) to Java variables.
- Sets `OnClickListener` for each operation button.
- Retrieves input values, checks for empty inputs, performs the selected operation, and displays the result via a `Toast`.
# References


###### Information
- date: 2025.01.14
- time: 12:43