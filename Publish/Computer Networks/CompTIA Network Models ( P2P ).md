---
Title: CompTIA Network Models
Status: 
marker:
  - "[[Computer Networks]]"
  - "[[CompTIA]]"
  - "[[networking]]"
  - "[[network Topologies]]"
tags:
  - "#self-study"
  - "#book"
  - excalidraw
Date: 2024.09.23
Time: 11:26
---
# CompTIA Network Models
In this note we will cover these topics
### Topics Covered
- [Network Models](#network-models)
  - [Physical Topology](#network-models)
  - [Logical Topology](#network-models)
- [Peer to Peer Network Model](#peer-to-peer-network-model)
  - [Advantages of P2P Network](#advantages-of-p2p-network)
  - [Disadvantages of P2P Network](#disadvantages-of-p2p-network)
- [NOS (Network Operating Systems)](#nos)

---

This index links to each section, providing an organized way to navigate the topics covered in your notes.
# Network Models
A topology describes how the part of a whole that are networking devices are working together. When studying networking we need to understand both the **Physical Topology** and **Logical Topology** of a network.

- **Physical Topology**: Mostly refers to a network's hardware and how other computers and devices are interconnected with cables or radio signals.
- **Logical Topology**: It refers to how software controls access to network resources and software gain access to the network. How applications share their resources on the network.

By applying control on how users and programs get access to resources on networks is a function of the Operating Systems. The OS chooses either Peer to Peer connection or client-server model to connect. Peer-to-peer can be achieved with literally any two device.

## Peer to Peer Network Model
In a P2P Model the operating system of each computer on the network is responsible for controlling access to its resources without centralized control.

Each computer on P2P network is called a **Node** or **Hosts** on the network and controls its own administration, resources, and security.

In a P2P Network devices can share resources through various techniques of file sharing or user accounts. Most OSs offer for sharing files with Peered Devices. 
These Work Even if all the nodes are running different OS.

If all the nodes are windows based then resources can be shared using windows folder using file sharing or a Windows WorkGroup. In both the cases each computer contains and maintains a list of users and their rights to Local Resources on the computer. You can combine folders and file sharing work groups but that increases confusion and complicates the situations.

If the computer network has fewer than 15 nodes a peer to peer network is the way to go.
### Advantages of P2P Network
Page 27
- They are simple to configure
- Used where technical 
### Advantages 
- They are not scalable, when networks needs to be increased in size adding or editing the network.
- They are not necessarily secure, meaning that in simple installations, data and other resources shared by network users can be easily discovered and used by unauthorized people
- They are not practical for connecting more than a few computers because it’s too time consuming to manage the resources on the network.
	- For example, suppose you want to set up a file server using P2P file sharing. A server is any computer or program that provides a service, such as data or other resources, to other devices. A file server stores files for other computers to access. On this file server, you create a folder named \SharedDocs and create 20 user accounts, one for each of 20 users who need access to the folder. Then you must set up the workstations with the same user accounts, and the password to each user account on the workstation must match the password for the matching user account on the file server. It can be an organizational nightmare to keep it all straight! If you need to manage that many users and shared resources, it’s probably best to implement Windows Server or another NOS.
![[Pasted image 20241001133030.png]]


# Side Notes
## NOS
Nos is a serer Operating servers. There are various servers that are available for example Ubuntu Server, Red Hat Enterprise etc. In a server everything is managed using a CLI. Hypervisors are also used to 


# References


###### Information
- date: 2024.09.23
- time: 11:26
- Continued to [[CompTIA Client Server Model]]