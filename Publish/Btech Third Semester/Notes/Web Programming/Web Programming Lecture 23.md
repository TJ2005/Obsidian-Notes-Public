---
Title: Web Programming Lecture 19
Status: 
marker:
  - "[[Web Programming]]"
  - "[[web development]]"
  - "[[networking]]"
  - "[[Modules in JS]]"
  - "[[Presentation]]"
tags: 
Date: 2024.09.23
Time: 11:18
---
### Web Programming - Lecture 19 Notes

#### Date: 2024.09.23  
#### Time: 11:18

---

### **Network Layers in Web Programming**

Web applications operate across several layers that work together to facilitate communication between users and servers. These layers are divided as follows:

#### 1. **Client Layer**:
   - This is the **front-end** layer, responsible for interacting with the user.
   - **Components**:
     - **Web Browser**: The traditional browser (e.g., Chrome, Firefox) used to access web applications.
     - **App**: Desktop or mobile apps that connect to the server for data.
     - **Mobile Browser**: Mobile-specific browsers that provide web-based access on smaller devices.

#### 2. **Server Layer**:
   - This is the **back-end** layer, responsible for handling user requests and delivering data.
   - **Components**:
     - **Web Server**: The server that handles HTTP requests, hosts the website, and serves files or responses (e.g., Apache, NGINX).

#### 3. **Business Layer**:
   - This layer handles the **logic** and **processing** of the application.
   - **Components**:
     - **Application Layer**: Processes business logic, handles requests, and executes the necessary operations. This could include frameworks such as Node.js, Django, etc.
     - **File System**: Manages files, directories, and data needed by the application. For example, it could store uploaded files or configuration data.

#### 4. **Data Layer**:
   - This layer is responsible for managing and storing data.
   - **Components**:
     - **Database**: The storage system that holds the application’s data (e.g., MySQL, MongoDB).
     - **External System**: Any external services or third-party APIs used by the application for additional data or services (e.g., a payment gateway or social media API).

---

### **Node.js**

Node.js is a powerful, open-source, server-side runtime environment built on Chrome's V8 JavaScript engine. It is commonly used for building scalable network applications. A significant feature of Node.js is its **event-driven, non-blocking I/O model**, which makes it lightweight and efficient.

#### **Modules in Node.js**

Node.js applications are composed of modules. These modules help in organizing the codebase and enable code reusability.

- **What is a Module?**  
  A module is a separate unit of code, essentially a file in Node.js that contains related functionality. Modules help in managing dependencies and maintaining a clean code structure.
  
- **Core Modules in Node.js**:
  Node.js comes with several built-in modules, such as:
  - `fs` (File System) for file operations.
  - `http` for creating web servers.
  - `path` for handling and transforming file paths.
  - `os` for accessing operating system information.

#### **HTTP Module in Node.js**

The **`http` module** in Node.js allows the creation of web servers that can listen for and respond to HTTP requests.

- **Creating a Server with `http` Module**:
  ```js
  const http = require('http');

  const server = http.createServer((req, res) => {
    res.statusCode = 200;
    res.setHeader('Content-Type', 'text/plain');
    res.end('Hello, World!\n');
  });

  server.listen(3000, () => {
    console.log('Server running at http://localhost:3000/');
  });
  ```
  - This code creates a basic HTTP server that listens on port 3000.
  - When accessed, it returns a "Hello, World!" message in plain text.

---

### **References**

- **Node.js Documentation**: [https://nodejs.org/en/docs/](https://nodejs.org/en/docs/)
- **Mozilla Developer Network (MDN) Web Docs**: [https://developer.mozilla.org/en-US/](https://developer.mozilla.org/en-US/)
- **HTTP Protocol Overview**: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview)
- **Web Development with Node.js**: [https://nodejs.dev/](https://nodejs.dev/)

---

### **Summary**

In this lecture, we covered the structure of web application layers, focusing on how different components interact across the client, server, business, and data layers. We also introduced **Node.js** as a runtime environment that supports server-side development using JavaScript and explored its **module** system, particularly focusing on the **`http` module** for creating basic servers.

