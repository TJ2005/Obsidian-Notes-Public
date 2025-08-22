---
Title: "Mobile Application Development Lab 5"
Status: 
marker: 
tags: 
Date: "2025.02.21"
Time: "14:23"
---
# Mobile Application Development Lab 4
	
## Activity_Main.xml
```xml
<?xml version="1.0" encoding="utf-8"?>  
<GridLayout xmlns:android="http://schemas.android.com/apk/res/android"  
    xmlns:app="http://schemas.android.com/apk/res-auto"  
    xmlns:tools="http://schemas.android.com/tools"  
    android:layout_width="match_parent"  
    android:layout_height="match_parent"  
    android:background="#EDE8E8"  
    android:columnCount="2"  
    android:padding="10dp"  
    android:rowCount="7"  
    tools:context=".MainActivity">  
  
    <Button        android:id="@+id/btn_add"  
        android:layout_width="100dp"  
        android:layout_height="wrap_content"  
        android:layout_row="4"  
        android:layout_column="0"  
        android:layout_marginLeft="@android:dimen/app_icon_size"  
        android:layout_marginTop="@android:dimen/app_icon_size"  
        android:onClick="add"  
        android:text="@string/e" />  
  
    <Button        android:id="@+id/btn_del"  
        android:layout_width="wrap_content"  
        android:layout_height="wrap_content"  
        android:layout_row="4"  
        android:layout_column="1"  
        android:layout_gravity="center_horizontal"  
        android:layout_marginTop="@android:dimen/app_icon_size"  
        android:onClick="delete"  
        android:text="@string/f" />  
  
    <Button        android:id="@+id/btn_mod"  
        android:layout_width="wrap_content"  
        android:layout_height="wrap_content"  
        android:layout_row="5"  
        android:layout_column="0"  
        android:layout_gravity="center_horizontal"  
        android:layout_marginLeft="@android:dimen/app_icon_size"  
        android:onClick="modify"  
        android:text="@string/g" />  
  
    <Button        android:id="@+id/btn_view"  
        android:layout_width="100dp"  
        android:layout_height="wrap_content"  
        android:layout_row="5"  
        android:layout_column="1"  
        android:layout_gravity="center_horizontal"  
        android:onClick="view"  
        android:text="@string/h" />  
  
    <Button        android:id="@+id/btn_viewall"  
        android:layout_width="wrap_content"  
        android:layout_height="wrap_content"  
        android:layout_row="6"  
        android:layout_column="0"  
        android:layout_columnSpan="2"  
        android:layout_gravity="center_horizontal"  
        android:layout_marginTop="@android:dimen/app_icon_size"  
        android:onClick="viewall"  
        android:text="@string/i" />  
  
    <EditText        android:id="@+id/txt_roll"  
        android:layout_width="100dp"  
        android:layout_height="wrap_content"  
        android:layout_row="1"  
        android:layout_column="1"  
        android:hint="" />  
  
    <EditText        android:id="@+id/name"  
        android:layout_width="100dp"  
        android:layout_height="wrap_content"  
        android:layout_row="2"  
        android:layout_column="1"  
        android:hint="" />  
  
    <EditText        android:id="@+id/marks"  
        android:layout_width="100dp"  
        android:layout_height="wrap_content"  
        android:layout_row="3"  
        android:layout_column="1"  
        android:hint="" />  
  
    <TextView        android:layout_width="wrap_content"  
        android:layout_height="wrap_content"  
        android:layout_row="0"  
        android:layout_column="0"  
        android:layout_columnSpan="2"  
        android:layout_gravity="center_horizontal"  
        android:text="@string/a" />  
  
    <TextView        android:layout_width="wrap_content"  
        android:layout_height="wrap_content"  
        android:layout_row="1"  
        android:layout_column="0"  
        android:text="@string/b" />  
  
    <TextView        android:layout_width="wrap_content"  
        android:layout_height="wrap_content"  
        android:layout_row="2"  
        android:layout_column="0"  
        android:text="@string/c" />  
  
    <TextView        android:layout_width="wrap_content"  
        android:layout_height="wrap_content"  
        android:layout_row="3"  
        android:layout_column="0"  
        android:text="@string/d" />  
</GridLayout>
```

## Strings.xml
```xml
<resources>  
    <string name="app_name">k057</string>  
    <string name="a">Student Details</string>  
    <string name="b">Enter Roll No</string>  
    <string name="c">Enter Name</string>  
    <string name="d">Enter Marks</string>  
    <string name="e">ADD</string>  
    <string name="f">DELETE</string>  
    <string name="g">MODIFY</string>  
    <string name="h">VIEW</string>  
    <string name="i">VIEW ALL</string>  
</resources>
```

## Main.java
```java
package com.example.lab5;  
  
import androidx.appcompat.app.AppCompatActivity;  
import androidx.appcompat.app.AlertDialog;  
import android.content.Context;  
import android.database.Cursor;  
import android.database.sqlite.SQLiteDatabase;  
import android.os.Bundle;  
import android.view.View;  
import android.widget.Button;  
import android.widget.EditText;  
public class MainActivity extends AppCompatActivity {  
  
    // Declare the variables for EditText and Buttons  
    EditText txtroll, txtname, txtmarks;  
    Button btnadd, btnmod, btnview, btndel, btnviewall;  
    SQLiteDatabase db; // Variable to handle the database operations  
  
    @Override  
    protected void onCreate(Bundle savedInstanceState) {  
        super.onCreate(savedInstanceState);  
        setContentView(R.layout.activity_main);  
  
        // Initialize the buttons and text fields by finding them in the layout  
        btnadd = findViewById(R.id.btn_add);  
        btndel = findViewById(R.id.btn_del);  
        btnmod = findViewById(R.id.btn_mod);  
        btnview = findViewById(R.id.btn_view);  
        btnviewall = findViewById(R.id.btn_viewall);  
        txtroll = findViewById(R.id.txt_roll);  
        txtname = findViewById(R.id.name);  
        txtmarks = findViewById(R.id.marks);  
  
        // Open or create the database called "Studentdb". If it doesn't exist, it will be created  
        db = openOrCreateDatabase("Studentdb", Context.MODE_PRIVATE, null);  
  
        // Create a table called "student" in the database, if it doesn't exist already.  
        db.execSQL("CREATE TABLE IF NOT EXISTS " +  
                "student(rollno text, name text, marks real);");  
    }  
  
    // This method adds a new record to the database  
    public void add(View v) {  
        if (check()) {  
            db.execSQL("insert into student values('"  
                    + txtroll.getText().toString() + "','"  
                    + txtname.getText().toString() + "',"  
                    + Float.parseFloat(txtmarks.getText().toString()) + ");");  
            showmsg("Added", "Record Saved");  
        }  
    }  
  
    // This method deletes a record from the database based on the roll number entered  
    public void delete(View v) {  
        if (txtroll.getText().toString().isEmpty()) {  
            showmsg("Error", "Roll no to be given");  
        } else {  
            Cursor c = db.rawQuery("select * from student where rollno='" + txtroll.getText().toString() + "';", null);  
            if (c.moveToFirst()) {  
                db.execSQL("delete from student where rollno='" + txtroll.getText().toString() + "';");  
                showmsg("Deleted", "Record deleted: " + txtroll.getText().toString());  
            } else {  
                showmsg("Error", txtroll.getText().toString() + " does not exist");  
            }  
        }  
    }  
  
    // This method checks if the input fields are not empty  
    public boolean check() {  
        if (txtroll.getText().toString().isEmpty() || txtname.getText().toString().isEmpty() || txtmarks.getText().toString().isEmpty()) {  
            showmsg("Error", "Fields cannot be blank");  
            return false;  
        } else {  
            return true;  
        }  
    }  
  
    // This method shows an alert dialog with the given title and message  
    public void showmsg(String title, String msg) {  
        AlertDialog.Builder builder = new AlertDialog.Builder(this);  
        builder.setTitle(title);  
        builder.setMessage(msg);  
        builder.show();  
    }  
  
    // This method displays all the records in the database  
    public void viewall(View v) {  
        Cursor c = db.rawQuery("select * from student;", null);  
        if (c.getCount() == 0) {  
            showmsg("Error", "Table empty");  
        } else {  
            StringBuffer buffer = new StringBuffer();  
            while (c.moveToNext()) {  
                buffer.append("Rollno: " + c.getString(0) + "\n");  
                buffer.append("Name: " + c.getString(1) + "\n");  
                buffer.append("Marks: " + c.getFloat(2) + "\n");  
                buffer.append("----------------\n");  
            }  
            showmsg("Records", buffer.toString());  
        }  
    }  
  
    // This method displays the record based on the roll number entered  
    public void view(View v) {  
        if (txtroll.getText().toString().isEmpty()) {  
            showmsg("Error", "Rollno cannot be blank");  
        } else {  
            Cursor c = db.rawQuery("select * from student where rollno='" + txtroll.getText().toString() + "';", null);  
            if (c.moveToFirst()) {  
                txtname.setText(c.getString(1));  
                txtmarks.setText(c.getString(2));  
            } else {  
                showmsg("Error", "Record does not exist");  
            }  
        }  
    }  
  
    // This method modifies an existing record in the database based on the roll number  
    public void modify(View v) {  
        if (check()) {  
            String rollno = txtroll.getText().toString();  
            String name = txtname.getText().toString();  
            float marks = Float.parseFloat(txtmarks.getText().toString());  
  
            // Check if a record with the given roll number exists  
            Cursor c = db.rawQuery("select * from student where rollno='" + rollno + "';", null);  
            if (c.moveToFirst()) {  
                // Update the existing record  
                db.execSQL("UPDATE student SET name='" + name + "', marks=" + marks + " WHERE rollno='" + rollno + "';");  
                showmsg("Updated", "Record updated successfully.");  
            } else {  
                // If no record is found with the given roll number, show an error message  
                showmsg("Error", "No record found with Roll No: " + rollno);  
            }  
        }  
    }  
}
```

# Output Screenshots
![[IMG-20250730000528598.png|300]]

# References


###### Information
- date: 2025.02.21
- time: 14:23