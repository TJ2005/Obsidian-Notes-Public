---
Title: Mobile Application Development Lecture 3
Status: 
marker: 
tags: 
Date: 2025.01.13
Time: 11:08
---
# Mobile Application Development UI Components
When developing mobile applications, especially for Android, various UI components are used to build the graphical user interface (GUI). These components allow interaction with the user, such as text input, button presses, and image displays. Below is a list of commonly used UI elements in Android development:
## 1. **TextView**
   - **Description**: A `TextView` is used to display text on the screen. It is commonly used for static labels, instructions, or other textual content in an app.
   - **Example**: 
     ```xml
     <TextView
         android:id="@+id/sampleTextView"
         android:layout_width="wrap_content"
         android:layout_height="wrap_content"
         android:text="Hello, World!" />
     ```

## 2. **EditText**
   - **Description**: An `EditText` is used to accept input from the user. It is typically used for forms or anywhere the user needs to enter text, such as a login form.
   - **Example**: 
     ```xml
     <EditText
         android:id="@+id/sampleEditText"
         android:layout_width="match_parent"
         android:layout_height="wrap_content"
         android:hint="Enter your name" />
     ```

## 3. **AutoCompleteTextView**
   - **Description**: A `AutoCompleteTextView` is a subclass of `EditText` that provides suggestions based on user input. It helps the user fill in text fields quickly by suggesting possible completions.
   - **Example**:
     ```xml
     <AutoCompleteTextView
         android:id="@+id/sampleAutoCompleteTextView"
         android:layout_width="match_parent"
         android:layout_height="wrap_content"
         android:hint="Start typing..."
         android:completionThreshold="1"/>
     ```

## 4. **Button**
   - **Description**: A `Button` is used for user interaction. It is typically clicked to perform an action, such as submitting a form or navigating to another screen.
   - **Example**:
     ```xml
     <Button
         android:id="@+id/sampleButton"
         android:layout_width="wrap_content"
         android:layout_height="wrap_content"
         android:text="Click me!" />
     ```

## 5. **ImageButton**
   - **Description**: An `ImageButton` is similar to a `Button`, but instead of text, it displays an image. It is useful when you want to represent actions with icons (e.g., play, pause).
   - **Example**:
     ```xml
     <ImageButton
         android:id="@+id/sampleImageButton"
         android:layout_width="wrap_content"
         android:layout_height="wrap_content"
         android:src="@drawable/sample_image" />
     ```

## 6. **CheckBox**
   - **Description**: A `CheckBox` allows the user to select or deselect a single option. It is often used in forms or settings where multiple choices can be made.
   - **Example**:
     ```xml
     <CheckBox
         android:id="@+id/sampleCheckBox"
         android:layout_width="wrap_content"
         android:layout_height="wrap_content"
         android:text="I agree to the terms" />
     ```

## 7. **RadioButton**
   - **Description**: A `RadioButton` is used in a group of `RadioButtons` where only one option can be selected at a time. It is often used for selecting a single option from a set of choices.
   - **Example**:
     ```xml
     <RadioGroup
         android:id="@+id/radioGroup"
         android:layout_width="wrap_content"
         android:layout_height="wrap_content">
         
         <RadioButton
             android:id="@+id/sampleRadioButton1"
             android:layout_width="wrap_content"
             android:layout_height="wrap_content"
             android:text="Option 1" />
             
         <RadioButton
             android:id="@+id/sampleRadioButton2"
             android:layout_width="wrap_content"
             android:layout_height="wrap_content"
             android:text="Option 2" />
     </RadioGroup>
     ```

## 8. **Spinner**
   - **Description**: A `Spinner` provides a dropdown menu to select one item from a list. It is an alternative to `RadioButton` when there are too many options to display at once.
   - **Example**:
     ```xml
     <Spinner
         android:id="@+id/sampleSpinner"
         android:layout_width="wrap_content"
         android:layout_height="wrap_content" />
     ```

## 9. **Switch**
   - **Description**: A `Switch` is a toggle button that can either be on or off. It is commonly used in settings to enable or disable a feature.
   - **Example**:
     ```xml
     <Switch
         android:id="@+id/sampleSwitch"
         android:layout_width="wrap_content"
         android:layout_height="wrap_content"
         android:text="Enable notifications" />
     ```

## 10. **ImageView**
   - **Description**: An `ImageView` is used to display an image to the user. It supports various image formats like PNG, JPG, etc.
   - **Example**:
     ```xml
     <ImageView
         android:id="@+id/sampleImageView"
         android:layout_width="wrap_content"
         android:layout_height="wrap_content"
         android:src="@drawable/sample_image" />
     ```

## 11. **ProgressBar**
   - **Description**: A `ProgressBar` is used to show the progress of an operation, like file downloading or data processing. It can be displayed in a circular or horizontal form.
   - **Example**:
     ```xml
     <ProgressBar
         android:id="@+id/sampleProgressBar"
         android:layout_width="wrap_content"
         android:layout_height="wrap_content"
         android:visibility="gone" />
     ```

## 12. **SeekBar**
   - **Description**: A `SeekBar` allows the user to select a value from a range by dragging a thumb across a horizontal bar. It is commonly used for volume control or setting values within a range.
   - **Example**:
     ```xml
     <SeekBar
         android:id="@+id/sampleSeekBar"
         android:layout_width="match_parent"
         android:layout_height="wrap_content" />
     ```

## Conclusion
These UI components are essential for building interactive and user-friendly mobile applications. By combining them in various ways, developers can create complex interfaces that respond to user input and display the necessary information effectively.


# Checking *Cases*

```java
public void onCheckBoxClicked(View view) {
    // Determine if the checkbox is checked
    boolean checked = ((CheckBox) view).isChecked();  // Type-cast view to CheckBox

    // Switch statement based on the checkbox ID
    switch (view.getId()) {
        case R.id.checkbox_option1:
            if (checked) {
                // Perform action when checkbox_option1 is checked
                Toast.makeText(getApplicationContext(), "Option 1 is selected", Toast.LENGTH_SHORT).show();
            } else {
                // Perform action when checkbox_option1 is unchecked
                Toast.makeText(getApplicationContext(), "Option 1 is deselected", Toast.LENGTH_SHORT).show();
            }
            break;

        case R.id.checkbox_option2:
            if (checked) {
                // Perform action when checkbox_option2 is checked
                Toast.makeText(getApplicationContext(), "Option 2 is selected", Toast.LENGTH_SHORT).show();
            } else {
                // Perform action when checkbox_option2 is unchecked
                Toast.makeText(getApplicationContext(), "Option 2 is deselected", Toast.LENGTH_SHORT).show();
            }
            break;
        
        // Add more cases for other checkboxes if needed
        
        default:
            break;
    }
}
```

### Explanation of Changes:

1. **Type-casting**: The `view` object is a general `View` type, so it needs to be cast to a `CheckBox` to call `isChecked()` on it.
    
    ```java
    boolean checked = ((CheckBox) view).isChecked();
    ```
    
2. **Switch Case**: The `switch` statement is used to check which checkbox was clicked based on its `ID`. In this example, we handle two checkboxes, `checkbox_option1` and `checkbox_option2`. If more checkboxes are involved, you can add additional cases.
    
3. **Toast Messages**: For each checkbox, a `Toast` is displayed to indicate whether the option was selected or deselected.
    
4. **`getApplicationContext()`**: The `Toast` uses the `getApplicationContext()` method to get the context, which is required to show the message. If you're inside an `Activity`, you can also use `this` as the context.
    

### Example of XML Layout:

Ensure that your checkboxes in the XML layout file are correctly defined with the respective IDs:

```xml
<CheckBox
    android:id="@+id/checkbox_option1"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="Option 1"
    android:onClick="onCheckBoxClicked" />

<CheckBox
    android:id="@+id/checkbox_option2"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="Option 2"
    android:onClick="onCheckBoxClicked" />
```

The `android:onClick="onCheckBoxClicked"` attribute links the click event of each checkbox to the `onCheckBoxClicked` method in your activity.