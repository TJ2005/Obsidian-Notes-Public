---
Title: CompTIA Client Server Model
Status: 
marker:
  - "[[CompTIA]]"
  - "[[Computer Networks]]"
tags:
  - self-study
Date: 2024.10.01
Time: 16:21
---
# Client Server Model
The [[client server model]] as the name suggests is a central network where every data is sent and fetched through a server instead. Every server has a **similar** [[NOS]] installed so they can talk to each other efficiently.

## Server
This takes into account a windows server to explain everything about servers.
When a windows server controls access to a group of computers this logical group of computers is called a **windows domain**. 
The centralized directory which contains the user account information for all the computers is called a  **AD ( Active Directory )**.
Each user on the network has their own domain-level account assigned by the network administrator and kept in Active Directory
This account is local which is specifically set to that domain or a microsoft account or that domain account which links local domain resources with the microsoft resources. 
A user may Sign In on the network using their logon resources and get access to the active directory.
This is managed by **AD DS ( Active Directory Domain Services )**

## Client
Now this was all servers. Lets have a look on clients that are served.
The computer that makes the request is called a **client**. Clients have local data storage they can store their own data and application data. 
Clients cannot access each others data directly and it has to go through the server.
![[IMG-20241016142605494.png]]
### Responsibilities of the server client NOS
- Managing data and other resources for clients.
- Ensuring authority and that only authorized users have access to their accounts.
- Read Write permissions.
- Restricting when and where a user can access their files from.
- Dictating or generalizing a set rules that the clients use to communicate often called protocols
- Supplying the application data and files to clients.

## Properties of Servers
A server has these properties due to the following reasons:
- More Memory and Processing clockspeed and power
	- Since they handle more logical clients connections
- Uses **RAID ( Redundant Array of Independent disks )** so that if one hard drive fails another takes responsibility

## Advantages & Disadvantages of CS Model
There are various advantages of Client Server Model Over P2P model.
- User accounts and passwords to the network are assigned in one place.
- Access to multiple shared resources can be easily granted to one user.
- Problems can only occur at one location so fixing also needed at only one location
- Client Server Models are more scalable than P2P since theres only one Data Base of Lists.

## Miscellaneous Questionnaire

**REMEMBER THIS...**

- Compare physical topology with logical topology.
- Describe a client-server network model in contrast with a peer-to-peer network model.
- Explain the role of AD (Active Directory) in a Windows domain.

**SELF-CHECK**

1. Which of the following is part of a network's physical topology?
    
    - a. A network server's operating system
    - b. A printer plugged into a nearby desktop computer
    - c. Password for the wireless network
    - d. File permission settings on a desktop computer
2. Which of the following is an advantage of P2P file sharing?
    
    - a. Scalable
    - b. Centrally controlled
    - c. Secure
    - d. Inexpensive
3. What group must clients join to access network resources in a client-server network?
    
    - a. Workgroup
    - b. Domain
    - c. Peer group
    - d. RAID

	
# References


###### Information
- date: 2024.10.01
- time: 16:21