# 32 — Dynamic Routing

> 📚 **Course:** CompTIA Network+ (N10-009)
> 
> 📅 **Last modified:** 2026-08-18

---

## Introduction to Dynamic Routing

Dynamic routing is an automated process that allows routers to discover routes and update each other based on the best available path. Unlike **static routing**, which requires the network administrator to manually configure each route on every device, dynamic routing eliminates the need for constant manual interventions or SSH changes every time the infrastructure changes. When a new router is added or removed, all other devices on the network are automatically notified.

## Operation and System Requirements

The update process takes place behind the scenes in real time. Routers monitor traffic on their local subnet to detect other routers sending routing updates, often using **multicast** messages. Once a router has built its own routing table, it informs its neighbors of the routes it knows.

However, this automation comes at a cost:

- **System resources:** The process requires a certain overhead in terms of **CPU and memory** within the router to handle computations and updates.
- **Initial configuration:** Although it reduces the long-term workload, it requires initial planning and configuration of the chosen protocol, which can vary in complexity.

---

## Selection Criteria and Protocol Types

### Decision-Making Criteria

Each routing protocol uses different criteria to determine the best path to a remote destination. Some of the factors taken into account include:

- **Link status** (whether the link is up or down).
- The **hop count** required to reach the destination.
- **Speed** and throughput of the connection.
- **Convergence time**, i.e., how quickly the network updates itself after a change.

## Main Routing Protocols

### 1. EIGRP (Enhanced Interior Gateway Routing Protocol)

This protocol is historically linked to **Cisco** environments, although it is also available on other devices.

- **Advantages:** It is relatively easy to configure and converges very quickly in the event of network changes.
- **Efficiency:** It can identify and avoid routing loops and uses minimal network traffic for updates, preserving bandwidth for other applications.

### 2. OSPF (Open Shortest Path First)

OSPF is an open standard link-state protocol used by many different vendors, making it ideal for multi-vendor networks.

- **Autonomous Systems (AS):** It is often implemented in networks under a single administrative control, such as a WAN with many routers.
- **Link Cost:** It uses a "cost" value assigned to each link, usually based on speed and availability; the path with the lowest cost is considered the best. It also supports **load balancing** across links with identical costs.

### 3. BGP (Border Gateway Protocol)

BGP is classified as an external gateway protocol and is the protocol that "makes **the Internet** work".

- **Usage:** It is designed to connect different Autonomous Systems or different organizations together.
- **Fun fact:** It is sometimes referred to as the "three-napkin protocol" because its core concepts were initially sketched out on napkins to solve the problem of dynamic routing on a global scale.
