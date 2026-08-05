# 23 — Calculating IPv4 Subnets and Hosts

> 📚 **Course:** CompTIA Network+ (N10-009)
> 
> 📅 **Last modified:** 2026-08-05

---

## Introduction to Subnetting

The process of creating smaller networks is fundamental because it would be technically impossible for a single device to know the location of every other device in the world. Through subnetting, we create smaller networks connected by routers, which allow packets to be forwarded to their final destination without the sender needing to know the exact location of the recipient.

## Variable Length Subnet Masks (VLSM)

Unlike classful networks, which have a fixed number of bits in the subnet mask, **VLSM** allows for masks of variable length.

- **Flexibility:** Network administrators can create networks of the exact required size, deciding how many bits to allocate to the subnet and how many to hosts.
- **Pizza analogy:** Dividing a network with VLSM is like deciding how many slices to cut a pizza into: you can choose to divide it into two, four, eight, or more parts depending on your needs.

## The Concept of "Borrowing" Bits

To create subnets, bits are "borrowed" from what was originally the host portion of the IP address.

- **Class A Example:** A Class A address (such as 10.0.0.0) has a default prefix of **/8** (255.0.0.0).
- If we move the demarcation line (for example, to **/24**), we are borrowing 16 bits from the host portion to turn them into subnet bits.
- This reduces the available space for hosts, but dramatically increases the number of independent networks we can create.

## Formulas for Quick Calculation

Instead of constantly converting between binary and decimal, it is more efficient to use **powers of two**:

1. **Number of Subnets:** 2n (where _n_ is the number of bits borrowed for the subnet).
2. **Number of Hosts per Subnet:** (2h)−2 (where _h_ is the number of bits remaining for hosts).
    - _Note:_ We subtract 2 because each subnet must reserve one address for the **network address** and one for the **broadcast address**.

## Practical Calculation Examples

### 1. Address 10.1.1.0/24 (Modified Class A)

- **Class A Default:** /8 (8 network bits).
- **Bits Borrowed (Subnet):** 16 (since 24 - 8 = 16).
- **Remaining Host Bits:** 8 (since 32 - 24 = 8).
- **Calculation:**
    - Subnets: 216=65,536.
    - Hosts: (28)−2=254.

### 2. Address 192.168.1.0/26 (Modified Class C)

- **Class C Default:** /24 (24 network bits).
- **Bits Borrowed (Subnet):** 2 (26 - 24 = 2).
- **Remaining Host Bits:** 6 (32 - 26 = 6).
- **Calculation:**
    - Subnets: 22=4.
    - Hosts: (26)−2=62.

### 3. Address 172.16.5.0/21 (Modified Class B)

- **Class B Default:** /16 (16 network bits).
- **Bits Borrowed (Subnet):** 5 (21 - 16 = 5).
- **Remaining Host Bits:** 11 (32 - 21 = 11).
- **Calculation:**
    - Subnets: 25=32.
    - Hosts: (211)−2=2,046.

Using powers of two is a quick method, but there are additional shortcuts to further speed up these calculations in daily work.
