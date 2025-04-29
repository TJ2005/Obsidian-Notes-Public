---
Title: Computer Networking Lecture 4
Status: true
marker: 
tags: 
Date: 2024-07-23
Time: 12:13
---
# Index
- [OSI Reference Model (Open System Interconnection)](#osi-reference-model-open-system-interconnection)
- [The Seven Layers of the OSI Model](#the-seven-layers-of-the-osi-model)
  - [Physical Layer (Layer 1)](#physical-layer-layer-1)
  - [Data Link Layer (Layer 2)](#data-link-layer-layer-2)
  - [Network Layer (Layer 3)](#network-layer-layer-3)
  - [Transport Layer (Layer 4)](#transport-layer-layer-4)
  - [Session Layer (Layer 5)](#session-layer-layer-5)
  - [Presentation Layer (Layer 6)](#presentation-layer-layer-6)
  - [Application Layer (Layer 7)](#application-layer-layer-7)
- [Importance of the OSI Model](#importance-of-the-osi-model)
- [TCP/IP Reference Model](#tcpip-reference-model)
- [Layers of the TCP/IP Reference Model](#layers-of-the-tcpip-reference-model)
  - [Network Interface Layer (Link Layer)](#network-interface-layer-link-layer)
  - [Internet Layer](#internet-layer)
  - [Transport Layer](#transport-layer)
  - [Application Layer](#application-layer)
- [Comparison with OSI Model](#comparison-with-osi-model)
- [Key Protocols and Their Functions](#key-protocols-and-their-functions)
  - [IP (Internet Protocol)](#ip-internet-protocol)
  - [TCP (Transmission Control Protocol)](#tcp-transmission-control-protocol)
  - [UDP (User Datagram Protocol)](#udp-user-datagram-protocol)
  - [HTTP (HyperText Transfer Protocol)](#http-hypertext-transfer-protocol)
  - [FTP (File Transfer Protocol)](#ftp-file-transfer-protocol)
  - [SMTP (Simple Mail Transfer Protocol)](#smtp-simple-mail-transfer-protocol)
  - [DNS (Domain Name System)](#dns-domain-name-system)
- [Importance of the TCP/IP Model](#importance-of-the-tcpip-model)
- [Private Public Ports etc](#private-public-ports-etc)
- [Sockets](#sockets)
- [Ports](#ports)
- [HTTP/S](#https)
- [Communication](#communication)
- [Layers 7 Layer 4 Layer](#layers-7-layer-4-layer)
- [References](#references)


# Birth Of the network

#### Arpanet
ARPANET was created by the United States Department of Defense's Advanced Research Projects Agency (ARPA). Key contributors were:
- **J.C.R. Licklider**: Visionary behind the concept.
- **Leonard Kleinrock**: Developed packet-switching theory.
- **Robert Taylor**: Secured funding and support.
- **Vinton Cerf and Robert Kahn**: Developed the TCP/IP protocol suite.

ARPANET launched in 1969, connecting four universities.
The US DOD Invented this by funding the project.

#### Other Companies
Other Companies like IBM and many more tried to copy this and generated their own versions of this internets pre production version. However these were all proprietary meaning IBMs network couldn't talk to others and vice versa. 
# TCP/IP Reference Model

## OSI Reference Model ( Open System Interconnection )
![[OSI Reference Model.excalidraw]]
The OSI (Open Systems Interconnection) model is a conceptual framework used to understand and standardize the functions of a telecommunication or computing system without regard to its underlying internal structure and technology. The model is divided into seven layers, each specifying particular network functions.
### The Seven Layers of the OSI Model

1. **Physical Layer (Layer 1)**:
   - Deals with the physical connection between devices and the transmission and reception of raw bit streams over a physical medium.
   - Examples: Ethernet cables, Hubs.

2. **Data Link Layer (Layer 2)**:
   - Provides node-to-node data transfer and handles error correction from the physical layer.
   - Examples: Switches, Bridges, MAC addresses.

3. **Network Layer (Layer 3)**:
   - Manages data routing, forwarding, and addressing, enabling data to be sent from source to destination across multiple networks.
   - Examples: Routers, IP addresses.

4. **Transport Layer (Layer 4)**:
   - Ensures end-to-end communication, error recovery, and flow control.
   - Examples: TCP (Transmission Control Protocol), UDP (User Datagram Protocol).

5. **Session Layer (Layer 5)**:
   - Manages sessions or connections between applications, establishing, maintaining, and terminating connections.
   - Examples: Session establishment, maintenance, and termination protocols.

6. **Presentation Layer (Layer 6)**:
   - Translates data between the application layer and the network format, handling data encryption, compression, and translation.
   - Examples: Encryption (SSL/TLS), data compression.

7. **Application Layer (Layer 7)**:
   - Provides network services directly to user applications, facilitating communication with other applications over the network.
   - Examples: HTTP, FTP, SMTP, DNS.

### Importance of the OSI Model

- **Standardization**: Provides a universal set of standards for networking, ensuring interoperability between different systems and technologies.
- **Modularity**: Each layer is independent, so changes in one layer do not necessarily affect the others, making network management more efficient.
- **Troubleshooting**: Helps in diagnosing and fixing network issues by isolating problems within specific layers.
- **Education**: Aids in teaching and understanding how networks operate, providing a clear framework for studying and developing networking technologies.

By dividing network communication into these seven distinct layers, the OSI model simplifies the process of designing and implementing network protocols, ensuring that diverse systems can communicate effectively.

## TCP/IP

	![[TCP IP Ref Model.excalidraw.md]]

The TCP/IP reference model, also known as the Internet Protocol Suite, is a set of communication protocols used to interconnect network devices on the internet. It provides end-to-end data communication, specifying how data should be packetized, addressed, transmitted, routed, and received at the destination. The TCP/IP model simplifies network communication by dividing it into four layers, each responsible for different aspects of the communication process.

### Layers of the TCP/IP Reference Model

1. **Network Interface Layer (Link Layer)**
   - **Function**: Responsible for the physical transmission of data over a network. It defines protocols for how data is sent and received on the physical medium (like Ethernet).
   - **Protocols and Technologies**: Ethernet, Wi-Fi, ARP (Address Resolution Protocol), PPP (Point-to-Point Protocol).
   - **Components**: Network interface cards (NICs), cables, switches, and other hardware.

2. **Internet Layer**
   - **Function**: Handles the logical addressing and routing of data packets. It is responsible for moving packets from the source to the destination across multiple networks.
   - **Protocols**: IP (Internet Protocol), ICMP (Internet Control Message Protocol), ARP (Address Resolution Protocol), and RARP (Reverse Address Resolution Protocol).
   - **Components**: Routers, gateways.

3. **Transport Layer**
   - **Function**: Provides end-to-end communication, error detection and correction, and ensures that data is delivered in the correct order and without errors.
   - **Protocols**: TCP (Transmission Control Protocol) for reliable communication, and UDP (User Datagram Protocol) for connectionless communication.
   - **Components**: Hosts, end systems, applications.

4. **Application Layer**
   - **Function**: Contains protocols and services that support network applications. It provides services directly to the user's application processes, such as email, file transfer, and web browsing.
   - **Protocols**: HTTP (HyperText Transfer Protocol), FTP (File Transfer Protocol), SMTP (Simple Mail Transfer Protocol), DNS (Domain Name System), Telnet, SSH.
   - **Components**: Application software and network services.

### Comparison with OSI Model

The TCP/IP model is often compared to the OSI model, which has seven layers. Here are some key differences:

- **Layer Mapping**: The TCP/IP model has four layers, while the OSI model has seven layers. Some OSI layers are combined in the TCP/IP model (e.g., the OSI's Application, Presentation, and Session layers are combined into the TCP/IP Application layer).
- **Development**: The TCP/IP model was developed earlier and is based on standard protocols used on the internet, whereas the OSI model was developed as a theoretical framework.
- **Adoption**: The TCP/IP model is the basis for the Internet and is widely adopted, while the OSI model is more of a guideline and is used for teaching and conceptual understanding.

### Key Protocols and Their Functions

- **IP (Internet Protocol)**: Provides logical addressing and routing. It is responsible for packetizing data, adding addressing information, and ensuring that packets are routed correctly to their destination.
- **TCP (Transmission Control Protocol)**: Provides reliable, ordered, and error-checked delivery of a stream of bytes. It establishes a connection between the sender and receiver before data can be sent.
- **UDP (User Datagram Protocol)**: Provides a connectionless service for applications that do not require reliable delivery. It is used for tasks such as streaming audio and video.
- **HTTP (HyperText Transfer Protocol)**: Used for transferring web pages on the internet.
- **FTP (File Transfer Protocol)**: Used for transferring files between computers on a network.
- **SMTP (Simple Mail Transfer Protocol)**: Used for sending emails.
- **DNS (Domain Name System)**: Translates human-readable domain names into IP addresses.

### Importance of the TCP/IP Model

- **Standardization**: Provides a standardized set of protocols that ensures different devices and networks can communicate with each other.
- **Interoperability**: Ensures that various hardware and software components from different manufacturers can work together.
- **Scalability**: Supports a vast and growing network like the Internet, accommodating billions of devices.
- **Flexibility**: Allows for the integration of new technologies and protocols as the network evolves.

The TCP/IP model has been instrumental in the development and expansion of the internet, providing a robust and adaptable framework for network communication.

## Ports
Every Computer has a network connected to it if it has access to internet. Imagine your house being connected to the road network. However not everyone is welcome to your house. But for an office everyone should be welcomed or the work cant be done. Similar logic can be applied to ports. They are doors meaning end points for your data packets.  Each door and window or any means to enter the house/office can be deemed as a port with this logic.

A normal house is related to a private computer who only goes out in the internet and brings stuff back for himself lets say grocery here would be our everyday data browsing.

But for an office people come to the office from other office and from homes to do work and then get their work done and go out these are public ports in the current context. Anyone can access them. A firewall would be the security guard to the office.

With all that said for technical terms
In the context of computer networks, **ports** are logical constructs that serve as communication endpoints for data packets, facilitating interaction between applications and network services.
### Private Ports
- **Definition**: Ports that are used by software applications for specific purposes, as registered with IANA but not as universally standardized as well-known ports.
- **Port Range**: 1024 to 49151.
- **Usage**: Applications and services request registration of these ports to prevent conflicts and ensure proper allocation. Examples include:
    - **SQL Server**: Port 1433
    - **IMAP**: Port 143

### Dynamic Ports or Private
- **Definition**: Ports used for ephemeral connections, assigned dynamically by the operating system.
- **Port Range**: 49152 to 65535.
- **Usage**: Typically used by client-side applications to establish temporary connections with server-side services. These ports are often allocated dynamically during the connection setup process.

### Public Ports
- **Definition**: These are ports reserved for specific protocols and services that are well-defined and standardized.
- **Port Range**: 0 to 1023.
- **Usage**: Assigned by the Internet Assigned Numbers Authority (IANA) for widely-used services. Examples include:
    - **HTTP**: Port 80
    - **HTTPS**: Port 443
    - **FTP**: Port 21

## Sockets
Sockets are an abstraction of IP addresses and Ports. Now we just discussed what ports are in a relative argument that it is a door or a window or any means to enter a place. But what is the address of the place?
That here in Computer Network would be our IP. So a full office address + open doors = a address for someone to connect to the office. These sockets are also endpoints.

**Sockets** are fundamental components in networking that enable communication between applications over a network. They act as endpoints for sending and receiving data across a network and facilitate the interaction between software processes.

A **socket** is an abstraction that represents a combination of an IP address and a port number. It provides a mechanism for applications to communicate over a network using standard protocols such as TCP (Transmission Control Protocol) or UDP (User Datagram Protocol).

### Components of a Socket

1. **IP Address**
    
    - **Definition**: A unique identifier assigned to each device on a network.
    - **Purpose**: Specifies the device in the network communication process.
2. **Port Number**
    
    - **Definition**: A numerical identifier for a specific process or service on a device.
    - **Purpose**: Differentiates between different services or applications on the same device.

There are different types of sockets that i will not cover here.

## Socket Operation

1. **Binding**: Associating a socket with a specific IP address and port number on the local machine.
2. **Listening**: Preparing a socket to accept incoming connection requests (relevant for server-side sockets).
3. **Accepting**: Establishing a connection with a client and creating a new socket for that connection.
4. **Connecting**: Initiating a connection to a remote socket (relevant for client-side sockets).
5. **Sending/Receiving Data**: Transferring data between sockets using send and receive operations.
## HTTP/S
HTTPS Stands for Hyper Text Transfer Protocol Secure. It is an extension of HTTP designed to provide secure communication over a network using SSL and other method
### Key Features of HTTPS
There are various reasons why HTTPS was implemented even after the existence of HTTP. They are as follows.
- **Encryption**: HTTPS uses protocols like TLS ( Transfer Layer Security ) or SSL ( Secure Sockets Layer ) between a server and a client making their interconnectivity impenetrable.
- **Data Integrity**: With TLS and SSL we are sure that there will be no tampering of the data sent through the network between client and server thru and fro.
- **Authentication**: With the enrollment of HTTPS all websites are required to acquire a valid certificate from vendors so the users can be assured with the certificate that the website is indeed legitimate and not some other IP that could come from [[DNS Cache Poisoning]].
### How HTTPS Works
HTTPS works in a step based manner.
- **Handshake**: A handshake between server and client is performed where they check whether the server is legitimate or not. This is a TLS Handshake. The keys are negotiated here, Keys are exchanged, and Server certificate authentication is also done here.
- **Data Encryption**: After the Handshake both the server and client have a symmetric key. Using this key they encrypt and decrypt the data sent over the network.
- **Transmission**: Now the data is encrypted and ready for transmission.

# Differences Between Layer 7 and Layer 4 in the OSI Model

In the OSI (Open Systems Interconnection) model, networking and communication functions are divided into seven distinct layers. **Layer 7** and **Layer 4** represent different levels of this model, each handling specific aspects of network communication.

## Layer 7: Application Layer

- **Function**: 
  - Provides network services directly to end-user applications.
  - Manages application-level protocols and services that end users interact with.

- **Responsibilities**:
  - **Protocols**: Includes HTTP, HTTPS, FTP, SMTP, and DNS.
  - **Data Handling**: Deals with high-level protocols for data exchange and application-specific functions.
  - **Services**: Manages functions such as email, file transfer, and web browsing.

- **Examples**:
  - **Web Browsers**: Use HTTP/HTTPS to request and display web pages.
  - **Email Clients**: Use SMTP or IMAP to send and receive emails.

## Layer 4: Transport Layer

- **Function**:
  - Provides end-to-end communication services for applications and manages data flow between hosts.
  - Ensures complete data transfer between devices across a network.

- **Responsibilities**:
  - **Protocols**: Includes TCP (Transmission Control Protocol) and UDP (User Datagram Protocol).
  - **Data Handling**: Manages data segmentation, error correction, and flow control.
  - **Connection Management**: Establishes, maintains, and terminates connections (TCP) or handles connectionless communication (UDP).

- **Examples**:
  - **TCP**: Ensures reliable data transfer with error-checking and flow control.
  - **UDP**: Provides fast, connectionless communication with minimal overhead.

## Key Differences

1. **Layer Function**:
   - **Layer 7 (Application Layer)**: Focuses on application-specific protocols and user interactions. It interfaces directly with software applications.
   - **Layer 4 (Transport Layer)**: Focuses on end-to-end data transfer, managing communication between devices and ensuring data integrity and reliability.

2. **Data Handling**:
   - **Layer 7**: Deals with application data and provides services like web browsing or email.
   - **Layer 4**: Handles data segmentation into packets, manages connections, and ensures reliable delivery.

3. **Protocols**:
   - **Layer 7**: Includes protocols like HTTP, FTP, SMTP, and DNS.
   - **Layer 4**: Includes TCP and UDP, which manage data transport and error recovery.

4. **Interaction with End Users**:
   - **Layer 7**: Directly interacts with user applications and provides the interface for services.
   - **Layer 4**: Operates in the background, ensuring data is correctly transmitted between the application endpoints.

## Summary

Layer 7 (Application Layer) and Layer 4 (Transport Layer) of the OSI model serve different roles in network communication. Layer 7 provides application-level services and user interactions, while Layer 4 manages end-to-end communication, data integrity, and connection control. Understanding these layers helps in diagnosing network issues and designing efficient communication systems.


# References
