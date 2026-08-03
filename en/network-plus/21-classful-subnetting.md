# 21 — Classful Subnetting

> 📚 **Course:** CompTIA Network+ (N10-009)
> 
> 📅 **Last modified:** 2026-08-03

---

## Classful Subnetting

Classful subnetting is a method of describing an IP address in relation to its **default subnet mask**. Although this system has not been officially used since 1993, it remains a fundamental concept because it serves as a **starting point** for understanding how to subdivide networks today.

## Address Classes and Subnet Masks

The system divides addresses into several main classes (A, B, and C), each with a clear demarcation between the portion of the address dedicated to the network and that dedicated to hosts.

- **Class A:** Addresses with a first octet between **0 and 127**. The default subnet mask is **255.0.0.0**, meaning the first 8 bits are for the network and the remaining 24 are for hosts.
- **Class B:** Addresses with a first octet between **128 and 191**. The default subnet mask is **255.255.0.0** (16 network bits, 16 host bits).
- **Class C:** Addresses with a first octet between **192 and 223**. The default subnet mask is **255.255.255.0** (24 network bits, 8 host bits).
- **Class D:** Addresses between **224 and 239**, used exclusively for **multicast** communication and not assigned to individual devices.
- **Class E:** Addresses between **240 and 255**, considered a **reserved** range for future or experimental purposes.

## Identification via Binary Bits

It is possible to determine the class of an address by looking at the initial bits of the first octet:

- **Class A:** The first bit is always **0**.
- **Class B:** The first two bits are **10**.
- **Class C:** The first three bits are **110**.
- **Class D:** The first four bits are **1110**.
- **Class E:** The first four bits are **1111**.

## The Four Key Values of a Subnet

When calculating an IP subnet, it is essential to identify four key values:

1. **Network Address:** Defines the subnet itself. It is calculated by setting all host bits to **zero**.
2. **First Usable Host Address:** This is always the numerical value immediately **after** the network address.
3. **Network Broadcast Address:** This is the last address in the subnet, used to send data to all devices simultaneously. It is calculated by setting all host bits to **one** (255 in decimal).
4. **Last Usable Host Address:** This is the numerical value immediately **before** the broadcast address.

## Practical Calculation Examples

### Class A Example (Address 10.74.22.11)

Since it starts with 10, it is a Class A with mask 255.0.0.0.

- **Network Address:** 10.0.0.0.
- **First Host:** 10.0.0.1.
- **Broadcast:** 10.255.255.255.
- **Last Host:** 10.255.255.254.

### Class B Example (Address 172.16.18.200)

It starts with 172, so it is Class B with mask 255.255.0.0.

- **Network Address:** 172.16.0.0.
- **First Host:** 172.16.0.1.
- **Broadcast:** 172.16.255.255.
- **Last Host:** 172.16.255.254.

### Class C Example (Address 192.168.4.77)

It starts with 192, so it is Class C with mask 255.255.255.0.

- **Network Address:** 192.168.4.0.
- **First Host:** 192.168.4.1.
- **Broadcast:** 192.168.4.255.
- **Last Host:** 192.168.4.254.
