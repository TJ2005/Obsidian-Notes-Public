---
Title: Configuring a login warning banner on router R1 and R3
Status: true
marker:
  - "[[Cisco Network Simulations]]"
  - "[[OSPF]]"
  - "[[Setting up OSPF & Telnetting Cybersecurity Fundamentals Lab 5 Task 1]]"
tags:
Date: 2025.09.09
Time: 01:52
---
Topology used in this lab is from [[Setting up OSPF & Telnetting Cybersecurity Fundamentals Lab 5 Task 1| Lab 5 OSPF ]]
# Task 2 : Configuring a login warning banner on router R1 and R3
**Task 1**
Setting up the banner for login with this command. With this we can display a message for every user who tries to telnet on the router.

```nginx
router3 # banner motd $Unauthorized access strictly prohibited!
```

#### Question
What does the `$` convert into in the `show run` command. It converts into `\c` these are markers from cisco to show where banner starts and ends.

```nginx
Router#show run | section prohibited
banner motd ^CUnauthorized access strictly prohibited!^C
```

# Task 3 : Username Password for R1 and R3
We will be setting new users for telnetting in this one.

Creating a new user using this command.
```js
R1(config)# username user01 secret user01pass
```

Setting the console line to use this by default
```js
R1(config)# line console 0
R1(config-line)# login local
R1(config-line)# end
R1# exit
```

Now we are forced to switch to a new user.

### Questions
Which Hashing method is used for the password
- MD5 Hashing method is used for pass
Whats the difference between logging in the console before and now
- The console now prompts for user
- harder to bruteforce
Were you able to issue `show-run`
- Yes
Were you prompted for a password to go to exec mode
- Yes
Were you prompted for a username & a password to telnet?
- Yes 

# Task 4 : Configure SSH Server on router r1 and R3
# References


###### Information
- date: 2025.09.09
- time: 01:52