---
Title: DNS Resolving
Status: true
marker: 
tags: 
Date: 2024.08.09
Time: 22:22
---
Domain Name System is run on most computers. The main function is storing  domain name addresses to a certain IP Address and vice versa. A simple domain for say https://google.com isn't something that a client contacts. It should be resolved to a IP Address before being contacted.

#### How
There are usually some ( one or two ) servers that know what Domain Name is at what IP. 
Now where these two servers lie and to find them is what actually also DNS does. Imagine asking for the way when you are lost before maps was invented. You would ask from person to person after each turn u make right.

Similarly the DNS also resolves the IP address by asking multiple servers about the DNS and then they let us know the way further.
If this cannot be completed you get the good ol DNS couldn't be resolved error.

#### Working
We store the frequently visited websites IP's on a cache. 
Lets say you turn your computer on after a month all the cache has been flushed.
The first step that your computer does when u look for `google.com` IP is you look for a name server.

The first name server you contact is either your organization's Name Server that could be your university's DNS or a Company's server or if you are at home it would be your ISP or maybe an OpenDNS or some opensource DNS server that is selfhosted by you.

![[DNS Resolving.excalidraw]]

Every Processing unit here has a cache that temporarily stores the IP.
The first person who checks for google.com will store the address in cache to optimize traffic so they store it with them and start serving as a DNS Server of a sort between the network so they don't have to create extra traffic at Root Name Server or any other level where it wouldn't be needed.

Now all this information needs to be labeled so there is a query ID attached to every request.

So if I send a response to a DNS and I get the query ID correct I can poison the DNS to into thinking that the query ID for that specific website and its IP is something other than that it actually is. This is called [[DNS Cache Poisoning]].