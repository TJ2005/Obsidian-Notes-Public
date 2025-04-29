---
Title: Computer Networks Lab 3
Status: 
marker:
  - "[[btech]]"
tags:
  - BTech
Date: 2024.07.29
Time: 10:23
---
 Computer Networks Lab 3
# Index

1. **Main note**
    - [Lab Experiment: Implementing TCP Server and Client in C](#lab-experiment-implementing-tcp-server-and-client-in-c)
2. **Objective**
    - [Objective](#objective)
3. **Materials and Equipment**
    - [Materials and Equipment](#materials-and-equipment)
4. **Procedure**
    - [Procedure](#procedure)
    1. [Setting up the TCP Server](#1-setting-up-the-tcp-server)
        - [Code: TCPServer.c](#code-tcpserverc)
    2. [Setting up the TCP Client](#2-setting-up-the-tcp-client)
        - [Code: TCPClient.c](#code-tcpclientc)
    3. [Steps](#steps)
        - [Compiling the Server and Client Programs](#compile-the-server-and-client-programs)
        - [Running the Server](#run-the-server)
        - [Running the Client](#run-the-client)
    4. [Expected Output](#expected-output)
        - [Server Side Example Output](#server-side-example-output)
        - [Client Side Example Output](#client-side-example-output)
5. **Conclusion**
    - [Conclusion](#conclusion)
6. **References**
    - [References](#references)

# Main note

## Lab Experiment: Implementing TCP Server and Client in C

### Objective
The objective of this lab experiment is to create a TCP server and a TCP client using C language. The client will send a message to the server, which will receive, display, and send the message back to the client.

### Materials and Equipment
- A computer with a C compiler installed (e.g., GCC).
- Basic knowledge of C programming and networking concepts.

### Procedure

#### 1. Setting up the TCP Server

**Code: TCPServer.c**
```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <unistd.h>
#include <arpa/inet.h>

#define PORT 8080
#define BUFFER_SIZE 1024

int main() {
    int server_fd, new_socket;
    struct sockaddr_in address;
    int addrlen = sizeof(address);
    char buffer[BUFFER_SIZE] = {0};
    
    // Creating socket file descriptor
    if ((server_fd = socket(AF_INET, SOCK_STREAM, 0)) == 0) {
        perror("Socket failed");
        exit(EXIT_FAILURE);
    }

    // Forcefully attaching socket to the port 8080
    address.sin_family = AF_INET;
    address.sin_addr.s_addr = INADDR_ANY;
    address.sin_port = htons(PORT);

    if (bind(server_fd, (struct sockaddr *)&address, sizeof(address)) < 0) {
        perror("Bind failed");
        close(server_fd);
        exit(EXIT_FAILURE);
    }
    if (listen(server_fd, 3) < 0) {
        perror("Listen failed");
        close(server_fd);
        exit(EXIT_FAILURE);
    }
    if ((new_socket = accept(server_fd, (struct sockaddr *)&address, (socklen_t*)&addrlen)) < 0) {
        perror("Accept failed");
        close(server_fd);
        exit(EXIT_FAILURE);
    }
    read(new_socket, buffer, BUFFER_SIZE);
    printf("Message received: %s\n", buffer);
    send(new_socket, buffer, strlen(buffer), 0);
    printf("Message sent: %s\n", buffer);

    close(new_socket);
    close(server_fd);
    return 0;
}
```

#### 2. Setting up the TCP Client

**Code: TCPClient.c**
```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <unistd.h>
#include <arpa/inet.h>

#define PORT 8080
#define BUFFER_SIZE 1024

int main() {
    int sock = 0;
    struct sockaddr_in serv_addr;
    char *hello = "Hello from client";
    char buffer[BUFFER_SIZE] = {0};

    if ((sock = socket(AF_INET, SOCK_STREAM, 0)) < 0) {
        printf("\n Socket creation error \n");
        return -1;
    }

    serv_addr.sin_family = AF_INET;
    serv_addr.sin_port = htons(PORT);

    if (inet_pton(AF_INET, "127.0.0.1", &serv_addr.sin_addr) <= 0) {
        printf("\nInvalid address/ Address not supported \n");
        return -1;
    }

    if (connect(sock, (struct sockaddr *)&serv_addr, sizeof(serv_addr)) < 0) {
        printf("\nConnection Failed \n");
        return -1;
    }
    send(sock, hello, strlen(hello), 0);
    printf("Message sent: %s\n", hello);
    read(sock, buffer, BUFFER_SIZE);
    printf("Message received: %s\n", buffer);

    close(sock);
    return 0;
}
```

### Steps

1. **Compile the Server and Client Programs**
   ```sh
   gcc TCPServer.c -o TCPServer
   gcc TCPClient.c -o TCPClient
   ```

2. **Run the Server**
   ```sh
   ./TCPServer
   ```

3. **Run the Client**
   ```sh
   ./TCPClient
   ```

### Expected Output

- When the client sends a message, the server will receive and display the message.
- The server will then send the same message back to the client.
- The client will display the received message.

**Example Output:**

*Server Side:*
```
Message received: Hello from client
Message sent: Hello from client
```

*Client Side:*
```
Message sent: Hello from client
Message received: Hello from client
```

### Conclusion

In this lab experiment, we successfully implemented a TCP server and client in C. The client sends a message to the server, which then displays and sends the message back to the client. This experiment demonstrates the basics of socket programming and inter-process communication over a network.

### References
- [Beej's Guide to Network Programming](https://beej.us/guide/bgnet/)
- [TCP/IP Sockets in C: Practical Guide for Programmers](https://www.amazon.com/TCP-Sockets-Practical-Programmers-Morgan/dp/0123745403)

# References


###### Information
- date: 2024.07.29
- time: 10:23](<## Lab Experiment: Implementing TCP Server and Client in C