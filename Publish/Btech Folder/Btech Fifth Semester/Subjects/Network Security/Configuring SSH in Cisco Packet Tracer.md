---
Title: Configuring SSH in Cisco Packet Tracer
Status: true
marker:
tags:
Date: 2025.09.15
Time: 18:34
---
# Configuring SSH in Cisco Packet Tracer

---

### 1. Initial Router Configuration

This step involves basic device setup, including assigning a **hostname** and configuring an **IP address** on the interface for network connectivity.

Bash

```
configure terminal
! Set a unique hostname for the device
hostname R1
!
! Access the interface connected to the local network
interface GigabitEthernet0/0
!
! Assign an IP address and subnet mask
ip address 10.0.0.1 255.255.255.0
!
! Enable the interface
no shutdown
exit
```

---

### 2. Configure IP Domain Name

An **IP domain name** is required before you can generate the RSA keys used by SSH for encryption.

Bash

```
! Configure a domain name for the network
ip domain-name mynetwork.local
```

---

###  3. Generate RSA Crypto Keys

SSH requires **RSA (Rivest-Shamir-Adleman) keys** to encrypt the connection. This command generates these keys. A modulus of 1024 bits is standard for lab environments.

Bash

```
! Generate RSA keys for SSH encryption
crypto key generate rsa
!
! When prompted for the key size, enter 1024
1024
```

---

### ## 4. Create a Local User Account

SSH requires user authentication. This command creates a local username and a secret (encrypted) password on the router for login purposes.

Bash

```
! Create a local user with a secure password
username admin secret cisco123
```

---

### ## 5. Configure VTY Lines for SSH Access

The virtual terminal lines (**VTY**) are used for remote access. These commands configure the VTY lines to accept only SSH connections and to authenticate users against the local user database.

Bash

```
! Access the virtual terminal lines 0 through 4
line vty 0 4
!
! Specify that only SSH is allowed for incoming connections
transport input ssh
!
! Use the local user database for login authentication
login local
!
exit
```

---

### ## 6. Verify SSH Connection from PC

From the command prompt of a PC on the same network, use the `ssh` command to connect to the router's IP address with the credentials created in Step 4.

Bash

```
# The command format is: ssh -l <username> <router_ip_address>
ssh -l admin 10.0.0.1
```

You will be prompted for the password (`cisco123`), and upon successful entry, you will gain remote access to the router's command line.



# References


###### Information
- date: 2025.09.15
- time: 18:34