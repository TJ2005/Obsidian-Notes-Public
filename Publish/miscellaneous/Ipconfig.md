---
Title: Ipconfig
Status: true
marker: 
tags: 
Date: 2024.08.09
Time: 20:37
---
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

###### Information
- date: 2024.08.09
- time: 20:37