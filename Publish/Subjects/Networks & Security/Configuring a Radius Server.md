---
Title: Configuring a Radius Server
Status: true
marker:
  - "[[Network Security Index]]"
tags:
Date: 2025.09.10
Time: 11:25
---
# Title

**Configuring 802.1X Authentication using RADIUS in Cisco Packet Tracer**

---

## Aim

To configure and verify **802.1X port-based authentication** on a Cisco switch using a **RADIUS server** and a **client PC** in Cisco Packet Tracer.

---

## Tools Required

* **Cisco Packet Tracer** → Network simulation environment.
* **Switch (2960)** → Provides access ports for client devices.
* **RADIUS Server** → Handles AAA (Authentication, Authorization, Accounting).
* **Client PC** → Connects to the switch and requests authentication.
* **Command Line Interface (CLI)** → For configuring the switch.

---

## Explanation of Tools

* **RADIUS Server** → Centralized authentication system.

  * Checks user credentials (username & password).
  * Authorizes or denies client access.
  * Provides logging (accounting).

* **Switch (2960)** → Acts as the authenticator.

  * Forwards client login requests to the RADIUS server.
  * Grants or blocks network access based on RADIUS response.

* **Client PC** → The device that requests access.

  * Provides credentials (e.g., username: student, password: cisco123).
  * Only gets network access if authenticated.

* **CLI** → Used to configure:

  * Switch IP address.
  * AAA (Authentication, Authorization, Accounting).
  * RADIUS server details.
  * 802.1X authentication on switch ports.

---

## Steps

### Step 1: Configure the RADIUS Server

1. Add a **server** device in Packet Tracer.
2. Assign IP configuration:

   * IP Address: **192.168.1.10**
   * Subnet Mask: **255.255.255.0**
   * Gateway: **192.168.1.1**
3. Go to **Services → AAA** → Enable AAA.
4. Add a new user:

   * Username: **student**
   * Password: **cisco123**
5. Set **Shared Secret**: **radiuskey**

---

### Step 2: Configure the Switch (CLI)

```cisco
Switch> enable
Switch# configure terminal

! Configure management IP
Switch(config)# interface vlan 1
Switch(config-if)# ip address 192.168.1.1 255.255.255.0
Switch(config-if)# no shutdown

! Enable AAA
Switch(config)# aaa new-model

! Configure RADIUS server
Switch(config)# radius-server host 192.168.1.10 key radiuskey

! Enable 802.1X globally
Switch(config)# dot1x system-auth-control

! Configure interface for authentication
Switch(config)# interface fastethernet 0/1
Switch(config-if)# authentication port-control auto
Switch(config-if)# dot1x pae authenticator

! Save configuration
Switch(config-if)# end
Switch# write memory
```

---

### Step 3: Configure the Client PC

1. Assign IP:

   * IP Address: **192.168.1.20**
   * Subnet Mask: **255.255.255.0**
   * Gateway: **192.168.1.1**
2. Go to **Desktop → 802.1X**.
3. Enable **802.1X Authentication**.
4. Enter credentials:

   * Username: **student**
   * Password: **cisco123**
5. Click **Connect**.

---

### Step 4: Verification

* On switch, run:

  ```cisco
  Switch# show dot1x all
  ```
* With **correct credentials** → client is authorized.
* With **wrong credentials** → authentication fails.
* Ping from client to RADIUS server:

  ```sh
  ping 192.168.1.10
  ```
* Verify connectivity and access status.

---

## Conclusions

* Configured **RADIUS server** for centralized authentication.
* Enabled **802.1X port-based authentication** on Cisco switch.
* Successfully authenticated the client PC with valid credentials.
* Verified denial of access when incorrect credentials were used.
* Understood that RADIUS ensures only **authorized devices** gain access, improving **network security**.
---

# References


###### Information
- date: 2025.09.10
- time: 11:25