# 18 — Network Architectures

> 📚 **Course:** CompTIA Network+ (N10-009)
> 
> 📅 **Last modified:** 2026-08-02

---

## 1. The Three-Tiered Architecture

The three-tiered architecture is a very common standard design in large enterprise networks. This model divides the network into three hierarchical layers to optimize resource management and connectivity.

- **Core Layer:** This represents the heart of the network and serves as the central point for all critical resources. This is where servers, applications, databases, and the main routers that connect the different parts of the infrastructure reside.
- **Distribution Layer:** This acts as an intermediary between end users and the core's central resources. This layer consists of a set of switches that provide connectivity and redundancy, ensuring that there are multiple paths to reach the core in the event of a failure.
- **Access Layer:** This is the physical connection point for users. Access switches are typically located near workstations, for example on the same floor of a building, and allow user devices to connect to the distribution layer.

To better understand this structure, one can use the **analogy of a city**: the **Core** is the city center with the main resources; the **Distribution** represents the highways connecting the suburbs to the center; the **Access** is the local streets connecting individual homes to the highways.

## 2. Collapsed Core Architecture (Two-Tier)

In smaller organizations, a three-tier architecture might be excessive and costly. In these scenarios, a **collapsed core** architecture is often adopted.

This two-tier model **merges the core and distribution layers** into a single functional layer, keeping only the access layer separate. The main advantages of this approach include a simplified design, easier troubleshooting, and lower costs due to the fewer devices required. However, the main drawback is **reduced redundancy**: the loss of a single component can have a greater impact on the overall network resilience compared to the three-tier model.

## 3. Data Center Traffic Flows

When analyzing data movement within a data center, it is essential to identify the traffic's source and destination using two main definitions:

- **East-West Traffic:** This refers to traffic where both the source and destination reside within the same data center. A typical example is data exchange between a file server and an image server on the same local network. This type of traffic typically benefits from very fast response times.
- **North-South Traffic:** This indicates traffic that enters the data center from an external source or exits it to the outside (for example, to the Internet). This flow requires more stringent security management, as the data interacts with external networks not controlled by the organization.
