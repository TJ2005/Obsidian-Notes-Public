---
Title: SSL
Status: 
marker: 
tags: 
Date: 2025.08.07
Time: 12:14
---
# SSL

> [!Info]
> We will look at [[SSL]] represented into a timeline as it has been deprecated and [[TLS]] is its new replacement.


## SSL 2.0 

### Core Functions:

* Allowed client and server to agree on:
  * Encryption algorithm (e.g., RC2, RC4)
  * Key exchange method (usually [[RSA]])
* Performed a basic handshake
* Transmitted data with encryption and message integrity

```sql
Client                                      Server
  |                                            |
  |------> ClientHello (cipher list) --------->|
  |                                            |
  |<----- ServerHello (chosen cipher) ---------|
  |                                            |
  |---> ClientMasterKey (encrypted) ---------->|
  |                                            |
  |---> ClientFinished ----------------------->|
  |                                            |
  |<--- ServerVerify + ServerFinished ---------|
  |                                            |
  |==== Encrypted communication begins =======>|
```

### Notes:
* **ClientHello**: Lists supported cipher algorithms.
* **ServerHello**: Chooses a cipher suite.
* **ClientMasterKey**: A premaster secret, encrypted with server’s public key.
* **Finished messages**: Verify handshake completion.
* After this, both sides derive session keys and start encrypted communication.
### Vulnerability: **MITM + Downgrade Attack**
* SSL 2.0 didn't authenticate the handshake messages properly.
* No integrity check on handshake → attacker could modify messages.
### Attack Flow:
1. Attacker intercepts ClientHello, strips strong ciphers.
2. Server chooses weak cipher (e.g., 40-bit RC2).
3. Attacker breaks encryption using brute force → reads or alters data.

---

## SSL 3.0 — What It Did

### Core Functions:
* Redefined the protocol structure:
  * Split into **handshake**, **record**, **alert**, and **ChangeCipherSpec** protocols
* Added support for:
  * Cipher suite negotiation
  * Certificate-based authentication
  * Message authentication codes (MACs)
* Allowed fragmentation and reassembly of handshake messages

Here is a diagram representing the **RSA-based key exchange flow** (used in SSL 3.0 and TLS 1.0–1.2):
```
Client                                            Server
  |                                                  |
  | ---> ClientHello (version, random, cipher list)  |
  |                                                  |
  | <--- ServerHello (version, chosen cipher)        |
  | <--- Certificate (with server's public key)      |
  |                                                  |
  | ---> ClientKeyExchange (Premaster Secret, RSA-encrypted) |
  |                                                  |
  | ---> ChangeCipherSpec                             |
  | ---> Finished (encrypted with session key)        |
  |                                                  |
  | <--- ChangeCipherSpec                             |
  | <--- Finished (encrypted with session key)        |
  |                                                  |
  |======== Secure Communication Begins ==========>  |
```

---

### What's happening here:

* **ClientHello**: Says "Here's what I support."
* **ServerHello + Certificate**: Chooses cipher, sends public key.
* **ClientKeyExchange**: Sends encrypted premaster secret → server decrypts it.
* **Both derive session keys** based on:

  * Premaster Secret
  * ClientRandom
  * ServerRandom
* **ChangeCipherSpec + Finished**: Switch to encrypted communication and verify handshake.

Let me know if you want this **compared side-by-side with ECDHE** or **TLS 1.3**, which completely removes the `ChangeCipherSpec` and uses different message flow.

### Vulnerability: **POODLE (Padding Oracle Attack)**

* SSL 3.0 used block ciphers with **CBC mode** and **MAC-then-encrypt**.
* Padding wasn't properly checked → oracle leakage

### Attack Flow:

1. Attacker forces client to fall back to SSL 3.0 (via downgrade).
2. Attacker captures many encrypted messages.
3. Modifies ciphertext blocks to guess plaintext padding.
4. Repeats with byte-by-byte padding manipulation.
5. Eventually recovers plaintext (e.g., session cookie).

---

## Summary Table

| Version | Core Functional Changes                                  | Vulnerability               | Attack Flow Summary                        |
| ------- | -------------------------------------------------------- | --------------------------- | ------------------------------------------ |
| SSL 2.0 | Basic handshake, no handshake integrity, weak encryption | Downgrade, MITM             | Strip strong ciphers, force weak ones      |
| SSL 3.0 | Modular structure, certificate support, MACs             | POODLE (CBC Padding Oracle) | Modify CBC blocks, infer plaintext padding |

---



# References


###### Information
- date: 2025.08.07
- time: 12:14