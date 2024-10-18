---
Title: ping
Status: 
marker: 
tags: 
Date: 2024.08.06
Time: 17:58
---
# Index
- [Ping](#ping)
  - [Syntax](#syntax)
  - [Storing Outputs](#storing-outputs)
  - [Example](#example)
  - [Using Ping to Estimate Distance](#using-ping-to-estimate-distance)
- [References](#references)

# Ping
Pinging is literally sending requests to the network to the address you write after the command.

#### Syntax
The command for windows is given by
`ping address`

#### Storing Outputs
Store this ping output by this 
`ping <address> > output.txt`

#### Example
For pinging nmims.in at college we got this output 
```powershell
Pinging nmims.in [95.217.93.209] with 32 bytes of data:
Reply from 95.217.93.209: bytes=32 time=140ms TTL=49
Reply from 95.217.93.209: bytes=32 time=139ms TTL=49
Reply from 95.217.93.209: bytes=32 time=263ms TTL=49
Reply from 95.217.93.209: bytes=32 time=229ms TTL=49

Ping statistics for 95.217.93.209:
    Packets: Sent = 4, Received = 4, Lost = 0 (0% loss),
Approximate round trip times in milli-seconds:
    Minimum = 139ms, Maximum = 263ms, Average = 192ms
```



#### Using Ping to estimate distance
This is the most horrible way to estimate actual distance... Regardless

Here we got the delay to be 140ms for one packet to calculate the distance we will account for The Speed in copper wire is $2*10^8$

To calculate the distance on an average basis (not accurate) we can apply

$$velocity = distance/time$$
$$2*10^8 = distance/140*10^-3$$
therefore
$$distance = 2*10^8*140*10^-3$$

Distance = 28000000m
Distance = 280000km
The distance it covered is probably 280,000 kms

To retrieve locations one shall check [[IP Lookup]]

---

# References


###### Information
- date: 2024.08.06
- time: 17:58