---
Title: DHCP
Status: 
marker:
  - "[[networking]]"
  - "[[IP]]"
  - "[[DNS]]"
tags: 
Date: 2024.08.01
Time: 16:54
---
# DHCP

# Main note

#### What is DHCP
DHCP stands for Dynamic Host Configuration [[Protocols|Protocol]]. It is the critical feature on which the users of an enterprise network communicate. DHCP helps enterprises to smoothly manage the allocation of [[IP]] to the end-user clients’ devices such as desktops, laptops, cellphones, etc. is an application layer protocol that is used to provide:
```
Subnet Mask (Option 1 - e.g., 255.255.255.0)  
Router Address (Option 3 - e.g., 192.168.1.1)  
DNS Address (Option 6 - e.g., 8.8.8.8)  
Vendor Class Identifier (Option 43 - e.g.,   
'unifi' = 192.168.1.9 ##where unifi = controller)
```
DHCP is based on a [[DHCP#^1]] and based on [[discovery]], [[offer]], [[request]], and [[ACK]].

In the DHCP (Dynamic Host Configuration Protocol) client-server model, the process of obtaining an IP address involves a sequence of messages between the client and server, known as DORA: Discovery, Offer, Request, and Acknowledgment (ACK). Here is a detailed explanation of each step:

1. **Discovery**: ^1
   - **What happens**: The DHCP client, which needs an IP address, broadcasts a DHCP Discover message to the network to find available DHCP servers.
   - **Purpose**: This message lets the DHCP servers know that a client is looking for an IP address and other network configuration parameters.

2. **Offer**:
   - **What happens**: One or more DHCP servers that receive the Discover message respond by broadcasting a DHCP Offer message to the client.
   - **Purpose**: The Offer message contains an available IP address and other network configuration details like the subnet mask, default gateway, and DNS servers. The client receives offers from multiple servers and chooses one.

3. **Request**:
   - **What happens**: The DHCP client sends a DHCP Request message to the server from which it wants to obtain the IP address.
   - **Purpose**: The Request message indicates to the chosen DHCP server that the client accepts the offered IP address and other network settings. It also informs other DHCP servers that the client has selected an offer, so they can release their offered IP addresses back to the pool.

4. **Acknowledgment (ACK)**:
   - **What happens**: The selected DHCP server sends a DHCP Acknowledgment (DHCP ACK) message to the client.
   - **Purpose**: The ACK message confirms that the IP address has been leased to the client, along with the lease duration and other network configuration parameters. At this point, the client can use the assigned IP address and other settings to communicate on the network.

These steps ensure that the client receives the necessary network configuration to function properly within the network, and they help manage IP address allocation efficiently.


## Why Do We Use DHCP?

DHCP helps in managing the entire process automatically and centrally. DHCP helps in maintaining a unique IP Address for a host using the server. DHCP servers maintain information on TCP/IP configuration and provide configuration of address to DHCP-enabled clients in the form of a lease offer.


# References


###### Information
- date: 2024.08.01
- time: 16:54