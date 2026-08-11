# 26 — Software Designed Networking (SND)

> 📚 **Course:** CompTIA Network+ (N10-009)
> 
> 📅 **Last modified:** 2026-08-11

---

## Introduction to Network Virtualization

One of the primary challenges in the virtual world is transferring the functions of physical devices (such as routers, switches, and firewalls) into a **virtualized environment**. By creating software versions of hardware functions, these capabilities can be deployed anywhere within a virtual environment, offering additional flexibility and functionality to the network.

---

## The Three Networking Planes

To understand how a networking device (physical or virtual) operates, its capabilities are divided into three distinct levels or "planes":

- **Data Plane (Infrastructure Layer):** This is the part of the device that performs the "heavy lifting" of **traffic forwarding**. It is responsible for moving information from one interface to another and handles functions such as trunking, encryption, and Network Address Translation (NAT). In a firewall, this plane corresponds to the physical interfaces to which the networks are connected.
- **Control Plane (Control Layer):** This layer determines **where data should go**. It contains the routing tables, switching tables, and all the logic that controls the device's operation and forwarding decisions.
- **Management Plane (Application Layer):** This is the layer used by the network administrator to **manage the device**. It is accessed whenever you use an SSH connection, a console, or a web interface to configure the appliance.

---

## Software Defined WAN (SD-WAN)

**SD-WAN** is the application of software-defined networking concepts to wide area networks (WANs), specifically designed to manage the complexities of **cloud**‑based environments.

The Shift from Data Center to Cloud

In the past, all resources (email, databases, applications) were concentrated in a single central data center, making WAN connections from remote sites straightforward. Today, because services have moved to the cloud and can be located anywhere in the world, connectivity has become more complex.

## Key Features of SD-WAN:

- **Application Aware:** SD-WAN recognizes which application is transmitting data (for example, an email or a database) and forwards the traffic to the nearest cloud service that is specific to that user.
- **Zero-touch provisioning:** Allows remote routers and switches to **update themselves automatically** in response to network changes or changes in service location, without requiring manual intervention from administrators.
- **Transport agnostic:** The technology is designed to operate independently of the type of physical connection used, whether it is high‑speed fiber optics, 5G, or DSL.
- **Centralized policy management:** Instead of configuring each individual router, the administrator defines policies on a **central console**; these changes are then automatically pushed to all SD-WAN devices on the network.

## Operational Benefits

The use of SD-WAN technology enables users in remote sites to directly access cloud services (such as email or databases) in an optimized manner, while still maintaining the ability to connect directly to the central data center when necessary.
