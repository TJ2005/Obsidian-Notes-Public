---
Title: "Mobile Application Development Lab 6"
Status: 
marker: 
tags: 
Date: "2025.03.12"
Time: "08:12"
---




# Submission: `Batch_k057_Exp_No`

## `activity_main.xml`

```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/myLayout"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <Spinner
        android:id="@+id/spn_color"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:entries="@array/colors" />

    <Button
        android:id="@+id/btn_clear"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="CLEAR" />
</LinearLayout>
```

---

## `MainActivity.java`

```java
package com.example.k057;

import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.AdapterView;
import android.widget.Button;
import android.widget.LinearLayout;
import android.widget.Spinner;

public class MainActivity extends AppCompatActivity {
    Button btnclear;
    Spinner spncolor;
    TouchScreen ts;
    LinearLayout my_layout;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        btnclear = findViewById(R.id.btn_clear);
        spncolor = findViewById(R.id.spn_color);
        my_layout = findViewById(R.id.myLayout);

        ts = new TouchScreen(this, null);
        my_layout.addView(ts);

        btnclear.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                ts.clearCanvas();
            }
        });

        spncolor.setOnItemSelectedListener(new AdapterView.OnItemSelectedListener() {
            @Override
            public void onItemSelected(AdapterView<?> adapterView, View view, int i, long l) {
                ts.changeColor(String.valueOf(spncolor.getSelectedItem()));
            }

            @Override
            public void onNothingSelected(AdapterView<?> parent) { }
        });
    }
}
```

---

## `TouchScreen.java`

```java
package com.example.k057;

import android.content.Context;
import android.graphics.Canvas;
import android.graphics.Color;
import android.graphics.Paint;
import android.graphics.Path;
import android.util.AttributeSet;
import android.view.MotionEvent;
import android.view.View;

public class TouchScreen extends View {
    Paint myPaint;
    Path myPath;

    public TouchScreen(Context context, AttributeSet attrs) {
        super(context, attrs);
        myPaint = new Paint();
        myPath = new Path();
        myPaint.setColor(Color.BLACK);
        myPaint.setStyle(Paint.Style.STROKE);
        myPaint.setStrokeWidth(6f);
        myPaint.setStrokeJoin(Paint.Join.ROUND);
    }

    public void clearCanvas() {
        invalidate();
        myPath.reset();
    }

    public void changeColor(String str) {
        myPaint.setColor(Color.parseColor(str));
    }

    @Override
    public boolean onTouchEvent(MotionEvent event) {
        float event_x = event.getX();
        float event_y = event.getY();

        switch (event.getAction()) {
            case MotionEvent.ACTION_DOWN:
                myPath.moveTo(event_x, event_y);
                return true;
            case MotionEvent.ACTION_MOVE:
                myPath.lineTo(event_x, event_y);
                break;
            case MotionEvent.ACTION_UP:
                break;
            default:
                return false;
        }
        invalidate();
        return super.onTouchEvent(event);
    }

    @Override
    protected void onDraw(Canvas canvas) {
        super.onDraw(canvas);
        canvas.drawPath(myPath, myPaint);
    }
}
```

---

## `strings.xml`

```xml
<resources>
    <string name="app_name">k057</string>
    <string-array name="colors">
        <item>RED</item>
        <item>GREEN</item>
        <item>YELLOW</item>
        <item>BLUE</item>
    </string-array>
</resources>
```

### output
![](https://i.imgur.com/NhgGJuO.png)
