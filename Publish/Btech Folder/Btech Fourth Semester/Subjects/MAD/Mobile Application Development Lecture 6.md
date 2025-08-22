---
Title: "Mobile Application Development Lecture 6"
Status: 
marker: 
tags: 
Date: "2025.03.24"
Time: "11:30"
---
# Mobile Application Development Lecture 6

```java
import android.os.Bundle;

import android.app.Activity;

import android.view.ContextMenu;

import android.view.ContextMenu.ContextMenuInfo;

import android.view.Menu;

import android.view.MenuItem;

import android.view.View;

import android.widget.AdapterView;

import android.widget.ArrayAdapter;

import android.widget.ListView;

import android.widget.Toast;

  

public class MainActivity extends Activity {

  

    ListView listView1;

    String places[] = {"Place1", "Place2", "Place3"};

  

    @Override

    protected void onCreate(Bundle savedInstanceState) {

        super.onCreate(savedInstanceState);

        setContentView(R.layout.activity_main);

  

        listView1 = (ListView) findViewById(R.id.listView1);

  

        ArrayAdapter<String> adapter = new ArrayAdapter<String>(this, android.R.layout.simple_list_item_1, places);

        listView1.setAdapter(adapter);

  

        // Register the ListView for Context menu

        registerForContextMenu(listView1);

    }

  

    @Override

    public void onCreateContextMenu(ContextMenu menu, View v, ContextMenuInfo menuInfo) {

        super.onCreateContextMenu(menu, v, menuInfo);

        menu.setHeaderTitle("Select The Action");

        //groupId, itemId, order, title

        menu.add(0, v.getId(), 0, "Call");

        menu.add(0, v.getId(), 1, "SMS");

        menu.add(0, v.getId(), 2, "Email");

    }

  

    @Override

    public boolean onContextItemSelected(MenuItem item) {

        if (item.getTitle() == "Call") {

            Toast.makeText(getApplicationContext(), "Calling...", Toast.LENGTH_LONG).show();

        } else if (item.getTitle() == "SMS") {

            Toast.makeText(getApplicationContext(), "Sending SMS...", Toast.LENGTH_LONG).show();

        } else if (item.getTitle() == "Email") {

            Toast.makeText(getApplicationContext(), "Sending Email...", Toast.LENGTH_LONG).show();

        } else {

            return false;

        }

        return true;

    }

}
```

```xml
<?xml version="1.0" encoding="utf-8"?>

  

<menu xmlns:android="http://schemas.android.com/apk/res/android">

  

    <item android:id="@+id/item1"

          android:title="Item 1" />

  

    <item android:id="@+id/item2"

          android:title="Item 2" />

  

    <item android:id="@+id/item3"

          android:title="Item 3" />

  

</menu>
```



# References


###### Information
- date: 2025.03.24
- time: 11:30