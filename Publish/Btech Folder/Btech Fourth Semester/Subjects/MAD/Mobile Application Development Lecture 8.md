---
Title: Mobile Application Development Lecture 4
Status: 
marker: 
tags: 
Date: 2025.01.20
Time: 11:46
---
# Android Concepts Used in `SecondActivity.java`

## 1. **Package Declaration**
   - `package com.example.lenovo.multipleactivities;`
   - The package declaration helps organize classes and avoid name conflicts. It follows Java naming conventions, typically using a reverse domain name structure.

## 2. **Import Statements**
   - `import android.app.Activity;`
   - `import android.content.Intent;`
   - `import android.os.Bundle;`
   - `import android.widget.TextView;`
   - These imports bring necessary Android classes into the scope, such as:
     - `Activity`: Represents an Android screen.
     - `Intent`: Used for data communication between activities.
     - `Bundle`: Used to pass data across activity states.
     - `TextView`: A UI widget for displaying text.

## 3. **Activity Class Inheritance**
   - `public class SecondActivity extends Activity`
   - The `SecondActivity` class extends `Activity`, meaning it inherits properties and behaviors from the Android `Activity` class, making it an interactive UI screen.

## 4. **Constant Variable Declaration**
   - `public final static String MESSAGE_KEY = "com.example.lenovo.multipleactivities.message_key";`
   - This constant key is used to retrieve data from the intent. It follows best practices for defining constant values.

## 5. **TextView Declaration**
   - `TextView textView;`
   - A member variable is declared to hold a reference to the TextView UI element, which displays the received message.

## 6. **onCreate() Method**
   - `@Override protected void onCreate(Bundle savedInstanceState)`
   - This lifecycle method is overridden to initialize the activity when it is created.
   - The `Bundle savedInstanceState` parameter is used to restore the activity's previous state if applicable.

## 7. **Setting Layout for the Activity**
   - `setContentView(R.layout.activity_second);`
   - This line sets the user interface layout for the activity from the XML resource file `activity_second.xml`.

## 8. **Intent Handling**
   - `Intent intent = getIntent();`
   - `String message = intent.getStringExtra(MESSAGE_KEY);`
   - The `getIntent()` method fetches the intent that started this activity, and `getStringExtra()` retrieves the string data passed from the previous activity.

## 9. **UI Component Initialization**
   - `textView = findViewById(R.id.textView);`
   - The `findViewById()` method finds the TextView element from the XML layout using its ID.

## 10. **Displaying Retrieved Data**
   - `textView.setText(message);`
   - The retrieved message is set to the `TextView` to display the data passed from the previous activity.

## 11. **Best Practices in the Code**
   - Proper use of constants for intent keys to avoid hard-coded strings.
   - Ensuring `findViewById` is correctly used to reference UI elements to prevent `NullPointerException`.
   - Code follows standard Android lifecycle and structure.

## 12. **XML Layout Dependency**
   - The code assumes the existence of an `activity_second.xml` file in the `res/layout` folder containing a `TextView` with the ID `textView`.

---

## **Key Takeaways**
1. Always declare constant keys for passing data between activities.
2. Use `Intent` to communicate between different screens.
3. Handle `NullPointerException` by verifying the existence of UI elements.
4. Follow Android's activity lifecycle methods like `onCreate()`.
5. Always set the correct layout using `setContentView()`.
6. Use descriptive names for variables and constants to enhance code readability.
