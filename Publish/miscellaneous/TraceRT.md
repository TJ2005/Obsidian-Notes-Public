---
Title: TraceRT
Status: 
marker:
  - "[[Computer Networks]]"
tags: 
Date: 2024.08.06
Time: 18:25
---
### Definition
The `tracert` command (short for "trace route") is a network diagnostic tool used to track the pathway that a packet of data takes from your computer to a destination host, such as a website or server. It is available on Windows, while the equivalent command on Unix-like systems (Linux, macOS) is `traceroute`.

### Purpose and Usage
The primary purpose of `tracert` is to identify the route and measure the transit delays of packets across an IP network. It is helpful for diagnosing network connectivity issues and pinpointing where packets are being delayed or lost.

### How It Works

1. **Sending Packets with Incrementing TTL:**
   `tracert` works by sending a series of Internet Control Message Protocol (ICMP) Echo Request packets to the destination with varying Time-To-Live (TTL) values. The TTL value starts at 1 and increments by 1 with each subsequent packet.

2. **ICMP Time Exceeded Messages:**
   Each router that handles a packet decrements the TTL by 1. When the TTL reaches 0, the router discards the packet and sends an ICMP Time Exceeded message back to the source. This way, `tracert` can identify each hop along the path to the destination.

3. **Final Destination:**
   When the packet finally reaches the destination, it sends an ICMP Echo Reply message, indicating that the destination has been reached.

### Common Usage and Options

#### Basic Syntax

```sh
tracert [hostname or IP address]
```

#### Example

To trace the route to example.com:

```sh
tracert example.com
```

### Options

1. **-d**: Prevents `tracert` from resolving IP addresses to hostnames. This speeds up the process as DNS resolution is not performed.
   ```sh
   tracert -d example.com
   ```

2. **-h maximum_hops**: Specifies the maximum number of hops to search for the target (default is 30).
   ```sh
   tracert -h 15 example.com
   ```

3. **-w timeout**: Sets the timeout period (in milliseconds) for each reply (default is 4000 ms).
   ```sh
   tracert -w 1000 example.com
   ```

4. **-4**: Forces `tracert` to use IPv4.
   ```sh
   tracert -4 example.com
   ```

5. **-6**: Forces `tracert` to use IPv6.
   ```sh
   tracert -6 example.com
   ```

### Interpreting the Output

The output of `tracert` typically includes:

- **Hop Number**: The position in the path (starting at 1 for the first hop).
- **Round Trip Time (RTT)**: The time it takes for the packet to go to the hop and back, usually displayed in milliseconds.
- **IP Address**: The IP address of the router or gateway at that hop.
- **Hostname**: The resolved hostname (if DNS resolution is enabled).

Example output:

```
Tracing route to example.com [93.184.216.34] over a maximum of 30 hops:

  1    1 ms    1 ms    1 ms  192.168.1.1
  2   15 ms   14 ms   15 ms  203.0.113.1
  3   23 ms   23 ms   23 ms  198.51.100.1
  4   25 ms   25 ms   25 ms  example.com [93.184.216.34]

Trace complete.
```

### Conclusion

`tracert` is a valuable tool for network administrators and anyone troubleshooting network issues, providing insights into the path and performance of network routes to remote hosts.


# References


###### Information
- date: 2024.08.06
- time: 18:25