---
Title: Cybersecurity Fundamentals Lab 5
Status: true
marker:
  - "[[Cybersecurity Fundamentals]]"
  - "[[Cisco Network Simulations]]"
tags:
Date: 2025.08.12
Time: 10:30
---
# Setting OSPF Up
## Aim 
To set [[OSPF]] up and understand how area linking works. Later on we will learn how to implement [[Lab 5 Setting UP SSH|SSH]] and [[Lab 5 Other Tasks|Encrypt Configuration Files]]
## Lab work
We begin by making the topology. Its quite simple we have 
- 3 routers
- 2 switches
- 2 computers

![[IMG-20250918102128240.png|center]]

---
## Actual Work

## Step 1
Once the topology is ready we will configure the OSPF
Command to switch the line and start configuring the OSPF
```js "Router 0"
R1(config)# router ospf 1
```

Command to assign areas to the interfaces/IP's
```js
R1(config-router)# network 192.168.1.0 0.0.0.255 area 0

R1(config-router)# network 10.1.1.0 0.0.0.3 area 0
```

Command to change the interface to passive-interface.
	This basically makes the interface go awol and not send hello packets to all the devices to convert users into known neighbors. Read more at [[OSPF]].
```js
R1(config)# router ospf 1

R1(config-router)# passive-interface g0/1

R3(config)# router ospf 1

R3(config-router)# passive-interface g0/1
```

**Checking for OSPF Neighbors** 
```js
R3(config)# show ip ospf neighbor
R3(config)# show ip route
```

```js
Router>enable
Router#show ip ospf neighbor

Neighbor ID     Pri   State           Dead Time   Address         Interface
10.2.2.2          0   FULL/  -        00:00:31    10.1.1.2        Serial0/0/0
Router#
```

```js
Router#
Router#show ip route
Codes: L - local, C - connected, S - static, R - RIP, M - mobile, B - BGP
       D - EIGRP, EX - EIGRP external, O - OSPF, IA - OSPF inter area
       N1 - OSPF NSSA external type 1, N2 - OSPF NSSA external type 2
       E1 - OSPF external type 1, E2 - OSPF external type 2, E - EGP
       i - IS-IS, L1 - IS-IS level-1, L2 - IS-IS level-2, ia - IS-IS inter area
       * - candidate default, U - per-user static route, o - ODR
       P - periodic downloaded static route

Gateway of last resort is not set

     10.0.0.0/8 is variably subnetted, 2 subnets, 2 masks
C       10.1.1.0/30 is directly connected, Serial0/0/0
L       10.1.1.1/32 is directly connected, Serial0/0/0
     192.168.1.0/24 is variably subnetted, 2 subnets, 2 masks
C       192.168.1.0/24 is directly connected, GigabitEthernet0/1
L       192.168.1.1/32 is directly connected, GigabitEthernet0/1

Router#
```
---
### Setting Password
Setting configuration for minimum 10 digit password. This will set a password whenever someone tries to log on to the console.
```js
R1(config)# security passwords min-length 10
```

We have set the password to the good old gullible mpstme1234. With this every one who wants exec permission will have to know this secret.
```js
R1(config)# enable secret mpstme1234
```

### Questions on Setting password
- How does configuring an enable secret password help protect a router from being compromised by an attack?
	- We can prevent these issues.
	- Physical access : 
		- Anyone with access to the console port will be able to change the configuration files
		- They could take down interfaces.
		- Create Backdoors
	- Misconfigured VTY Lines:
		- People could bruteforce VTY Line Password
		- Immediate Exec Priviliges
		- Enables Secrets
	- Insider Threat
		- Junior Devs with password can make exec commands.
		- Junior devs could make accidental Wipeouts

---
## **Configuring** the lines 
Just like we configured the to be secure with a password we can set the other lines like Console to have a secure password so anyone with the access of these ports will have to login.

**Console Line**
```js
R1(config)# line console 0
// Setting Console Line's Config
R1(config-line)# password mpstme
// Set secret to mpstme
R1(config-line)# exec-timeout 5 0
// need to log in every 5 minutes 0 seconds
R1(config-line)# login
// Login prompt enabled
R1(config-line)# logging synchronous
// need to check
```

- Changed to config mode line
- Set password
- `exec-timeout 5 0` 
	- need login every 5 minute 0 seconds
- `login`
	- Login is required

**Aux Line**
```js
R1(config)# line aux 0
R1(config-line)# password mpstme1234
R1(config-line)# exec-timeout 5 0
R1(config-line)# login
```

Refer above for explanation

---
## Telnetting to `Router 2` from `Router 1`

At this point we will try to telnet to `Router 2` from `Router 1` which will fail because we have not set the VTY ( Virtual Terminals ) Lines.
```js
R2>telnet 10.1.1.1
```

### Questions
- Were you able to login? Explain.
	- We were not because the VTY Lines are not setup. Which essentially means that the virtual mean 
- What messages were displayed?
	- `Host Unreachable`
---
## Setting up VTY (Virtual Terminal ) Lines 
Since we have failed telnetting because of absence of VTY Lines we will do it now.

```js
R1(config)# line vty 0 4
// There are 5 VTY Lines in cisco packet tracer.
// We configure vty for 0 to 4 (0,1,2,3,4)
R1(config-line)# password ciscovtypass
// Set Password
R1(config-line)# exec-timeout 5 0
//Exec Timeout 5 min 0 secs
R1(config-line)# transport input telnet
// setting main protocol a telnet
R1(config-line)# login
// Login Required Config Command
```

Read the comments to understand the purpose of each command.


### Questions after setting VTY
- Were You able to login? 
	- Yes Since the VTY Lines are now configured.
- Enter into exec mode.
	- No we cannot enter into exec mode as we have only local priviliges.
	- Thus we cannot read the aux and vty passwords
	- After enabling a secret in Router 3 I was able to get into `exec` mode and read the config file
- Can you read the aux and vty password?
	- Yes these are stored in clear words.

## Setting UP `password-encryption`
As we have discovered a major vulnerability we will add security through depth by encrypting the passwords on the victim Router.
One can hide their passwords from being in clear text by using the `service password-encryption` command to encrypt the password in the configuration files.

**After Encryption**
```js
line con 0
 exec-timeout 5 0
 password 7 082C5C5D1D140046405858
 login
line aux 0
line vty 0 4
 exec-timeout 5 0
 password 7 0822455D0A1613030B1B0D1739
 login
 transport input telnet
```

### Questions on Password-encryption
- **Enable secret password** (set with `enable secret`)
    - This is **Type 5** (MD5 hash) by default.
    - Stronger encryption, one-way hashed, harder to crack.
- **Other passwords** (console, AUX, VTY) after `service password-encryption`
    - These are **Type 7**.
    - Weak reversible encryption, mostly just obfuscation, so not secure against an attacker who knows Type 7.

# References
![[IMG-20250918102128315.png]]
![[IMG-20250918102129141.png]]
s
![[IMG-20250918102129646.png]]
![[IMG-20250918102130023.png]]
![[IMG-20250918102130124.png]]
###### Information
- date: 2025.08.12
- time: 10:30
![[IMG-20250918102130390.png]]
```bash 

Router>
Router>enable
Router#config t
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#line console 0
Router(config-line)#password mpstme
Router(config-line)#exec time 5 0
                         ^
% Invalid input detected at '^' marker.
	
Router(config-line)#exec-timeout 5 0
Router(config-line)#login
Router(config-line)#logging synchronous
Router(config-line)#
Router#
%SYS-5-CONFIG_I: Configured from console by console

Router#line console 0
            ^
% Invalid input detected at '^' marker.
	
Router#config t
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#line console 0
Router(config-line)#password mpstme1234
Router(config-line)#
Router#
```
