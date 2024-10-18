---
Title: Computer Networks Subnetting and Supernetting
Status: 
marker:
  - "[[btech]]"
  - "[[Computer Networks]]"
tags: 
Date: 2024.10.07
Time: 07:39
---
# Subnetting and Supernetting Notes

### **Information Needed to Solve the Problem**

To solve problems involving subnetting and determining the range of IP addresses, here’s the essential information you need:

1. **IP Address**: 
   - This is the starting point. In this case, it is given as **205.16.37.32** or **205.16.37.39**, depending on the example being worked on.

2. **Subnet Mask**: 
   - This tells us how many bits are allocated to the network portion versus the host portion of the IP address.
   - For example, a subnet mask of **28** means 28 bits are allocated for the network, and 4 bits are available for hosts.

3. **Number of IP Addresses**: 
   - The number of available IP addresses in a subnet is determined by the number of bits used for the host portion.
   - The formula for calculating the number of IP addresses is:

     $\text{Number of IP addresses} = 2^{\text{Number of Host Bits}}$

   - In a **28** subnet, 4 bits are available for hosts, which gives us $2^4 = 16$ IP addresses.

4. **Binary Conversion**: 
   - Understanding how to convert IP addresses into their binary form allows you to easily calculate the first and last address in a block.
   - Example: The IP address **205.16.37.32** is converted into binary, which gives:

     `11001101.00010000.00100101.00100000`

5. **First and Last Address Calculation**:
   - To find the **first address**, set the host bits to all zeros (`0`).
   - To find the **last address**, set the host bits to all ones (`1`).

---
### Key Concepts:

1. **Subnetting**: 
   - Increases the number of `1`s in the subnet mask.
   - Helps divide a network into smaller sub-networks (subnets).

2. **Supernetting**:
   - Increases the number of `1`s in the mask.
   - Combines multiple networks into a larger one.

---

### Problem 1:

#### **Description**:
A block of **16 addresses** is granted to a small organization. The first address is given as **205.16.37.32**, and the task is to find the binary representation of the first and last addresses in this block.

#### **Given**:
- First address: **205.16.37.32** (in binary: `11001101.00010000.00100101.00100000`)
- Last address: **205.16.37.47**

#### **Solution**:
1. Addresses are **contiguous**.
2. The number of addresses is a power of 2: **16 = 2^4**.
3. The first address is **divisible by 16** (starting from **205.16.37.32**).

---

### Problem 2:

#### **Description**:
A block of addresses is granted to a small organization. One of the addresses given is **205.16.37.39/28**. The task is to find the first address in this block.

#### **Solution**:

- Binary representation of the given address: **11001101 00010000 00100101 00100111**
- Using the subnet mask **/28**, we know there are **4 position zeros** for the host portion.

#### **First Address**:
- The first address in binary: `11001101 00010000 00100101 00100000`
- Therefore, the first address is **205.16.37.32**.

#### **Last Address**:
- Set the last 4 bits of the host portion to 1s for the last address.
- The last address is: **11001101 00010000 00100101 00101111**
- Therefore, the last address is **205.16.37.47**.

---

### Additional Method for Finding Addresses:

Given an IP address: **205.16.37.39/28**, we can calculate the number of addresses in the block using the formula:

\[
\text{Number of addresses} = 2^{32 - 28} = 2^4 = 16 \text{ addresses}
\]

The first address is **205.16.37.32**, and the last address is **205.16.37.47**.

---

### **Binary Representation of IP Addresses**:

For the address **205.16.37.32**:
- **205** in binary: `11001101`
- **16** in binary: `00010000`
- **37** in binary: `00100101`
- **32** in binary: `00100000`

The binary representation: `11001101.00010000.00100101.00100000`

Similarly, for **205.16.37.47**:
- **205** in binary: `11001101`
- **16** in binary: `00010000`
- **37** in binary: `00100101`
- **47** in binary: `00101111`

The binary representation: `11001101.00010000.00100101.00101111`

---

### Formula Recap:

- **First address**: Convert the IP address to binary, and set the host bits to 0.
- **Last address**: Convert the IP address to binary, and set the host bits to 1.


# References


###### Information
- date: 2024.10.07
- time: 07:39