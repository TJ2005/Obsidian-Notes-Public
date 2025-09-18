---
Title: Lab 5 Setting UP SSH in
Status: true
marker:
  - "[[Cybersecurity Fundamentals]]"
  - "[[Computer Networks]]"
  - "[[Cisco Network Simulations]]"
  - "[[Setting up OSPF & Telnetting Cybersecurity Fundamentals Lab 5 Task 1]]"
tags:
  - BTech
Date: 2025.09.09
Time: 02:11
---
# Lab 5 Setting UP SSH in
The topology used in this lab document is from [[Setting up OSPF & Telnetting Cybersecurity Fundamentals Lab 5 Task 1|Lab 5 Task 1]]
### Setting a hostname for each device
Each device has to have a hostname for themselves. Set that by this command.
```js
hostname {whateverhostnameuwant}
```

```js
router# hostname router1
router1#
```

### Setting up SSH Key Pair for comms
We will need a RSA Key pair to communicate with SSH Protocol. We can gen that using this command.
```js
Router1(config)# crypto key generate rsa 
```

### Configure SSH Timeouts and Auth Parameters
Set the timeouts for failsafe protection.
```js
Router1(Config)# ip ssh time-out 90
// 90 seconds timeoutu for ssh
Router1(Config)# ip ssh authentication-retries 2
```

#### Question
Show IP SSH Command Output

```js
router3#show ip ssh

SSH Enabled - version 1.99

Authentication timeout: 120 secs; Authentication retries: 3
```


# References


###### Information
- date: 2025.09.09
- time: 02:11