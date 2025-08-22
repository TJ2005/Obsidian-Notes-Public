---
Title: "Mobile Application Development Lab 5"
Status: 
marker: 
tags: 
Date: "2025.02.28"
Time: "14:35"
---
# Mobile Application Development Lab 5

## `Activity_main.xml`
```xml
<?xml version="1.0" encoding="utf-8"?>  
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"  
    android:layout_width="match_parent"  
    android:layout_height="match_parent"  
    android:orientation="vertical"  
    android:padding="16dp"  
    android:gravity="center">  
  
    <EditText        android:id="@+id/username"  
        android:layout_width="match_parent"  
        android:layout_height="wrap_content"  
        android:hint="Username"  
        android:inputType="text" />  
  
    <EditText        android:id="@+id/password"  
        android:layout_width="match_parent"  
        android:layout_height="wrap_content"  
        android:hint="Password"  
        android:inputType="textPassword" />  
  
    <Button        android:id="@+id/login_button"  
        android:layout_width="wrap_content"  
        android:layout_height="wrap_content"  
        android:text="Login" />  
</LinearLayout>
```

## `mainactivity.java`
```java
package com.example.lab5;  
  
import android.content.Intent;  
import android.os.Bundle;  
import android.view.View;  
import android.widget.Button;  
import android.widget.EditText;  
import android.widget.Toast;  
import androidx.appcompat.app.AppCompatActivity;  
  
public class MainActivity extends AppCompatActivity {  
  
    private EditText usernameEditText, passwordEditText;  
    private Button loginButton;  
  
    private static final String CORRECT_USERNAME = "user";  
    private static final String CORRECT_PASSWORD = "password";  
  
    @Override  
    protected void onCreate(Bundle savedInstanceState) {  
        super.onCreate(savedInstanceState);  
        setContentView(R.layout.activity_main);  
  
        usernameEditText = findViewById(R.id.username);  
        passwordEditText = findViewById(R.id.password);  
        loginButton = findViewById(R.id.login_button);  
  
        loginButton.setOnClickListener(new View.OnClickListener() {  
            @Override  
            public void onClick(View v) {  
                String username = usernameEditText.getText().toString();  
                String password = passwordEditText.getText().toString();  
  
                if (username.equals(CORRECT_USERNAME) && password.equals(CORRECT_PASSWORD)) {  
                    Intent intent = new Intent(MainActivity.this, SecondActivity.class);  
                    intent.putExtra("username", username);  
                    intent.putExtra("password", password);  
                    startActivity(intent);  
                } else {  
                    Toast.makeText(MainActivity.this, "Invalid username or password!", Toast.LENGTH_SHORT).show();  
                }  
            }  
        });  
    }  
}
```

## `secondActivity.java`
```java
package com.example.lab5;  
  
import android.content.Intent;  
import android.os.Bundle;  
import android.view.View;  
import android.widget.AdapterView;  
import android.widget.ArrayAdapter;  
import android.widget.Button;  
import android.widget.LinearLayout;  
import android.widget.Spinner;  
import android.widget.TextView;  
import android.widget.Toast;  
import androidx.appcompat.app.AppCompatActivity;  
  
public class SecondActivity extends AppCompatActivity {  
  
    @Override  
    protected void onCreate(Bundle savedInstanceState) {  
        super.onCreate(savedInstanceState);  
        // Use Linear Layout class for creating linear layout  
        LinearLayout secondLayout = new LinearLayout(this);  
        // Change Parameter to Vertical  
        secondLayout.setOrientation(LinearLayout.VERTICAL);  
        secondLayout.setPadding(16, 16, 16, 16);  
  
        // get the intent parameters passed from previous  
        Intent intent = getIntent();  
        String username = intent.getStringExtra("username");  
        String password = intent.getStringExtra("password");  
  
        // Create a TextView dynamically to display username and password  
        TextView welcomeText = new TextView(this);  
        welcomeText.setText("Welcome " + username);  
        welcomeText.setTextSize(18);  
        welcomeText.setPadding(0, 0, 0, 20);  
  
        // Create a Spinner dynamically for color selection  
        Spinner colorSpinner = new Spinner(this);  
        String[] colors = {"RED", "GREEN", "BLUE", "YELLOW", "WHITE"};  
        ArrayAdapter<String> adapter = new ArrayAdapter<>(this, android.R.layout.simple_spinner_item, colors);  
        adapter.setDropDownViewResource(android.R.layout.simple_spinner_dropdown_item);  
        colorSpinner.setAdapter(adapter);  
  
        // Set listener for color selection  
        colorSpinner.setOnItemSelectedListener(new AdapterView.OnItemSelectedListener() {  
            @Override  
            public void onItemSelected(AdapterView<?> parentView, View selectedItemView, int position, long id) {  
                String selectedColor = parentView.getItemAtPosition(position).toString();  
  
                // Change the background color based on the selected color  
                switch (selectedColor) {  
                    case "RED":  
                        secondLayout.setBackgroundColor(getResources().getColor(android.R.color.holo_red_dark));  
                        break;  
                    case "GREEN":  
                        secondLayout.setBackgroundColor(getResources().getColor(android.R.color.holo_green_dark));  
                        break;  
                    case "BLUE":  
                        secondLayout.setBackgroundColor(getResources().getColor(android.R.color.holo_blue_dark));  
                        break;  
                    case "YELLOW":  
                        secondLayout.setBackgroundColor(getResources().getColor(android.R.color.holo_orange_light));  
                        break;  
                    case "WHITE":  
                        secondLayout.setBackgroundColor(getResources().getColor(android.R.color.white));  
                        break;  
                }  
            }  
  
            @Override  
            public void onNothingSelected(AdapterView<?> parentView) {  
                // Do nothing  
            }  
        });  
  
        // Create a Button dynamically to go back to MainActivity  
        Button backButton = new Button(this);  
        backButton.setText("Go Back");  
        backButton.setOnClickListener(new View.OnClickListener() {  
            @Override  
            public void onClick(View v) {  
                // Start MainActivity and finish SecondActivity  
                Intent intent = new Intent(SecondActivity.this, MainActivity.class);  
                startActivity(intent);  
                finish();  
            }  
        });  
  
        // Add views to the layout  
        secondLayout.addView(welcomeText);  
        secondLayout.addView(colorSpinner);  
        secondLayout.addView(backButton);  
  
        // Set the dynamic layout as the content view  
        setContentView(secondLayout);  
    }  
}
```


<div style="display: flex; flex-direction: row; height: 40em; gap:1em; justify-content:center">
  <img src="https://i.imgur.com/LW5xlvZ.png" style="height: 100%; object-fit: cover;">
  <img src="https://i.imgur.com/XvoLReO.png" style="height: 100%; object-fit: cover;">
</div>




# References


###### Information
- date: 2025.02.28
- time: 14:35