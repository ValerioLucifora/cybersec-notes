# 22 — IPv4 Subnet Masks

> 📚 **Course:** CompTIA Network+ (N10-009)
> 
> 📅 **Last modified:** 2026-08-05

---

## Introduction to Classless Subnetting

As of 1993, the networking system no longer uses classful subnetting (Class A, B, or C). In its place, **classless subnetting**, also known as **CIDR** (_Classless Inter-Domain Routing_), is employed, allowing for more flexible IP address management. This methodology enables the assignment of subnet masks that do not necessarily have to fit within the rigid patterns of the older default classes.

## CIDR Notation (Cider Block Notation)

Instead of always writing the subnet mask in decimal format (such as 255.255.255.0), **CIDR notation** is often used, which simply indicates the **number of bits** that make up the mask.

- For example, a decimal mask of 255.0.0.0 corresponds to **/8** notation, because it contains eight individual bits.
- An IP address written as 192.168.1.44**/24** indicates that the subnet mask has 24 active bits, which is equivalent to 255.255.255.0.

## Device Configuration

The choice of notation often depends on the device or operating system being configured.

- **Operating Systems (e.g., Windows):** Typically require the subnet mask to be entered in **decimal** format.
- **Routers and Switches:** Frequently use **CIDR notation** (e.g., /8 instead of 255.0.0.0). It is always essential to consult the device documentation to verify which format is preferred.

## Binary Structure of the Mask

A subnet mask consists of a **contiguous series of ones** (on the left) followed by a series of **zeros** (on the right).

- **Bits set to 1:** Represent the **network** portion of the address.
- **Bits set to 0:** Represent the **host** portion of the address.

For example, in a **/24** mask, there are 24 bits set to "1" and 8 bits set to "0," meaning the network portion is 24 bits long and the host portion is 8 bits long.

## Binary-to-Decimal Conversion

Since masks follow strict rules (contiguous bits), there are only certain decimal values that can appear in an octet. A reference table can be created to facilitate the conversion:

- 10000000 = 128
- 11000000 = 192
- 11100000 = 224
- 11110000 = 240
- 11111111 = 255.

## Calculation Examples

The video provides several practical examples for converting CIDR notation to decimal and vice versa:

- **/12:** Composed of 8 bits in the first octet and 4 in the second. In decimal, this is **255.240.0.0**.
- **/16:** Composed of 16 bits (two full octets of "1"s). In decimal, this is **255.255.0.0**.
- **/19:** Composed of 8+8+3 bits. In decimal, this is **255.255.224.0**.
- **/26:** Composed of 8+8+8+2 bits. In decimal, this is **255.255.255.192**.
- **/20:** Composed of 20 total bits (8+8+4), which translates to **255.255.240.0** in decimal format.
