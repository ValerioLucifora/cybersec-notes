# 24 — Magic Number Subnetting

> 📚 **Course:** CompTIA Network+ (N10-009)
> 
> 📅 **Last modified:** 2026-08-06

---

## Introduction to Fast Subnetting

Traditional subnetting often requires converting IP addresses and subnet masks into binary format, a process that can be time-consuming and error-prone. The **Magic Number** method is a shortcut that allows you to quickly calculate the fundamental network information (Subnet ID, broadcast address, and host range) using only powers of two and simple arithmetic operations, often performable mentally.

## Calculation Objectives

Applying this method aims to obtain four essential pieces of information for each subnet:

1. **Subnet ID (or Network Address):** The first address of the subnet.
2. **Broadcast Address:** The last address of the subnet.
3. **First usable host:** The first address assignable to a device (Subnet ID + 1).
4. **Last usable host:** The last address assignable to a device (Broadcast - 1).

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

**Formula:** 256 − interesting_octet_value = Magic_Number

This number represents the size of the address block (including network ID and broadcast) for each subnet.

### 3. Determine the Subnet ID

To find the Subnet ID in the interesting octet, locate the multiple of the Magic Number that is closest (without exceeding) to the value of the corresponding octet in the IP address.

- _Example:_ If the IP in the interesting octet is 77 and the Magic Number is 16, the blocks are 0, 16, 32, 48, 64, 80. The 77 falls within the block starting at **64**.

### 4. Calculate the Broadcast Address

Once the Subnet ID for the interesting octet is known, calculate the broadcast using the following formula:

**Formula:** Subnet_ID + Magic_Number − 1 = Broadcast

For the other octets:

- If the mask was 255, copy the value from the Subnet ID.
- If the mask was 0, the broadcast octet will be **255**.

---

## Summary Practical Example

Consider the IP **10.180.122.244** with mask **255.248.0.0**:

1. **Interesting Octet:** The second (value 248).
2. **Magic Number:** 256 − 248 = 8.
3. **Subnet ID:** The IP in the interesting octet is 180. The multiples of 8 near 180 include 176 (8x22). The Subnet ID is therefore **10.176.0.0**.
4. **Broadcast:** 176(Subnet_ID) + 8(Magic_Number) − 1 = 183. The final broadcast is **10.183.255.255**.
5. **Hosts:** The first host is **10.176.0.1** and the last is **10.183.255.254**.
