# 30 — IPv6 Addressing

> 📚 **Course:** CompTIA Network+ (N10-009)
> 
> 📅 **Last modified:** 2026-08-17

---

## **1. The Need for the Transition to IPv6**

### **IPv4 Address Exhaustion**
It is currently estimated that there are about **20 billion devices connected to the Internet**, but the **IPv4 protocol can only support 4.29 billion**. To overcome this limitation, methods such as **NAT (Network Address Translation)** have been used, which allows hundreds or thousands of devices to connect using a minimal number of public IPv4 addresses. However, IPv4 addresses are now exhausted and NAT adds technical complexity that some applications would prefer to avoid.

### **The IPv6 Solution**
IPv6 was created to definitively solve this constraint. While IPv4 addresses are 32 bits long, **IPv6 addresses are 128 bits**, offering a vastly larger addressing space. To give an idea of the scale, every grain of sand on Earth could have 45 quintillion unique IPv6 addresses.

---

## **2. Structure and Format of the IPv6 Address**

### **Technical Characteristics**
Unlike IPv4, which uses decimal numbers and dots, IPv6 uses **hexadecimal values separated by colons (:)**. A full 128-bit address is composed of **8 sections**, each of which:

- Is **16 bits** long.
- Equals **2 bytes** (or two octets).

### **Example Address**

fe80::5d18:652:6ffd:8f52

---

## **3. Address Compression Rules**

Since writing 128 bits in hexadecimal can be complex, there are two fundamental rules to abbreviate them:

- **Removal of leading zeros:** Within each group, zeros that precede other numbers can be omitted (e.g., `0001` becomes `1`).
- **Abbreviation with double colon:** If there are two or more consecutive groups consisting entirely of zeros, they can be replaced by a double colon. This operation can be performed **only once** per address to avoid ambiguity.

- **Compression Example 1:**
    - _Original address:_ `2600:dddd:1111:0001:0000:0000:0000:0001`.
    - _Process:_ Leading zeros are removed (e.g., `0001` becomes `1`) and the three consecutive zero groups are replaced by the double colon (`::`).
    - _Final result:_ **2600:dddd:1111:1::1**.
- **Compression Example 2:**
    - _Original address:_ `2601:04C3:4002:be00:0000:0000:0000:0066`.
    - _Process:_ Leading zeros are removed and the three final zero blocks are collapsed.
    - _Final result:_ **2601:4C3:4002:be00::66**.

---

## **4. Migration and Coexistence Strategies**

Since IPv4 and IPv6 cannot communicate directly with each other, strategies are needed to enable legacy systems to coexist with modern ones.

### **Tunneling (6to4 and 4in6)**
Tunneling consists of encapsulating the traffic of one protocol within the other (e.g., IPv6 inside IPv4) to traverse networks that do not support the original protocol.

- The **6to4** method creates an IPv6 address based on the existing IPv4 address, but requires specialized relay routers and does not support NAT.
- Today, tunneling is considered a short-term solution and is no longer common in modern enterprise networks; for example, support for 6to4 has been removed from recent versions of Windows.

### **Dual Stack**
This is the most common migration method. It consists of configuring a system (e.g., a network interface card) to have **both an IPv4 address and an IPv6 address assigned simultaneously**. The system will use independent routing tables and settings for each protocol, allowing applications to choose which version to use based on network availability.

---

## **5. Translation: NAT64 and DNS64**

When a pure IPv6 device needs to communicate with a pure IPv4 one, translation via **NAT64** is used.

- **NAT64:** A specialized router translates packets between the two protocols transparently.
- **DNS64:** It is a fundamental component of this process. When an IPv6 client requests the address of a server that only supports IPv4, the DNS64 server receives the IPv4 response and creates a synthetic IPv6 version of that address. This "fake" address redirects the client's traffic to the NAT64 router, which then performs the final translation to the destination IPv4 server.
