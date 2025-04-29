---
Title: Computer Networks Lecture 1
Status: 
marker:
  - "[[networking]]"
  - "[[Data]]"
  - "[[Prompts]]"
  - "[[logical addresses]]"
  - "[[IP]]"
  - "[[IPv4]]"
  - "[[IPv6]]"
  - "[[Ports]]"
  - "[[TTL]]"
  - "[[Apache2]]"
  - "[[Nginx]]"
tags: 
Date: 2024-07-15
Time: 22:25
---
# Computer Networks Lecture 1
# References
## Index
1. [Intro (Circuit Switching vs Packet Switching)](#intro-circuit-switching-vs-packet-switching)
2. [Data Transmission Methods](#data-transmission-methods)
3. [Prompts](#prompts)
4. [Connections](#connections)
5. [Logical Address](#logical-address)
6. [Port Addresses](#port-addresses)
7. [TTL (Time To Live)](#ttl)
8. [Software Servers](#software-servers)

---

# Computer Networks Lecture 1

15-07-2024 10:13

**Status:**

**Tags:** [[Computer Networks]] [[networking]] [[network Topologies]]

---

## Intro (Circuit Switching vs Packet Switching)
Telephones used circuit switches to use analog signals to contact multiple people. There are literally physical switches, which is why they are noted as circuit switching. Nowadays, modern devices use packet switching. The [[packets]] can be represented as something like an envelope. The packets cannot be endless; they should have a limit. There is technology in networking such as datagrams, segments, and packets.

---

## Data Transmission Methods

#### [[Simplex]]
In a simplex method of data transmission, data can only go one way, and one device can send at a time.

#### [[Half Duplex]]
Data can be sent both ways, but only one device at a time.

#### [[Full Duplex]]
Data can be sent both ways at the same time.

---

## Prompts
When a computer is booted up, it gives a prompt shell interface.

In [[windows]], we have:
```shell
c:\>netstat -p
```

In Linux when we are not sudo, we have:
```shell
$ping 127.0.0.1
```

In root, we have:
```shell
#
```
It has the most privileges because it is [[root]].

Why don't we use MAC addresses to [[ping]]?

## IPConfig
IP addresses are given to each network ID so to check that out we have a tool called [[Ipconfig]] Generally in all Operating Systems.

### What is IP Config
`ipconfig` is a tool used to access the information stored about the current network interfaces installed in a computer.

It gives you a list of data such as:
- `ipconfig /all`
	- displays Detailed information about [[mac Address]],[[DNS Server]],Subnet Mask,gateways
- `ipconfig /release`
	- Releases the current [[DHCP]] lease for all network adaptors thus in turn removing the [[IP]] address configuration assigned to us
- `ipconfig /renew`
	- Requests a new [[DHCP]] Lease thus assigning ourselves a new [[IP]].
- `ipconfig /renew6 /release6`
	- Does exactly what `ipconfig /renew` & `ipconfig /release` does but with [[IPv6]]
- `ipconfig /flushdns`
	- Clears the [[DNS]] resolver Cache, which can resolve DNS problems.
- `ipconfig /displaydns`
	- Just displays the DNS resolver cache

Refer [[Ipconfig]]

---
## Connections
Simply put, a copper cable itself cannot form a network; it is a passive component. It needs a [[node]] that is intelligent to control it. The prompt shells are nodes. Any device that sends useful data to the network can be called a node.

---

## Logical Address


[[IPv4]] and [[IPv6]] are called [[logical addresses]] because they are arbitrary; they can be changed by the user by flushing. They are not like a physical address that can never be changed.

What happens when one of the multiple Google servers loses a network card? When there is a massive scalable system, there should be independence from hardware addresses. To combat this, there are IP addresses.

## Port Addresses
In networking, when discussing port numbers, particularly in the context of [[TCP]] (Transmission Control Protocol) and [[UDP]] (User Datagram Protocol), the range of port numbers and their classifications are important for understanding how network communication is organized. Here’s a breakdown:

### Port Number Ranges

1. **Closed Ports (1 to 1023):**
   - Reserved for well-known services or system services, such as [[HTTP]] (port 80), [[HTTPS]] (port 443), [[FTP]] (port 21).
   - Not typically used for dynamically assigned or user-specific purposes.

2. **Private Ports (1024 to 5000):**
   - Known as registered or private ports, used by applications and services for various purposes, but not standardized.
   - Generally not registered with the [[IANA]] (Internet Assigned Numbers Authority).

3. **Temporary Port Addresses (Above 5000):**
   - Considered temporary or ephemeral ports, dynamically assigned by the OS to client-side applications and services when they initiate a connection to a server.
   - Used for outgoing connections and released back to the pool for reuse by other applications once the communication session is terminated.

### Usage and Significance

- **[[Closed Ports]]:** Reserved for well-known services and system functions.
- **[[Private Ports]]:** Available for applications and services without standardization.
- **[[Temporary Ports]]:** Dynamically assigned for outgoing connections from client applications.

These ports are decided by the Internet Task Force.

### Example Scenario

- **[[Web Browser]]:** When you browse a website, your web browser typically uses temporary ports (e.g., ports above 5000) to establish connections to the web server’s well-known port (e.g., port 80 for HTTP).

Understanding these port ranges helps in configuring firewalls, routing rules, and network security policies effectively.


## [[TTL (Time To Live)]]
In networking, the concept of Time To Live (TTL) is crucial for managing the lifespan of data packets traveling across networks. TTL is a mechanism used to prevent packets from circulating indefinitely within a network.

### Time To Live (TTL) Overview

1. **Definition:**
   - TTL is a field in the header of an IP packet that specifies the maximum number of hops (routers or other network devices) the packet can pass through before being discarded.

2. **Initial Value:**
   - When a packet is created, the TTL field is set to a specific initial value.

3. **Decrementing TTL:**
   - As the packet traverses each router, the router decreases the TTL value by one.

4. **TTL Expiry and Packet Discard:**
   - If the TTL value reaches zero before the packet reaches its destination, the router discards the packet and typically sends an ICMP Time Exceeded message back to the source.

### Importance of TTL

1. **Preventing Network Congestion:**
   - TTL ensures that stray or misrouted packets are automatically removed from the network.

2. **Network Stability:**
   - TTL reduces the risk of network congestion and routing loops.

3. **Diagnostic Tools:**
   - TTL is used by diagnostic tools like `tracert` (Windows) or `traceroute` (Unix/Linux).

### Example of TTL in Action

1. **Packet Creation:**
   - A packet is created with an initial TTL value of 64.

2. **First Router:**
   - The packet reaches the first router, which decrements the TTL to 63.

3. **Subsequent Routers:**
   - Each subsequent router continues to decrement the TTL by one.

4. **TTL Expiry:**
   - If the packet passes through 64 routers and the TTL reaches zero, the 64th router discards the packet and sends an ICMP Time Exceeded message back to the source.

### Summary

TTL is a critical feature in networking that controls the lifespan of packets to ensure they do not circulate indefinitely.

Refer [[TTL]]

---
# [[Software Servers]]

1. **[[HTTP]] (HyperText Transfer Protocol) Server:**
   - **Function:** Handles requests from web clients and delivers web pages, files, or other content over the internet.
   - **Example:** Apache HTTP Server (httpd), Nginx, Microsoft IIS (Internet Information Services).
   - **Usage:** Essential for hosting websites, web applications, and APIs accessible via browsers.

2. **[[FTPD]] (File Transfer Protocol Daemon):**
   - **Function:** Supports the FTP protocol for transferring files between computers on a network.
   - **Example:** vsftpd (Very Secure FTP Daemon), ProFTPD, FileZilla Server.
   - **Usage:** Commonly used for uploading website files, large data transfers, and managing remote file storage.

3. **[[Telnet Server]]:**
   - **Function:** Enables remote login and control of a computer or server over a network.
   - **Example:** Telnetd (Telnet daemon) on Unix/Linux systems.
   - **Usage:** Historically used for remote administration and troubleshooting of servers, now largely replaced by more secure protocols like SSH.

4. **[[SMTP]] (Simple Mail Transfer Protocol) Server:**
   - **Function:** Handles the sending, receiving, and routing of email messages over the internet.
   - **Example:** Postfix, Microsoft Exchange Server, Sendmail.
   - **Usage:** Essential for email communication, ensuring messages are delivered reliably and efficiently across different mail domains.

Refer [[Software Servers]] for more.

---


## Non Indexed
NIC
Networking has millions of packets. To flush these stray packets outside, there is TTL to flush these packets. When TTL = Value turns 0, it gets purged. It is an automatic process.

IP Address and Port together make a socket, which is an API command.

POP3
When a new tab is opened, at that moment, there is a new port opened and attached to the same window.

---

# References