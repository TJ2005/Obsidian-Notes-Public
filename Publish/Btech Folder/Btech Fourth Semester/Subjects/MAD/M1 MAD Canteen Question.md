---
Title: M1 MAD Canteen Question
Status: 
marker:
  - "[[Exam Solution]]"
  - "[[Mobile Application Development (MAD)]]"
tags: 
Date: 2025.02.04
Time: 20:41
---
# M1 MAD Canteen Question

### Program Overview:

This Android application simulates the process of ordering food from a canteen, where the user can select different food items and beverages, choose a dining option (Dine-In or Take Away), and calculate the total bill. Additionally, the app includes a feedback button that redirects users to a website for reviews.

### Layout Design:

The layout consists of several components to facilitate user interaction:

1. **TextViews**:
    
    - The first `TextView` displays the title ("MPSTME Canteen").
    - The second `TextView` provides a subtitle ("Today's Breakfast Menu").
2. **RadioGroup**:
    
    - Contains two `RadioButton` options ("Dine IN" and "Take Away"), allowing the user to select their preferred dining option.
3. **CheckBoxes**:
    
    - For selecting food and beverages, including Tea, Coffee, Poha/Upma, Idli/Dosa, and Sandwich. The prices for these items are displayed alongside the options.
4. **Buttons**:
    
    - A "Bill" button calculates the total based on selected items and dining option.
    - A "Feedback" button redirects to a restaurant review site.

### Code Breakdown:

#### **activity_main.xml**:

This XML file defines the user interface components:

- **RadioGroup**: Handles the dine-in or take-away option.
- **CheckBoxes**: Represent food and beverage items with associated prices.
- **Buttons**: "Bill" for calculating the total and "Feedback" for opening a feedback page.

```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="16dp"
    android:gravity="center"
    tools:context=".MainActivity">

    <!-- Title TextView -->
    <TextView android:id="@+id/title" android:layout_width="wrap_content" android:layout_height="wrap_content" 
        android:text="MPSTME Canteen" android:textSize="24sp" android:textStyle="bold" android:gravity="center" 
        android:layout_marginBottom="10dp"/>

    <!-- Subtitle TextView -->
    <TextView android:id="@+id/subtitle" android:layout_width="wrap_content" android:layout_height="wrap_content" 
        android:text="Today's Breakfast Menu" android:textSize="18sp" android:layout_marginBottom="10dp"/>

    <!-- Dine-in / Take-away RadioGroup -->
    <RadioGroup android:id="@+id/dineOption" android:layout_width="wrap_content" android:layout_height="wrap_content" 
        android:orientation="horizontal" android:layout_marginBottom="10dp">
        <RadioButton android:id="@+id/dineIn" android:text="Dine IN" android:checked="true"/>
        <RadioButton android:id="@+id/takeAway" android:text="Take Away"/>
    </RadioGroup>

    <!-- Food and beverage checkboxes -->
    <CheckBox android:id="@+id/tea" android:text="Tea (Rs20)"/>
    <CheckBox android:id="@+id/coffee" android:text="Coffee (Rs20)"/>
    <CheckBox android:id="@+id/pohaUpma" android:text="Poha/Upma (Rs40)"/>
    <CheckBox android:id="@+id/idliDosa" android:text="Idli/Dosa (Rs60)"/>
    <CheckBox android:id="@+id/sandwich" android:text="Sandwich (Rs100)"/>

    <!-- Buttons -->
    <Button android:id="@+id/billButton" android:text="Bill" android:onClick="calculateBill"/>
    <Button android:id="@+id/feedbackButton" android:text="Feedback" android:onClick="openFeedback"/>
</LinearLayout>
```

#### **MainActivity.java**:

The logic for calculating the bill and opening the feedback link is handled in this file.

- **Bill Calculation**: Based on the checkboxes and radio button selection, the total bill is calculated. If the "Take Away" option is selected, an additional charge is added to the total.

```java
public class MainActivity extends AppCompatActivity {
    private CheckBox tea, coffee, pohaUpma, idliDosa, sandwich;
    private RadioGroup dineOption;
    private RadioButton takeAway;
    private Button billButton, feedbackButton;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        // Get Declared elements from the activity sheet just like you do in java script
        tea = findViewById(R.id.tea);
        coffee = findViewById(R.id.coffee);
        pohaUpma = findViewById(R.id.pohaUpma);
        idliDosa = findViewById(R.id.idliDosa);
        sandwich = findViewById(R.id.sandwich);

        dineOption = findViewById(R.id.dineOption);
        takeAway = findViewById(R.id.takeAway);
        billButton = findViewById(R.id.billButton);
        feedbackButton = findViewById(R.id.feedbackButton);
    }

    public void calculateBill(View view) {
        int total = 0;
        // Since tea is an checkbox object it has a isChecked method.
        // Expected Return of method isChecked = Boolean
        // Add the values as per requirement


        if (tea.isChecked()) total += 20;
        if (coffee.isChecked()) total += 20;
        if (pohaUpma.isChecked()) total += 40;
        if (idliDosa.isChecked()) total += 60;
        if (sandwich.isChecked()) total += 100;

        if (takeAway.isChecked()) {
            total += 20;
        }
		// I dont know if toast is taught but this is chat gpt'd code as i didnt have this question.
        Toast.makeText(this, "Total Bill: ₹" + total, Toast.LENGTH_LONG).show();
    }

    public void openFeedback(View view) {
	  - // parse uri to access server??
        Intent browserIntent = new Intent(Intent.ACTION_VIEW, Uri.parse("https://restaurant-guru.in/GR-Jani-Canteen-Mumbai"));
        startActivity(browserIntent);
    }
}
```

#### **AndroidManifest.xml**:

This configuration file ensures the app has internet permissions for accessing the feedback page.

```xml
<manifest xmlns:android="http://schemas.android.com/apk/res/android">
    <uses-permission android:name="android.permission.INTERNET"/>
    <application android:allowBackup="true" android:icon="@mipmap/ic_launcher" android:label="@string/app_name">
        <activity android:name=".MainActivity" android:exported="true">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>
</manifest>
```

### Output:

- **After Clicking Bill (Dine In)**: The total bill is calculated based on selected items, and a message displays the total.
- **After Clicking Bill (Take Away)**: If "Take Away" is selected, a ₹20 additional charge is added to the bill.
- **After Clicking Feedback**: Redirects the user to a restaurant review page for providing feedback.

### Conclusion:

This app efficiently handles food order selection, bill calculation, and provides a convenient way for users to give feedback via an external link.

![[IMG-20250730000528538.png]]
# References


###### Information
- date: 2025.02.04
- time: 20:41