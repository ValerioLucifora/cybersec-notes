# 17 — Network Topologies

> 📚 **Course:** CompTIA Network+ (N10-009)
> 
> 📅 **Last modified:** 2026-08-02

---

## Introduction to Network Topologies

Networks can be connected in many different ways, and the choice of topology is critical both during the **planning and design** phase and during **troubleshooting**. Understanding the topology allows you to visualize how a network connects to others and how data is transmitted between the various nodes.

## Star Topology (Star Network)

The star topology, sometimes called **Hub and Spoke**, is one of the most popular configurations in large enterprise networks for connecting devices to one another.

#### Operation and Characteristics

- **Central Device:** There is a central network component to which all other devices connect directly.
- **Practical Example:** A classic example is **switched Ethernet**, where a switch sits at the center and all devices connect to it.
- **Communication:** If two network nodes want to communicate, data must necessarily pass through the central component.

## Mesh Topology

In a mesh network, a device or site connects to another through **more than one network connection**.

#### Main Advantages

- **Redundancy:** If one link fails, an alternative path can be used to complete the communication.
- **Load Balancing:** Data can be distributed across the available links to optimize performance.
- **WAN Usage:** Although applicable to local area networks (LANs), mesh topology is very common in wide area networks (**WANs**) to ensure connectivity to remote sites regardless of failures on individual links.

## Hybrid Networks

In large enterprise networks, it is common to find different architectures used in different sections of the infrastructure. When multiple topologies are combined (e.g., a star portion, a mesh portion, and a point-to-point link), a **hybrid network** is created.

## Spine and Leaf Architecture

Many modern data centers use the **Spine and Leaf** architecture.

- **Structure:** It consists of higher-tier switches (Spine) and intermediate-tier switches (Leaf) to which end devices connect.
- **Connection Rules:** Every Spine switch is connected to all Leaf switches, and every Leaf switch is connected to all Spine switches. However, Leaf switches never connect directly to each other, nor do Spine switches have direct connections to one another.
- **Top-of-Rack (ToR):** In this configuration, each physical rack in the data center has a Leaf switch positioned at the top to which all devices in that rack connect. This simplifies cabling, ensures redundancy, and increases performance since every device is only one switch "hop" away from any other in the data center.
- **Costs:** Although efficient for small data centers, the cost can increase significantly in facilities with hundreds or thousands of racks, as a dedicated switch is required for each rack.

## Point-to-Point Topology

As the name suggests, this topology involves a single point connected directly to another single point.

- **WANs:** It was a very common design in older WANs that used connections such as **T1 or T3** lines.
- **LANs:** It can also be used in local environments, for example, to connect two different buildings within a university or corporate campus.
