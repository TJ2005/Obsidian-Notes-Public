---
Title: Mobile Application Development Lab 4
Status: 
marker:
  - "[[Java]]"
tags: 
Date: 2025.02.20
Time: 09:31
---
# Activity Main.xml
```xml

```
# Main Activity.java
```java
package com.example.multiview;  
  
import android.content.Intent;  
import android.os.Bundle;  
import android.view.View;  
import android.widget.LinearLayout;  
  
import androidx.appcompat.app.AppCompatActivity;  
  
public class MainActivity extends AppCompatActivity {  
  
    LinearLayout ll;  
  
    @Override  
    protected void onCreate(Bundle savedInstanceState) {  
        super.onCreate(savedInstanceState);  
        setContentView(R.layout.activity_main);  
  
        ll = findViewById(R.id.lay_wel);  
        ll.setOnClickListener(new View.OnClickListener() {  
            @Override  
            public void onClick(View v) {  
                startActivity(new Intent(MainActivity.this, SecondActivity.class));  
            }  
        });  
    }  
}
```
# Second Activity.xml
```xml
<?xml version="1.0" encoding="utf-8"?>  
<LinearLayout  
    xmlns:android="http://schemas.android.com/apk/res/android"  
    xmlns:app="http://schemas.android.com/apk/res-auto"  
    xmlns:tools="http://schemas.android.com/tools"  
    android:orientation="vertical"  
    android:weightSum="10"  
    android:id="@+id/lay_wel"  
    android:padding="15dp"  
    android:gravity="center_horizontal"  
    android:background="@color/white"  
    android:layout_width="match_parent"  
    android:layout_height="match_parent"  
    tools:context=".SecondActivity">  
  
  
  
        <ImageView            android:layout_width="match_parent"  
            android:layout_height="wrap_content"  
            android:src="@drawable/nm"  
            android:layout_weight="2"  
            />  
        <ListView            android:layout_width="match_parent"  
            android:layout_height="match_parent"  
            android:layout_weight="2"  
            android:id="@+id/lv_dt"  
  
            />  
</LinearLayout>
```

# Second Activity.xml
```java
package com.example.multiview;  
  
import android.content.Intent;  
import android.net.Uri;  
import android.os.Bundle;  
import android.text.util.Linkify;  
import android.view.View;  
import android.widget.AdapterView;  
import android.widget.ArrayAdapter;  
import android.widget.ListView;  
import android.widget.TextView;  
  
import androidx.appcompat.app.AppCompatActivity;  
  
public class SecondActivity extends AppCompatActivity {  
    ListView lvdt;  
  
    @Override  
    protected void onCreate(Bundle savedInstanceState) {  
        super.onCreate(savedInstanceState);  
        setContentView(R.layout.activity_second);  
  
        lvdt = findViewById(R.id.lv_dt);  
  
        String[] menuItems = getResources().getStringArray(R.array.menu_items);  
        ArrayAdapter<String> adapter = new ArrayAdapter<>(this, android.R.layout.simple_list_item_1, menuItems);  
        lvdt.setAdapter(adapter);  
  
        lvdt.setOnItemClickListener(new AdapterView.OnItemClickListener() {  
            @Override  
            public void onItemClick(AdapterView<?> parent, View view, int position, long id) {  
                TextView tv = (TextView) view;  
                String str = tv.getText().toString();  
                switch (position) {  
                    case 0:  
                        // Handle Name click  
                        // Open a third activity to show the person's photo                        Intent intent = new Intent(SecondActivity.this, ThirdActivity.class);  
                        startActivity(intent);  
                        break;  
                    case 1:  
                        // Handle Phone Number click  
                        str = "tel:" + str;  
                        startActivity(new Intent(Intent.ACTION_DIAL, Uri.parse(str)));  
                        break;  
                    case 2:  
                        // Handle Email Address click  
                        Linkify.addLinks(tv, Linkify.EMAIL_ADDRESSES);  
                        break;  
                    case 3:  
                        // Open Google Search  
                        startActivity(new Intent(Intent.ACTION_VIEW, Uri.parse("https://www.google.com")));  
                        break;  
                    case 4:  
                        // Open Android Tutorial Website  
                        startActivity(new Intent(Intent.ACTION_VIEW, Uri.parse("https://developer.android.com")));  
                        break;  
                }  
            }  
        });  
    }  
}
```

# Third.xml
```xml
<?xml version="1.0" encoding="utf-8"?>  
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"  
    android:orientation="vertical"  
    android:layout_width="match_parent"  
    android:layout_height="match_parent"  
    android:gravity="center">  
  
    <ImageView  
        android:id="@+id/person_image"  
        android:layout_width="wrap_content"  
        android:layout_height="wrap_content"  
        android:src="@drawable/user" />  
</LinearLayout>
```
# Third Java
```java
package com.example.multiview;  
  
import android.os.Bundle;  
  
import androidx.appcompat.app.AppCompatActivity;  
import android.widget.ImageView;  
  
public class ThirdActivity extends AppCompatActivity {  
  
    ImageView personImage;  
  
    @Override  
    protected void onCreate(Bundle savedInstanceState) {  
        super.onCreate(savedInstanceState);  
        setContentView(R.layout.activity_third);  
  
        personImage = findViewById(R.id.person_image);  
        // Set the image for the person (replace with actual drawable)  
        personImage.setImageResource(R.drawable.user);  
    }  
}
```

# Outputs


![[IMG-20250730000528628.png]]
![[IMG-20250730000536642.png]]
![[IMG-20250730000559476.png]]
