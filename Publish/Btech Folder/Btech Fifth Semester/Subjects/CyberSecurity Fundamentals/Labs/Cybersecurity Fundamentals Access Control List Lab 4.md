---
Title: Cybersecurity Fundamentals Lab 4
Status: true
marker:
  - "[[Cybersecurity Fundamentals]]"
tags: 
Date: 2025.08.05
Time: 11:40
---
# Cybersecurity Fundamentals Lab 4
This lab focuses on access control lists. We will cover this:
- How the order of commands matter.
- Understand various types of access control list.

### Standard ACL's
It can filter only on the basis of the **source IP**.
You can filter:
- Network Host
- Source Host
You cannot Filter:
- Destination of packet
- Protocol 
- Port

### Extended ACL's
An extended ACL gives you much more power than just a standard ACL.
Extended IP ACLs check Packet Addresses for:
- source
- destination
They can also check for:
- protocols
- port numbers


## Network Topology ( CISCO )

![[IMG-20250808123453650.png|500]]
![[IMG-20250808123453782.png|center]]

- **On the router we disable any connection for 10.1.1.2**
	- `Router>en`
	  - This command is used to enable privileged EXEC mode on a Cisco router. It prompts for the enable password if one is set, allowing access to more advanced commands.
	- `Router#config t`
	  - This command enters global configuration mode from privileged EXEC mode, allowing configuration changes to be made on the router.
	- `Router(config)#`
	  - This prompt indicates that the router is in global configuration mode, where you can configure various router settings such as interfaces, routing protocols, and access lists.
	- `Router(config)#access-list 10 deny host 10.1.1.2`
	  - This command creates an access control list (ACL) entry that denies traffic from the specific host IP address `10.1.1.2`. The number `10` identifies the ACL.
	- `Router(config)#access-list 10 permit any`
	  - This command adds an entry to the ACL with identifier `10` that permits traffic from any source IP address, typically used to allow all traffic not explicitly denied by previous entries.
	- `Router(config)#interface fa0/0`
	  - This command enters interface configuration mode for the Fast Ethernet interface `0/0`, allowing specific configurations to be applied to that interface.
	- `Router(config-if)#ip access-group 10 in`
	  - This command applies the ACL with identifier `10` to the Fast Ethernet interface `0/0` in the inbound direction, filtering traffic as it enters the interface.
	- `Router#show access-lists 10`
	  - Check List

After this when we ping/try to access the website we successfully have validated that we cannot access the website since the hosts are unreachable.

- Now we configure the access list to disable the TCP Traffic from host IP address 10.1.2.2
	- `Router>en`
	  - This command is used to enable privileged EXEC mode on a Cisco router. It prompts for the enable password if one is set, allowing access to more advanced commands.
	- `Router#config t`
	  - This command enters global configuration mode from privileged EXEC mode, allowing configuration changes to be made on the router.
	- `Router(config)#access-list 110 deny tcp host 10.1.2.2 host 10.1.5.2 eq www`
	  - This command creates an access control list (ACL) entry that denies TCP traffic from the host IP address `10.1.2.2` to the host IP address `10.1.5.2` on port `www` (port 80). The number `110` identifies the ACL.
	- `Router(config)#access-list 110 permit ip any any`
	  - This command adds an entry to the ACL with identifier `110` that permits any IP traffic from any source to any destination, typically used to allow all traffic not explicitly denied by previous entries.
	- `Router(config)#interface fa0/0`
	  - This command enters interface configuration mode for the Fast Ethernet interface `0/0`, allowing specific configurations to be applied to that interface.
	- `Router(config-if)#ip access-group 110 out`
	  - This command applies the ACL with identifier `110` to the Fast Ethernet interface `0/0` in the outbound direction, filtering traffic as it exits the interface.
	- `Router#show access-lists 110`
	  - This command is used to display the contents of the access list with identifier `110`, allowing verification of the configured rules.

After doing these steps we have disabled the port **www** which translates to default 80 port with identifier 110.

When we ping the device we can **observe** that the **Pings go through** but the **Web server cannot be accessed.**


## **Questions & Answers**
1. Explain the significance of the implicit "deny all" rule in ACLs. How does it affect traffic that is not explicitly permitted?
	- If a packet does not meet any of the conditions that are defined before the `deny all` statement it will be denied permission to go through
2. Given a set of overlapping ACL entries, explain how the router determines which rule to apply.
	- The rules are a kind of venn diagram
3. An administrator reports that legitimate traffic is being dropped after applying an ACL. What troubleshooting steps to be taken to identify and resolve the issue?
	- Identify the Correct 
		- Protocol
		- Ports
		- Devices/mac addresses to deny
	- Basically narrow down the target that is supposed to be dropped with better queries.
4. Discuss how the placement of an ACL (inbound vs outbound) on an interface affects its operation.
	- **Outbound** : If we are to disable any connections to anyone outbound the packets will never reach the target destination
		- It essentially sets an outbound rule that nothing will to the set `Target` 
		- For example if a device is known to contact only a few selected devices to send the data outwards we can set an inverse outbound rule that only these device can be sent data.
		- With such rule if a malware that has gained access to the computer with execution power it wont be able to send the data outbound. Let alone even respond to the commands that the attacker sends to the host.
	- **Inbound** : If we are to disable any inbound connections we basically deny the applications the packets that are trying to reach them.
		- Essentially sets a rule that doesn't let the selected targets contact the host and send data to the host where the rule is set.
		- For example if a device is getting unwanted traffic it can basically identify those endpoints and block them so the unwanted traffic is no more being responded or one can say they are ignored.
5. Describe how ACLs can be integrated into a layered defense strategy in enterprise
	- A Layered Defence strategy has multiple levels that the attacker would have to encounter to gain ultimate access.
	- ACLS can be used as a beginner level layer to deny the access to the attacker
# References


###### Information
- date: 2025.08.05
- time: 11:40