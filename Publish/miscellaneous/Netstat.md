---
Title: Netstat
Status: 
marker: 
tags: 
Date: 2024.08.06
Time: 18:03
---
# Index
- [[Netstat]]
  - [Common Output](#Common-Output)
  - [Common Usage](#common-usage)
  - [Examples](#examples)
  - [Summary](#summary)
- [References](#references)


The `netstat` command is a network utility tool available in various operating systems, including Windows, Linux, and macOS. It provides detailed information about network connections, routing tables, interface statistics, masquerade connections, and multicast memberships. Here are some common usages and options:

To not study a detailed output just checkout common output and brief each title vaguely.
For the rest u can jump to [[Netstat#Common Usage|Common Netstat Usage]] and [[Netstat#Summary|Summary]]
### Common Output
   ```shell
$ netstat -a
Active Internet connections (servers and established)
Proto Recv-Q Send-Q Local Address           Foreign Address         State
tcp        0      0 localhost:domain        *:*                     LISTEN
tcp        0      0 *:ssh                   *:*                     LISTEN
tcp        0      0 localhost:ipp           *:*                     LISTEN
tcp        0      0 192.168.1.5:ssh         192.168.1.10:59382      ESTABLISHED
udp        0      0 localhost:domain        *:*                     
udp        0      0 *:bootpc                *:*                     
udp        0      0 192.168.1.5:ntp         *:*                     
udp        0      0 localhost:ntp           *:*                     
udp        0      0 *:ntp                   *:*                     

Active UNIX domain sockets (servers and established)
Proto RefCnt Flags       Type       State         I-Node   Path
unix  2      [ ACC ]     STREAM     LISTENING     12345    /var/run/dbus/system_bus_socket
unix  2      [ ACC ]     STREAM     LISTENING     67890    /tmp/.X11-unix/X0
unix  2      [ ]         DGRAM                    13579    /run/systemd/notify
unix  3      [ ]         STREAM     CONNECTED     24680    /run/systemd/journal/stdout
```

- **Proto:** Protocol being used (e.g., [[TCP]], [[UDP]]).
- **Recv-Q:** The count of bytes not copied by the user program connected to this socket.
- **Send-Q:** The count of bytes not acknowledged by the remote host.
- **Local Address:** The address and port number of the local end of the connection.
- **Foreign Address:** The address and port number of the remote end of the connection.
- **State:** The state of the connection (e.g., LISTEN, ESTABLISHED).

##### Example 
- **Protocol:** [[TCP]]
- **Recv-Q:** 0 (no bytes waiting to be read)
- **Send-Q:** 0 (no bytes waiting to be acknowledged)
- **Local Address:** localhost (local machine) on port `domain` (53, typically used for DNS)
- **Foreign Address:** `*:*` (listening for any incoming connection)
- **State:** LISTEN (the socket is waiting for a connection)
```shell
tcp        0      0 localhost:domain        *:*                     LISTEN
```

- **Protocol:** [[TCP]]
- **Recv-Q:** 0 (no bytes waiting to be read)
- **Send-Q:** 0 (no bytes waiting to be acknowledged)
 - **Local Address:** 192.168.1.5 (local machine) on port `ssh` (22)
 - **Foreign Address:** 192.168.1.10 on port 59382 (the remote machine connected to this SSH session)
- **State:** ESTABLISHED (the connection is active)
```shell
tcp        0      0 192.168.1.5:ssh         192.168.1.10:59382      ESTABLISHED

```

- **Protocol:** UDP
- **Recv-Q:** 0 (no bytes waiting to be read)
- **Send-Q:** 0 (no bytes waiting to be acknowledged)
- **Local Address:** 192.168.1.5 on port `ntp` (123, used for Network Time Protocol)
- **Foreign Address:** `*:*` (listening for any incoming packet)

```shell
udp        0      0 192.168.1.5:ntp         *:*                     
```
### Common Usage

1. **Displaying All Connections:**
   ```sh
   netstat -a
   ```
   This option displays all active connections and listening ports.

2. **Displaying Listening Ports:**
   ```sh
   netstat -l
   ```
   This option shows only the listening [[ports|port]].

3. **Displaying Network Statistics:**
   ```sh
   netstat -s
   ```
   This option displays network statistics for each protocol.

4. **Displaying Routing Table:**
   ```sh
   netstat -r
   ```
   This option shows the routing table.

5. **Displaying Interface Statistics:**
   ```sh
   netstat -i
   ```
   This option provides statistics for network interfaces.

6. **Displaying PID and Program Names (Linux only):**
   ```sh
   netstat -p
   ```
   This option shows the PID and program names for each connection.

### Combining Options

You can combine options to get more specific information. For example:

- Display all listening [[TCP]] ports and their corresponding process IDs:
  ```sh
  netstat -ltp
  ```

- Display all active connections with numeric addresses:
  ```sh
  netstat -an
  ```

### Windows Specific Options

In Windows, `netstat` has some additional options:

- **Displaying the Executable Involved in Creating Each Connection or Listening Port:**
  ```sh
  netstat -b
  ```

- **Displaying Ethernet Statistics:**
  ```sh
  netstat -e
  ```

- **Refreshing Every Interval of Seconds:**
  ```sh
  netstat -e [interval]
  ```

### Examples

- To display all active [[TCP]] connections:
  ```sh
  netstat -at
  ```

- To display all active [[UDP]] connections:
  ```sh
  netstat -au
  ```

- To display detailed information about the connections, including the address, port, and state:
  ```sh
  netstat -an
  ```

`netstat` is a powerful tool for network diagnostics and troubleshooting, helping administrators understand and manage network connections and activity on their systems.


## Summary

`netstat -a ` in most operating systems shows networking information that is available about network connections. They are mostly:
- **Proto:** Protocol being used (e.g., TCP, UDP).
- **Recv-Q:** Bytes not yet copied by the user program. ( Received Byte Count from the program using that port )
- **Send-Q:** Bytes not yet acknowledged by the remote host. ( Bytes that the other receiving end didn't count / use from the sent packets from that specific port)
- **Local Address:** Local address and port number. ( Local Address of the port )
- **Foreign Address:** Remote address and port number. ( Foreign address if any )
- **State:** Connection state (e.g., LISTEN, ESTABLISHED). ( [[Half Duplex]] / [[Half Duplex]])


---

# References
- [[UDP]]
- [[TCP]]
###### Information
- date: 2024.08.06
- time: 18:03