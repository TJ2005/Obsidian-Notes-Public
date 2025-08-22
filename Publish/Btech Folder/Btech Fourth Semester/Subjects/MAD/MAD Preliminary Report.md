---
Title: MAD Preliminary Report
Status: 
marker: 
tags: 
Date: 2025.01.27
Time: 19:43
---
# Title - COMMS
MPSTME - Mukesh Patel School Of Technology Management & Engineering
Department - BTECH CyberSecurity
Group Participants - 
- Tejas Sahoo K057
- Unnat Mishra K039
- Jay Desai

## Problem Statement:

There is a need for a simple and secure platform that allows users in environments like labs to transfer files from computers to phones without logging into formal systems like Teams, avoiding the creation of digital footprints.

## Project Brief Description:

COMMS is an Android-based application that facilitates secure, ephemeral communication and file transfer between devices. Users can join a temporary chat room by entering a unique code, enabling seamless file sharing. The app leverages an existing WebSocket-based server for real-time interactions and focuses on a minimalist, efficient design for quick usage.

## Project Features:

1. **Room-Based File Transfer:**
    
    - Users join a temporary room using a unique code.
    - Facilitates file sharing without leaving a trace.
2. **Random Username Generation:**
    
    - Automatically generates usernames if none are provided.
3. **Real-Time Communication and File Sharing:**
    
    - WebSocket-based infrastructure for fast, secure exchanges.
4. **Reusable Server Infrastructure:**
    
    - Utilizes an existing WebSocket server for scalability.
5. **Minimalist Design:**
    
    - Focused on quick and easy interactions.

## Android Topics/Libraries to be Used:

1. **WebSocket Integration:**
    
    - Using OkHttp or native WebSocket API for real-time functionality.
2. **Animations:**
    
    - MotionLayout for smooth transitions.
3. **Networking:**
    
    - Retrofit or OkHttp for backend communication (if necessary).
4. **UI/UX Design:**
    
    - Material Design principles for clean, accessible interfaces.
5. **State Management:**
    
    - ViewModel and LiveData for efficient state handling.
6. **Dependency Injection:**
    
    - Hilt for modular and testable code.

## Database Used:

**PostgreSQL:**

- Hosted on a personal VPS, PostgreSQL is used for its reliability and robust data handling.
- Ideal for real-time interactions with WebSockets.

## Additional Notes:

- Security and privacy are key priorities, ensuring no residual data is left after file transfers.
- The app’s lightweight design ensures quick load times and responsiveness for lab environments.
![[IMG-20250730000528576.svg]]

# Code

---

### 1. **MainActivity.java** (under `com.example.comms`)

```java
package com.example.comms;

import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

import com.example.comms.utils.CookieManager;
import com.example.comms.utils.NetworkUtils;
import com.example.comms.utils.RandomCodeGenerator;

import org.json.JSONObject;

import java.util.concurrent.CompletableFuture;

public class MainActivity extends AppCompatActivity {

    private EditText usernameInput, codeInput;
    private Button submitButton;
    private TextView errorMessage;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Initialize the views
        usernameInput = findViewById(R.id.usernameInput);
        codeInput = findViewById(R.id.code);
        submitButton = findViewById(R.id.loginButton);
        errorMessage = findViewById(R.id.errorMessage);

        // Set the submit button click listener
        submitButton.setOnClickListener(v -> handleSubmit());
    }

    private void handleSubmit() {
        // Get values from input fields
        String username = usernameInput.getText().toString().trim();
        String code = codeInput.getText().toString().trim();
        System.out.println("Username: " + username);
        System.out.println("Session Code: " + code);

        // Validate inputs
        if (username.isEmpty() || code.isEmpty()) {
            Toast.makeText(this, "Both fields are required", Toast.LENGTH_SHORT).show();
            return;
        }

        // If code is less than 6 characters, generate a new code
        if (code.length() < 6) {
            code = RandomCodeGenerator.generateAlphaCode();
            codeInput.setText(code);
            Toast.makeText(this, "Generated new session code: " + code, Toast.LENGTH_SHORT).show();
        }

        // Check if user already exists in cookies
        String userId = CookieManager.getUserId(this);

        if (userId != null) {
            // If user exists, join the session
            joinSession(userId, code);
        } else {
            // If user doesn't exist, create a new user and join the session
            createNewUserAndJoinSession(username, code);
        }
    }

    private void createNewUserAndJoinSession(final String username, final String code) {
        // Create a new user and join the session using CompletableFuture
        CompletableFuture<JSONObject> createUserFuture = NetworkUtils.createUser(username);

        createUserFuture.thenAccept(jsonResponse -> {
            try {
                String userId = jsonResponse.getString("userId"); // Extract userId from JSON response
                CookieManager.saveUserId(MainActivity.this, userId); // Save userId in cookies
                joinSession(userId, code);
            } catch (Exception e) {
                runOnUiThread(() -> Toast.makeText(MainActivity.this, "Error processing user creation response", Toast.LENGTH_SHORT).show());
            }
        }).exceptionally(ex -> {
            runOnUiThread(() -> Toast.makeText(MainActivity.this, "Error creating user", Toast.LENGTH_SHORT).show());
            return null;
        });
    }

    private void joinSession(String userId, String code) {
        // Join the session with the provided userId and session code using CompletableFuture
        CompletableFuture<NetworkUtils.NetworkResponse> joinSessionFuture = NetworkUtils.createOrJoinSession(userId, code);

        joinSessionFuture.thenAccept(jsonResponse -> {
            try {
                String sessionId = jsonResponse.getString("sessionId"); // Extract sessionId from response
                CookieManager.saveSessionId(MainActivity.this, sessionId);
                runOnUiThread(() -> {
                    Toast.makeText(MainActivity.this, "Session joined successfully", Toast.LENGTH_SHORT).show();
                    navigateToNextActivity();
                });
            } catch (Exception e) {
                runOnUiThread(() -> Toast.makeText(MainActivity.this, "Error processing session join response", Toast.LENGTH_SHORT).show());
            }
        }).exceptionally(ex -> {
            runOnUiThread(() -> Toast.makeText(MainActivity.this, "Error joining session", Toast.LENGTH_SHORT).show());
            return null;
        });
    }

    private void navigateToNextActivity() {
        // Navigate to the next activity (after joining the session)
        Intent intent = new Intent(MainActivity.this, ChatActivity.class);
        startActivity(intent);
        finish();
    }
}
```

---

### 2. **NetworkUtils.java** (under `com.example.comms.utils`)

```java
package com.example.comms.utils;

import okhttp3.OkHttpClient;
import okhttp3.Request;
import okhttp3.RequestBody;
import okhttp3.Response;
import okhttp3.MediaType;
import okhttp3.Call;

import org.json.JSONException;
import org.json.JSONObject;
import java.io.IOException;
import java.util.concurrent.CompletableFuture;

public class NetworkUtils {

    // Function to send a POST request for creating a new user and return a CompletableFuture
    public static CompletableFuture<JSONObject> createUser(String username) {
        CompletableFuture<NetworkResponse> future = new CompletableFuture<>();
        OkHttpClient client = new OkHttpClient();
        String jsonBody = "{\"username\":\"" + username + "\"}";
        RequestBody body = RequestBody.create(jsonBody, MediaType.parse("application/json"));
        Request request = new Request.Builder()
                .url("http://localhost:3000/api/newUser") // Replace with actual API URL
                .post(body)
                .build();

        client.newCall(request).enqueue(new okhttp3.Callback() {
            @Override
            public void onFailure(Call call, IOException e) {
                future.complete(new NetworkResponse(false, null, "Error creating user: " + e.getMessage()));
            }

            @Override
            public void onResponse(Call call, Response response) throws IOException {
                if (response.isSuccessful()) {
                    String jsonResponse = response.body().string();
                    JSONObject jsonObject = new JSONObject(jsonResponse);
                    future.complete(new NetworkResponse(true, jsonObject, null));
                } else {
                    future.complete(new NetworkResponse(false, null, "Error creating user, response code: " + response.code()));
                }
            }
        });

        return future; 
    }

    // Function to send a POST request to create or join a session and return a CompletableFuture
    public static CompletableFuture<NetworkResponse> createOrJoinSession(String userId, String sessionCode) {
        CompletableFuture<NetworkResponse> future = new CompletableFuture<>();
        OkHttpClient client = new OkHttpClient();
        String jsonBody = "{\"userId\":\"" + userId + "\", \"sessionCode\":\"" + sessionCode + "\"}";
        RequestBody body = RequestBody.create(jsonBody, MediaType.parse("application/json"));
        Request request = new Request.Builder()
                .url("http://localhost:3000/api/createOrJoinSession") // Replace with actual API URL
                .post(body)
                .build();

        client.newCall(request).enqueue(new okhttp3.Callback() {
            @Override
            public void onFailure(Call call, IOException e) {
                future.complete(new NetworkResponse(false, null, "Error creating or joining session: " + e.getMessage()));
            }

            @Override
            public void onResponse(Call call, Response response) throws IOException {
                if (response.isSuccessful()) {
                    String jsonResponse = response.body().string();
                    JSONObject jsonObject = new JSONObject(jsonResponse);
                    future.complete(new NetworkResponse(true, jsonObject, null));
                } else {
                    future.complete(new NetworkResponse(false, null, "Error creating or joining session, response code: " + response.code()));
                }
            }
        });

        return future; 
    }

    // Function to fetch a random username from the external API and return a CompletableFuture
    public static CompletableFuture<NetworkResponse> fetchRandomUsername() {
        CompletableFuture<NetworkResponse> future = new CompletableFuture<>();
        OkHttpClient client = new OkHttpClient();
        Request request = new Request.Builder()
                .url("https://usernameapiv1.vercel.app/api/random-usernames") 
                .build();

        client.newCall(request).enqueue(new okhttp3.Callback() {
            @Override
            public void onFailure(Call call, IOException e) {
                future.complete(new NetworkResponse(false, null, "Error fetching random username: " + e.getMessage()));
            }

            @Override
            public void onResponse(Call call, Response response) throws IOException {
                if (response.isSuccessful()) {
                    String jsonResponse = response.body().string();
                    JSONObject jsonObject = new JSONObject(jsonResponse);
                    future.complete(new NetworkResponse(true, jsonObject, null)); 
                } else {
                    future.complete(new NetworkResponse(false, null, "Error fetching random username, response code: " + response.code()));
                }
            }
        });

        return future;
    }

    // Utility class to hold network response data
    public static class NetworkResponse {
        private boolean success;
        private JSONObject response;
        private String errorMessage;

        public NetworkResponse(boolean success, JSONObject response, String errorMessage) {
            this.success = success;
            this.response = response;
            this.errorMessage = errorMessage;
        }

        public boolean isSuccess() {
            return success;
        }

        public JSONObject getResponse() {
            return response;
        }

        public String getErrorMessage() {
            return errorMessage;
        }
    }
}
```

---

### 3. **TextAnimationUtils.java** (under `com.example.comms.utils`)

```java
package com.example.comms.utils;

import android.os.Handler;
import android.widget.TextView;

public class TextAnimationUtils {

    public static void animateTyping(final TextView textView, final String fullText, final int typingDelay, final int completionDelay) {
        final Handler handler = new Handler();
        final StringBuilder typedText = new StringBuilder();
        int index = 0;

        Runnable typingRunnable = new Runnable() {
            @Override
            public void run() {
                if (index < fullText.length()) {
                    typedText.append(fullText.charAt(index));
                    textView.setText(typedText.toString());
                    index++;
                    handler.postDelayed(this, typingDelay);
                }
            }
        };

        handler.post(typingRunnable);
    }

    public static void animateBlinkingCursor(final TextView textView, final String fullText, final int blinkDelay) {
        final Handler handler = new Handler();
        final StringBuilder typedText = new StringBuilder(fullText);

        Runnable blinkRunnable = new Runnable() {
            @Override
            public void run() {
                typedText.append("_");
                textView.setText(typedText.toString());
                handler.postDelayed(this, blinkDelay);
            }
        };

        handler.post(blinkRunnable);
    }
}
```

---

### 4. **CookieManager.java** (under `com.example.comms.utils`)

```java
package com.example.comms.utils;

import android.content.Context;
import android.content.SharedPreferences;

public class CookieManager {

    private static final String PREF_NAME = "com.example.comms.preferences";
    private static final String USER_ID_KEY = "userId";
    private static final String SESSION_ID_KEY = "sessionId";

    // Save userId in SharedPreferences
    public static void saveUserId(Context context, String userId) {
        SharedPreferences preferences = context.getSharedPreferences(PREF_NAME, Context.MODE_PRIVATE);
        SharedPreferences.Editor editor = preferences.edit();
        editor.putString(USER_ID_KEY, userId);
        editor.apply();
    }

    // Retrieve userId from SharedPreferences
    public static String getUserId(Context context) {
        SharedPreferences preferences = context.getSharedPreferences(PREF_NAME, Context.MODE_PRIVATE);
        return preferences.getString(USER_ID_KEY, null);
    }

    // Save sessionId in SharedPreferences
    public static void saveSessionId(Context context, String sessionId) {
        SharedPreferences preferences = context.getSharedPreferences(PREF_NAME, Context.MODE_PRIVATE);
        SharedPreferences.Editor editor = preferences.edit();
        editor.putString(SESSION_ID_KEY, sessionId);
        editor.apply();
    }

    // Retrieve sessionId from SharedPreferences
    public static String getSessionId(Context context) {
        SharedPreferences preferences = context.getSharedPreferences(PREF_NAME, Context.MODE_PRIVATE);
        return preferences.getString(SESSION_ID_KEY, null);
    }
}
```

---

### 5. **RandomCodeGenerator.java** (under `com.example.comms.utils`)

```java
package com.example.comms.utils;

import java.util.Random;

public class RandomCodeGenerator {

    // Function to generate a random 6-character alphanumeric code
    public static String generateAlphaCode() {
        String characters = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789";
        StringBuilder code = new StringBuilder();
        Random rand = new Random();

        for (int i = 0; i < 6; i++) {
            int index = rand.nextInt(characters.length());
            code.append(characters.charAt(index));
        }
        return code.toString();
    }
}
```

---

# References


###### Information
- date: 2025.01.20
- time: 19:43