# 02 — Network Devices

> 📚 **Course:** CompTIA Network+ (N10-009)
> 
> 📅 **Last modified:** 2026-08-02

---

## 1. Routing and Switching Devices

**Router (OSI Layer 3)** The router is one of the most common devices and operates at **Layer 3 (Network Layer)** of the OSI model. Its primary function is to route data between different IP subnets, whether they are in the same data center or in different parts of the world. To determine the next "hop" for the information, the router uses **IP addresses**. These devices often connect different types of networks, such as a LAN (Local Area Network) to a WAN (Wide Area Network), using copper or fiber‑optic interfaces.

**Switch (OSI Layer 2)** Switches operate at **Layer 2 (Data Link Layer)** and use **MAC addresses** to forward traffic. Their operation is primarily hardware‑based, using specialized integrated circuits called **ASICs** (Application Specific Integrated Circuits). Many enterprise switches support **PoE (Power over Ethernet)** technology, which allows electrical power to be transmitted over the same cables used for the Ethernet connection.

**Layer 3 Switch** In some cases, routing capabilities are integrated directly into a switch. These are called **Layer 3 switches**, because they combine the switching capabilities of Layer 2 and the routing capabilities of Layer 3 in the same piece of equipment.

## 2. Network Security

**Firewall** Traditional firewalls filter traffic based on TCP or UDP port numbers. Modern **Next‑Generation Firewalls (NGFW)** are capable of identifying the specific applications traversing the network. Firewalls often also act as routers (Layer 3), handling communication between the inside and outside of the network, and supporting features such as **NAT (Network Address Translation)**, VPNs for encrypted traffic, and dynamic routing protocols.

**IDS and IPS** These systems look for incoming attacks by identifying common threats such as operating system exploits or application vulnerabilities (e.g., buffer overflows or cross‑site scripting).

- **IDS (Intrusion Detection System):** Monitors traffic and generates an alarm or alert if it detects an attack.
- **IPS (Intrusion Prevention System):** Goes beyond simple alerting and is capable of **blocking the attack** before it enters the network.

## 3. Traffic Optimization and Control

**Load Balancer** The load balancer distributes traffic across multiple physical servers to ensure the availability of high‑traffic sites. If a server fails, the load balancer removes it from the rotation, maintaining service availability through the remaining servers. It can also optimize communications via **TCP offloading**, handle encryption (SSL offload), perform data caching, and prioritize certain types of traffic through **QoS (Quality of Service)**.

**Proxy** A proxy acts as an intermediary between the user and the internet. It receives the user's requests, executes them on the user's behalf, checks that the response does not contain malicious software, and finally delivers it to the user. It can be **explicit** (requires configuration on the device) or **transparent** (operates invisibly). Proxies are useful for response caching, URL filtering, and content scanning.

## 4. Network Storage

**NAS (Network Attached Storage)** NAS provides **file‑level** access. This means that to modify a file, the entire document must be transferred to the system's memory and, once modified, rewritten entirely to the NAS.

**SAN (Storage Area Network)** SAN is more efficient for large files because it provides **block‑level** access. This allows only the specific blocks of data that have been changed to be modified, without having to copy the entire file. Both NAS and SAN are typically isolated on high‑bandwidth networks.

## 5. Wireless Connectivity

**Access Point (AP)** An access point enables wireless communication and acts as a bridge between the wireless network (802.11) and the wired Ethernet network (802.3), operating at **Layer 2 (OSI)**. Unlike home routers, enterprise APs are dedicated devices with a single function.

**Wireless LAN Controller (WLC)** In large enterprises with many APs, the WLC serves as a centralized management tool. It allows configuration, monitoring, and updating of all access points from a single interface, also facilitating user **roaming** between different areas of the building without losing connectivity. Generally, these systems are proprietary: the access point and the controller must be from the same manufacturer.
---
