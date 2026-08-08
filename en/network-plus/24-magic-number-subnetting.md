# 24 — Magic Number Subnetting

> 📚 **Course:** CompTIA Network+ (N10-009)
> 
> 📅 **Last modified:** 2026-08-08

---
## Introduction to Fast Subnetting

Traditional subnetting often requires converting IP addresses and subnet masks into binary format, a process that can be time-consuming and error-prone. The **Magic Number** method is a shortcut that allows you to quickly calculate the fundamental network information (Subnet ID, broadcast address, and host range) using only powers of two and simple arithmetic operations, often performable mentally.

## Calculation Objectives

Applying this method aims to obtain four essential pieces of information for each subnet:

1. **Subnet ID (or Network Address):** The first address of the subnet.
2. **Broadcast Address:** The last address of the subnet.
3. **First usable host:** The first address assignable to a device (Subnet ID + 1).
4. **Last usable host:** The last address assignable to a device (Broadcast - 1).

## Example 0: Determining the correct mask for your requirements

Before calculating addresses, the video shows how to choose the appropriate subnet mask.

- **Scenario:** You have the network **192.168.1.0/24** and need to support at least **40 devices** per subnet.
- **Reasoning:**
    - With **/24** (255.255.255.0) you have 1 network with 254 hosts. Too many hosts, too few networks.
    - With **/25** (255.255.255.128) you have 2 networks with 126 hosts. Still too many hosts.
    - With **/26** (255.255.255.192) you have 4 networks with **62 hosts** (calculated as 26−2). This number is perfect because it covers the required 40 while leaving some margin.
    - With **/27** (255.255.255.224) you would have 8 networks but only 30 hosts each, which is insufficient.


| Decimal Subnet Mask | Binary Subnet Mask                  | CIDR Notation | Networks | Hosts |
| ------------------- | ----------------------------------- | ------------- | -------- | ----- |
| 255.255.255.0       | 11111111.11111111.11111111.00000000 | /24           | 1        | 254   |
| 255.255.255.128     | 11111111.11111111.11111111.10000000 | /25           | 2        | 126   |
| 255.255.255.192     | 11111111.11111111.11111111.11000000 | /26           | 4        | 62    |
| 255.255.255.224     | 11111111.11111111.11111111.11100000 | /27           | 8        | 30    |
| 255.255.255.240     | 11111111.11111111.11111111.11110000 | /28           | 16       | 14    |
| 255.255.255.248     | 11111111.11111111.11111111.11111000 | /29           | 32       | 6     |


---

## Preparation and Useful Tools

Before starting the calculations, it is helpful to be familiar with some reference tables that speed up the process:

- **CIDR-to-Decimal Conversion:** Knowing which decimal value corresponds to a CIDR notation (e.g., /25 = 128, /26 = 192, /27 = 224).
- **Identifying the Interesting Octet:** Knowing in which octet the mask falls based on the CIDR:
    - Octet 2: from /9 to /16.
    - Octet 3: from /17 to /24.
    - Octet 4: from /25 to /30.
- **Range Table (Host Blocks):** Visualizing the blocks based on the number of hosts (e.g., blocks of 64: 0-63, 64-127, etc.).

---

## The Steps of the "Magic Number" Method

### 1. Identify the Interesting Octet

The **interesting octet** is the one in which the subnet mask value is neither 255 nor 0.

- If the mask octet is **255**, the corresponding IP octet is copied as-is into the Subnet ID.
- If the mask octet is **0**, the corresponding octet in the Subnet ID will always be 0.

### 2. Calculate the Magic Number

The "Magic Number" is obtained by subtracting the decimal value of the interesting octet of the mask from **256**.

$$
Formula: 256 − interesting_octet_value = Magic_Number
$$

This number represents the size of the address block (including network ID and broadcast) for each subnet.

### 3. Determine the Subnet ID

To find the Subnet ID in the interesting octet, locate the multiple of the Magic Number that is closest (without exceeding) to the value of the corresponding octet in the IP address.

- _**Practical Example**:
	 - IP Address: 165.245.77.14
	 - Subnet Mask: 255.255.240.0
	 - Magic Number: 256-240=16


| Mask      | 255.    | 255.    | 240.           | 0    |
| --------- | ------- | ------- | ------------------ | ---- |
| Action    | copy    | copy    | **256-240=16** | zero |
| IP        | 165.    | 245.    | **77.**        | 14   |
| Subnet ID | 165.    | 245.    | **64.**        | 0    |

| 0   | 16  | 32  | 48  | 64  | 80  | 96  | 112 | 128 | 144 | 160 | 176 | 192 | 208 | 224 | 240 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
- 77 falls within the range between 64 and 79, so we take the smaller number (following the rule of rounding down).

### 4. Calculate the Broadcast Address

Once the Subnet ID for the interesting octet is known, calculate the broadcast using the following formula:

$$
Formula: Subnet_ID + Magic_Number − 1 = Broadcast
$$

For the other octets:

- If the mask was 255, copy the value from the Subnet ID.
- If the mask was 0, the broadcast octet will be **255**.

- _**Practical Example**:
	- IP Address: 165.245.77.14
	- Subnet Mask: 255.255.240.0
	- Subnet ID: 165.245.64.0


| Mask      | 255.    | 255.    | **240.**       | 0    |
| --------- | ------- | ------- | ---------- | ---- |
| Action    | copy    | copy    | **256-240=16** | zero |
| Subnet ID | 165.    | 245.    | **64.**        | 0    |
| Broadcast | 165.    | 245.    | **79.**        | 255  |

- Calculation: Subnet ID + Magic Number - 1 = 64+16-1=**79**

---
