---
Title: M1 MAD Currency Question
Status: 
marker:
  - "[[Exam Solution]]"
  - "[[Mobile Application Development (MAD)]]"
tags: 
Date: 2025.02.04
Time: 20:08
---
# Android Currency Converter App - Detailed Explanation

This project is a simple currency converter application that allows users to input an amount in INR and convert it into various currencies such as Dollars, Yens, Pounds, and Bhat.

The structure of the app involves the following key components:

1. **MainActivity**: The entry point of the app where the user can choose between different types of conversions (Currency, Time, Speed, and Temperature). In this case, we focus on the Currency conversion.
    
2. **Currency Activity**: This activity handles the currency conversion. It lets users input an amount, select the target currency, and display the converted value.
    
3. **XML Layouts**: These define the user interface elements for the activities. We have XML files for the main screen and currency conversion screen.
    
4. **Java Code**: Implements the logic for handling user input, converting the currency, and displaying the result.
    

---

### 1. **Project Structure**

The overall structure of the project is as follows:

```
- src
  - MainActivity.java
  - Currency.java
- res
  - layout
    - activity_main.xml
    - currency.xml
  - values
    - strings.xml
  - mipmap
    - ic_launcher.xml
```

### 2. **XML Layouts for Structures**

#### `activity_main.xml` - Main Screen Layout

This XML file defines the layout for the main screen where users select which type of conversion they want to perform.

```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity"
    android:padding="20dp"
    android:orientation="vertical">

    <!-- Title -->
    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_centerHorizontal="true"
        android:width="450dp"
        android:background="#673AB7"
        android:gravity="center"
        android:padding="25dp"
        android:text="Converter"
        android:textColor="@color/white"/>

    <!-- Buttons for each type of conversion -->
    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_centerHorizontal="true"
        android:gravity="center"
        android:paddingTop="100dp"
        android:orientation="vertical">

        <!-- Currency Button -->
        <Button
            android:id="@+id/currency"
            android:layout_width="200dp"
            android:layout_height="60dp"
            android:text="Currency"/>
        
        <!-- Time Button -->
        <Button
            android:id="@+id/time"
            android:layout_width="200dp"
            android:layout_height="60dp"
            android:text="Time"/>
        
        <!-- Speed Button -->
        <Button
            android:id="@+id/speed"
            android:layout_width="200dp"
            android:layout_height="60dp"
            android:text="Speed"/>
        
        <!-- Temperature Button -->
        <Button
            android:id="@+id/Temperature"
            android:layout_width="200dp"
            android:layout_height="60dp"
            android:text="Temperature"/>
    </LinearLayout>
</RelativeLayout>
```

- **RelativeLayout** is used as the root layout, which is flexible and allows for easy positioning of elements.
- **TextView** at the top displays the title "Converter" in a centered, stylized text box.
- A **LinearLayout** contains four **Button** elements for Currency, Time, Speed, and Temperature conversions.

#### `currency.xml` - Currency Conversion Layout

This XML file defines the layout for the Currency conversion screen, where the user inputs an amount and selects a target currency to convert to.

```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".Currency"
    android:padding="20dp">

    <!-- Title -->
    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_centerHorizontal="true"
        android:width="450dp"
        android:background="#673AB7"
        android:gravity="center"
        android:padding="25dp"
        android:text="Currency"
        android:textColor="@color/white"/>

    <!-- Input fields and UI elements -->
    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_centerHorizontal="true"
        android:gravity="center"
        android:paddingTop="100dp"
        android:orientation="vertical">
        
        <!-- Instruction Text -->
        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Enter the Currency in INR"
            android:padding="15dp"/>

        <!-- User input field for amount -->
        <EditText
            android:id="@+id/editTextNumberDecimal"
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            android:inputType="number"
            android:hint="Enter the amount here"/>

        <!-- Instruction Text -->
        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Select the Currency to be converted"
            android:padding="15dp"/>

        <!-- Spinner to choose target currency -->
        <Spinner
            android:id="@+id/spinner"
            android:layout_width="match_parent"
            android:layout_height="70dp"/>

        <!-- Output Text to display the conversion result -->
        <TextView
            android:id="@+id/output"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_centerHorizontal="true"
            android:gravity="center"
            android:padding="15dp"
            android:text="Output"/>
    </LinearLayout>
</RelativeLayout>
```

- **TextView** is used to display instructions and the result.
- **EditText** allows the user to input the amount of money they wish to convert.
- **Spinner** is used to display a dropdown menu for selecting the currency to convert to.
- The **output TextView** displays the result of the conversion.

---

### 3. **Java Code Explanation**

#### `MainActivity.java` - Main Activity Logic

```java
package com.example.m1k057;

import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Find the Currency button by its ID
        Button currencyButton = findViewById(R.id.currency);
        
        // Set an onClickListener to start the Currency activity when the button is clicked
        currencyButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // Create an Intent to start the Currency activity
                Intent intent = new Intent(MainActivity.this, Currency.class);
                // Start the Currency activity
                startActivity(intent);
            }
        });
    }
}
```

- **onCreate**: This method is called when the MainActivity is created. It sets the layout to `activity_main.xml`.
- **currencyButton**: The button in `activity_main.xml` is linked to this variable using `findViewById()`.
- **setOnClickListener**: This listens for clicks on the button. When the button is clicked, the app starts the `Currency` activity via an **Intent**.

#### `Currency.java` - Currency Conversion Logic

```java
package com.example.m1k057;

import android.os.Bundle;
import android.view.View;
import android.widget.AdapterView;
import android.widget.ArrayAdapter;
import android.widget.EditText;
import android.widget.Spinner;
import android.widget.TextView;
import androidx.appcompat.app.AppCompatActivity;

public class Currency extends AppCompatActivity {
	// declaring objects for all the entities defined in xml
    private EditText inputAmount;
    private Spinner currencySpinner;
    private TextView output;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.currency);

        // Initialize UI components
        inputAmount = findViewById(R.id.editTextNumberDecimal);
        currencySpinner = findViewById(R.id.spinner);
        output = findViewById(R.id.output);

        // Set up the currency spinner with available options from strings.xml
        ArrayAdapter<CharSequence> adapter = ArrayAdapter.createFromResource(this, R.array.currency, android.R.layout.simple_spinner_item);
        adapter.setDropDownViewResource(android.R.layout.simple_spinner_dropdown_item);
        currencySpinner.setAdapter(adapter);

        // Set up the spinner item selection listener
        currencySpinner.setOnItemSelectedListener(new AdapterView.OnItemSelectedListener() {
            @Override
            public void onItemSelected(AdapterView<?> parent, View view, int position, long id) {
                // When an item is selected, call convertCurrency
                convertCurrency();
            }

            @Override
            public void onNothingSelected(AdapterView<?> parent) {}
        });
    }

   
```
# Outputs
![[IMG-20250730000528547.png|300]]
![[IMG-20250730000532380.png]]

###### Information
- date: 2025.02.04
- time: 20:08
- Chat GPT'd my file for markdown