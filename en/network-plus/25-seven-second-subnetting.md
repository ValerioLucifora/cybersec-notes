# 25 — Seven Second Subnetting

> 📚 **Course:** CompTIA Network+ (N10-009)
> 
> 📅 **Last modified:** 2026-08-08

---

## **Introduction to the "Seven Second Subnetting" Method**

"Seven Second Subnetting" is a shortcut technique designed to calculate subnet parameters extremely quickly during certification exams. Unlike the traditional method, which requires manual binary conversion, this system relies on a **predefined table** created at the start of the exam session.

The only mathematical calculation required is adding or subtracting the value **1** to determine the first and last usable IP addresses. This method is effective whether you are using a physical whiteboard at a test center or a virtual whiteboard online.

---

## **Building the Reference Table**

The core of this process is constructing a table that allows instant translation between CIDR notations and dotted‑decimal masks, and vice versa.


| Masks (CIDR) | Masks (CIDR) | Masks (CIDR) | Masks (CIDR) | Masks (decimal) | Networks | Addresses |
| ------------ | ------------ | ------------ | ------------ | --------------- | -------- | --------- |
| /1           | /9           | /17          | /25          | 128             | 2        | 128       |
| /2           | /10          | /18          | /26          | 192             | 4        | 64        |
| /3           | /11          | /19          | /27          | 224             | 8        | 32        |
| /4           | /12          | /20          | /28          | 240             | 16       | 16        |
| /5           | /13          | /21          | /29          | 248             | 32       | 8         |
| /6           | /14          | /22          | /30          | 252             | 64       | 4         |
| /7           | /15          | /23          | /31          | 254             | 128      | 2         |
| /8           | /16          | /24          | /32          | 255             | 256      | 1         |


---

## **The Four‑Step Process**

Once the table is ready, calculating any subnet follows four logical steps:

- **Step 1: Convert the mask.** Translate the CIDR notation (e.g., /26) into dotted‑decimal format (e.g., 255.255.255.192) using the table.
- **Step 2: Determine the network address.** Identify the starting address of the subnet that contains the given IP.
- **Step 3: Determine the broadcast address.** Find the last address within the subnet range.
- **Step 4: Calculate the usable IPs.** Determine the first usable IP by adding 1 to the network address and the last usable IP by subtracting 1 from the broadcast address.

---

## **Practical Rules for Octets**

To speed up calculations, fixed rules are applied based on the subnet mask value in each octet:

- **If the mask is 255:** Simply copy the original IP address number for that octet.
- **If the mask is 0:**
    - For the **network address**, write **0**.
    - For the **broadcast address**, write **255**.
- **If the mask is an intermediate value (e.g., 192, 224, 240):** Consult the "boundary" table to see which block your IP number falls into, then use the start of the block for the network address and the end of the block for the broadcast address.

---

## **Practical Example: 8‑bit (/24) Subnetting**

- **Starting IP:** 165.245.12.88/24
- **CIDR:** /24
- **Mask Conversion:** Looking at the table, a /24 corresponds to **255.255.255.0**.
- **Network Address:** Apply the rules: where the mask is 255, copy the IP number; where it is 0, write 0.
    - Result: **165.245.12.0**.
- **Broadcast Address:** Where the mask is 255, copy the IP number; where it is 0, write 255.
    - Result: **165.245.12.255**.
- **Usable IPs:** Add 1 to the network address and subtract 1 from the broadcast address.
    - First IP: 165.245.12.1; 
    - Last IP: 165.245.12.254.
