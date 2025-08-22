---
Title: Mobile Application Development Lab 3
Status: 
marker: 
tags: 
Date: 2025.01.20
Time: 12:48
---
# Mobile Application Development Lab 2

## ActivityMain.xml Explanation

This XML file defines the user interface layout of the main activity using `RelativeLayout`. It contains the following components:

```xml
<RelativeLayout  
    xmlns:android="http://schemas.android.com/apk/res/android"  
    xmlns:app="http://schemas.android.com/apk/res-auto"  
    xmlns:tools="http://schemas.android.com/tools"  
    android:id="@+id/main"  
    android:layout_width="match_parent"  
    android:layout_height="match_parent"  
    tools:context=".MainActivity">  
  
    <!-- AppBar Section -->  
    <androidx.appcompat.widget.Toolbar  
        android:id="@+id/toolbar"  
        android:layout_width="match_parent"  
        android:layout_height="?attr/actionBarSize"  
        android:background="?attr/colorPrimary"  
        android:title="@string/Title"  
        android:titleTextColor="@android:color/white"  
        android:layout_alignParentTop="true" />  
  
    <!-- Content Section -->  
    <Spinner  
        android:id="@+id/spinner2"  
        android:layout_width="match_parent"  
        android:layout_height="wrap_content"  
        android:layout_below="@id/toolbar"  
        android:layout_marginTop="16dp" />  
  
    <ImageView android:id="@+id/imageView"  
        android:layout_width="wrap_content"  
        android:layout_height="wrap_content"  
        android:layout_below="@id/spinner2"  
        android:layout_centerHorizontal="true"  
        android:layout_marginTop="16dp"  
        android:padding="10dp"/>  
  
</RelativeLayout>
```

## strings.xml Explanation

This resource file stores string values to be used in the UI, promoting better maintainability.

```xml
<resources>  
    <string name="app_name">PhotoViewer</string>  
    <string name="Title">Select an option</string>  
    <string-array name="options">  
        <item>Daft Punk</item>  
        <item>Foo Fighters</item>  
        <item>Kanye</item>  
        <item>Radiohead</item>  
        <item>Hozier</item>  
    </string-array>  
</resources>
```

## MainActivity.java Explanation

```java
// Package declaration
package com.example.photoviewer;

// Import necessary Android and UI components
import android.os.Bundle;
import android.view.View;
import android.widget.AdapterView;
import android.widget.ArrayAdapter;
import android.widget.ImageView;
import android.widget.Spinner;
import android.widget.Toast;

// Import AppCompatActivity to support older Android versions
import androidx.appcompat.app.AppCompatActivity;

// MainActivity class extending AppCompatActivity
public class MainActivity extends AppCompatActivity {

    @Override  
    protected void onCreate(Bundle savedInstanceState) {  
        super.onCreate(savedInstanceState);  
        setContentView(R.layout.activity_main);  // Link this Java class to the layout defined in activity_main.xml
  
        // Initialize the Spinner and ImageView from the layout
        Spinner spinner = findViewById(R.id.spinner2);  // Spinner to select an option
        ImageView imageView = findViewById(R.id.imageView);  // ImageView to display the corresponding image
  
        // Create an ArrayAdapter to populate the Spinner with options from the strings.xml resource
        ArrayAdapter<CharSequence> adapter = ArrayAdapter.createFromResource(  
                this,  
                R.array.options,  // Reference to string-array resource containing the list items
                android.R.layout.simple_spinner_item  // Default layout for spinner items
        );  
        adapter.setDropDownViewResource(android.R.layout.simple_spinner_dropdown_item);  // Set dropdown layout style
        spinner.setAdapter(adapter);  // Attach the adapter to the spinner
  
        // Define the action to perform when an item is selected from the spinner
        spinner.setOnItemSelectedListener(new AdapterView.OnItemSelectedListener() {  
            @Override  
            public void onItemSelected(AdapterView<?> parent, View view, int position, long id) {  
                // Get the selected option as a string
                String selectedOption = parent.getItemAtPosition(position).toString();  
                // Display a Toast message showing the selected option
                Toast.makeText(MainActivity.this, "Selected: " + selectedOption, Toast.LENGTH_SHORT).show();  
  
                // Switch case to update the ImageView based on the selected item position
                switch (position) {  
                    case 0: // Daft Punk  
                        imageView.setImageResource(R.drawable.daft_punk);  // Set corresponding image
                        break;  
                    case 1: // Foo Fighters  
                        imageView.setImageResource(R.drawable.foo_fighters);  
                        break;  
                    case 2: // Kanye  
                        imageView.setImageResource(R.drawable.kanye);  
                        break;  
                    case 3: // Radiohead  
                        imageView.setImageResource(R.drawable.radiohead);  
                        break;  
                    case 4: // Hozier  
                        imageView.setImageResource(R.drawable.hozier);  
                        break;  
                }  
            }  
  
            @Override  
            public void onNothingSelected(AdapterView<?> parent) {  
                // Do nothing if no item is selected
            }  
        });  
    }  
}
```

## Summary

- The app consists of a simple UI with a toolbar, spinner, and image view.
- The spinner allows users to select different options.
- Based on the selection, a corresponding image is displayed.
- Toast messages provide feedback to the user.

This setup showcases fundamental Android UI components such as `RelativeLayout`, `Spinner`, `ImageView`, and `Toolbar` along with basic event handling and resource management.
![[IMG-20250730000528652.mp4]]

 

## Explanation of the Code

### 1. Package Declaration

The package `com.example.photoviewer` groups related classes for the app.

### 2. Imports

The necessary Android and UI components are imported:

- `Bundle` for saving activity state.
- `View` for handling UI elements.
- `AdapterView` for managing item selections.
- `ArrayAdapter` to bind data to views.
- `ImageView` to display images.
- `Spinner` for dropdown selection.
- `Toast` for displaying short messages.
- `AppCompatActivity` to provide compatibility with older Android versions.

### 3. MainActivity Class

The `MainActivity` class extends `AppCompatActivity`, which provides backward compatibility for older Android versions.

### 4. onCreate Method

- `setContentView(R.layout.activity_main)`: Links the XML layout to the activity.
- `findViewById(R.id.spinner2)`: Finds the Spinner UI element.
- `findViewById(R.id.imageView)`: Finds the ImageView UI element.

### 5. Spinner Setup

- An `ArrayAdapter` is created to bind the `options` string array from `strings.xml` to the Spinner.
- `android.R.layout.simple_spinner_item`: Defines a basic layout for displaying items in the dropdown.
- `setDropDownViewResource`: Sets how items will appear when expanded.
- `spinner.setAdapter(adapter)`: Attaches the adapter to the Spinner.

### 6. Spinner Item Selection

A listener is set up to detect when an item is selected:

- `onItemSelected`:
    - Retrieves the selected item and displays it using `Toast`.
    - A `switch` statement is used to update the ImageView based on selection.
- `onNothingSelected`: Placeholder if no selection is made.

### 7. Switch Case Logic

Depending on the selected item, an appropriate image is displayed:

- Case 0: Daft Punk
- Case 1: Foo Fighters
- Case 2: Kanye
- Case 3: Radiohead
- Case 4: Hozier

### 8. XML Layout Components

#### ActivityMain.xml

- **Toolbar**
    - Provides an app bar with a title.
- **Spinner**
    - Allows user to select a music band.
- **ImageView**
    - Displays an image corresponding to the selected item.

#### strings.xml

Contains string resources for app name, title, and list of band names.

### 9. Summary

- The app includes a toolbar, a spinner, and an image view.
- The spinner lets users choose from a list of bands.
- The corresponding image appears based on the selection.
- Toast notifications provide user feedback.
# References


###### Information
- date: 2025.01.20
- time: 12:48