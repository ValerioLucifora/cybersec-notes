# 20 — IPv4 Addressing

> 📚 **Course:** CompTIA Network+ (N10-009)
> 
> 📅 **Last modified:** 2026-08-02

---

## **1. Introduction to IPv4 Addressing**

- **Definition and Uniqueness:** An IPv4 address is the unique identifier that every device must have to communicate on a network that uses the IP protocol.
- **Format:** It appears as a series of four numbers separated by dots (e.g., 192.168.1.165).
- **Subnet Mask:** This is a four-octet value (e.g., 255.255.255.0) used together with the IP address to determine which subnet the device belongs to.
- **Function of the Subnet Mask:** It is not transmitted over the network; it is used locally by the device to determine which other addresses are local and which are outside its own subnet.

## **2. Gateway and Special Addresses**

- **Default Gateway:** This is the IP address of a device (usually a router) located on the local subnet that enables communication with external networks. It must be part of the local network.
- **Loopback Address:** This serves to define the local device without knowing its specific IP and is useful for verifying that the IP stack is functioning correctly. The range is from 127.0.0.1 to 127.255.255.255.
- **Reserved Addresses:** There is a range of addresses (from 240.0.0.1 to 254.255.255.255), including Class E addresses, reserved for future use or testing and should never be assigned to devices.
- **Virtual IP (VIP):** These are addresses not associated with a physical Ethernet adapter, but assigned internally to a device, such as a virtual machine, in order to reference it consistently.

## **3. Technical Structure of the IPv4 Address**

- **OSI Layer:** The IPv4 protocol operates at **Layer 3 (Network Layer)** of the OSI model.
- **Bit Composition:** An IPv4 address consists of a total of **32 bits**, which corresponds to 4 bytes or 4 octets.
- **Octets:** Each octet is composed of 8 bits; for this reason, the maximum decimal value that each group can reach is 255.

## **4. Configuration Methods**

- **Manual Configuration:** In the past, the IP address, subnet mask, and gateway had to be entered manually on each individual device.
- **DHCP (Dynamic Host Configuration Protocol):** This is the modern protocol that automatically assigns all IP configuration settings when a device connects to a wired or wireless network.
- **APIPA (Automatic Private IP Addressing):** If a DHCP server is not available, the device automatically assigns itself a "link-local" address through the APIPA process.
- **APIPA Limitations:** APIPA addresses (in the range 169.254.1.0 - 169.254.254.255) allow communication only with other devices on the local subnet and cannot access the Internet. The system uses ARP to ensure that no other device on the network is already using that address.

## **5. Private Addresses and NAT**

- **Address Scarcity:** Since the available IPv4 addresses worldwide have been exhausted, strategies have been developed to extend their functionality.
- **Private IP Addresses:** These are address ranges usable only within an enterprise or home network and are not routable on the public Internet.
- **NAT (Network Address Translation):** This is the feature that allows a private IP address to be translated into a public address, enabling internal devices to communicate over the Internet.
- **RFC 1918 Standard:** This is the document that defines the three private address ranges:
    - **10.0.0.0 - 10.255.255.255:** A single Class A block (/8) with over 16 million addresses.
    - **172.16.0.0 - 172.31.255.255:** 16 contiguous Class B blocks (/12) with approximately 1 million addresses.
    - **192.168.0.0 - 192.168.255.255:** 256 contiguous Class C blocks (/16) with over 65,000 addresses.
