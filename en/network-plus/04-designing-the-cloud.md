# 04 — Designing the Cloud

> 📚 **Course:** CompTIA Network+ (N10-009)
> 
> 📅 **Last modified:** 2026-08-02

---

## Virtual Networks in Cloud Computing

The evolution toward the cloud is not just about servers, but about the entire network infrastructure. When migrating physical servers to a cloud environment, it is necessary to virtualize the components that connect them as well.

## 1. Network Function Virtualization (NFV)

**Network Function Virtualization (NFV)** is the process of replacing physical network devices (such as routers, switches, and firewalls) with their virtual equivalents.

- **Unchanged functionality:** Although these devices are no longer physical, they retain the exact same capabilities. Interfaces and configurations can be managed directly through the **hypervisor**.
- **Flexibility and speed:** Just as a server can be spun up with a click, a new virtual firewall can be deployed instantly or a router's configuration can be modified within the virtualized environment.

## 2. Virtual Private Cloud (VPC)

A common cloud instance is the **Virtual Private Cloud (VPC)**. This is an isolated environment where specific applications run (for example, a web server and a database together with load balancers and virtual switches).

- **Isolation:** Companies use separate VPCs for different applications or departments to keep systems distinct while managing them as single virtual appliances.

## 3. Connectivity and Routing

To enable these virtual entities to communicate with each other or with the outside world, several tools are used:

- **Transit Gateway:** Functions as a "cloud router." It enables communication between different VPCs that would otherwise remain isolated.
- **Internet Gateway:** Allows applications to be accessed from anywhere in the world via the Internet.
- **VPC NAT Gateway:** Enables devices on private networks to reach the Internet (for example, for updates), but prevents external devices from initiating connections inward.
- **VPN (Virtual Private Network):** Provides secure access to a VPC from a remote site or a user's workstation, creating an encrypted tunnel.
- **VPC Endpoint:** Creates a direct connection between VPCs from different cloud providers, or between a VPC and cloud storage services, without traversing the public Internet.

## 4. Virtual Network Security

Security in the cloud is managed through rules based on protocols and ports (TCP/UDP) or IP addresses (Layer 3).

- **Network Security Lists:** These are firewalls applied to entire subnets. They are broad, but may lack precision because they apply the same rules to all virtual networks assigned to them.
- **Network Security Groups (NSG):** Offer greater **granularity**. They allow security rules to be assigned to individual virtual network interface cards (**vNICs**), enabling different rules for different interfaces within the same subnet.
- **Virtual Firewalls:** For even more advanced security beyond standard security groups, dedicated virtual firewall platforms can be implemented.
---
