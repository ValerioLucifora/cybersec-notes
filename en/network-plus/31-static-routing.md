# 31 — Static Routing

> 📚 **Course:** CompTIA Network+ (N10-009)
> 
> 📅 **Last modified:** 2026-08-18

---

## The Role of the Router in Network Traffic

Routers used in homes and offices have the fundamental task of **forwarding traffic between different IP subnets**. Although the process can be technologically complex, it boils down to a few essential steps:

1. **Identification:** The router examines the incoming packet to identify the destination IP address.
2. **Consultation:** The router consults its **routing table** to determine the best path.
3. **Forwarding:** If the destination is part of a directly connected subnet, the packet is sent locally; otherwise, it is sent to the **"next hop"**, which is the IP address of the next router in the chain.

If a router does not find a match for the destination IP in its table, the packet is simply **dropped**.

## The Problem of Non-Directly Connected Networks

In a network with multiple routers, each device initially only knows the networks to which it is physically connected. For example, if Router 1 is connected to three local subnets, it will know how to handle traffic for those specific networks, but it will have no information about the networks located "behind" Router 2 or Router 3.

Without manual intervention or a dynamic protocol, if a user tries to send data to a remote subnet not present in the routing table, the router will not know where to send the traffic and will discard it.

## Definition of Static Routing

**Static routing** consists of the manual creation, by a network administrator, of the entries within the routing table. This method requires the manual configuration of each route on every router in the network. It is a very fast solution for small networks and does not involve the use of CPU cycles or memory to process dynamic protocols.

## Advantages and Disadvantages of Static Routing

The use of static routing has specific characteristics that make it suitable only for certain scenarios:

- **Advantages:**
    - **Low overhead:** Since there are no dynamic routing protocols, there is no bandwidth consumption for updates nor extra load on CPU and RAM.
    - **Security:** Because no automatic updates are exchanged between routers, it is considered a more secure method.
    - **Ideal for Stub Networks:** It is perfect for remote sites with a single connection to the outside.
- **Disadvantages:**
    - **Poor scalability:** Manually managing hundreds or thousands of routers would be extremely time-consuming.
    - **No automatic redundancy:** If a link goes down, the router cannot automatically recalculate the path; the administrator must intervene manually.
    - **Risk of human error:** An incorrect configuration can lead to the creation of **routing loops**.

## Practical Configuration Example

To allow Router 1 to communicate with the remote networks, the administrator must access the router (usually via SSH) and add the static routes.

To reach the 10.10.20.0/24 network (located behind Router 2), Router 1 is configured to send all traffic destined for that range to the address **10.10.40.2** (Router 2's interface). Once the packet is received, Router 2 will consult its own table, see that the network is locally connected, and deliver the packet to the final destination. The same process is applied for networks behind Router 3, specifying the relevant "next hop" address.
