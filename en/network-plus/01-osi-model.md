# 01 — OSI Model

> 📚 **Course:** CompTIA Network+ (N10-009)
> 
> 📅 **Last modified:** 2026-08-02

---

## The OSI (Open Systems Interconnection) Model

The **Open Systems Interconnection (OSI)** reference model is a framework used in the IT field to describe the process that data follows as it travels across networks. It is not a detailed description of the data itself, but rather a high‑level overview of its path through systems. Although most modern protocols are based on the TCP/IP stack, the OSI model is applicable to many different protocols and allows IT professionals to communicate using a common language.

## Structure and Memorizing the Layers

The OSI model consists of **seven distinct layers**. Starting from the top down, the layers are:

- **Layer 7:** Application
- **Layer 6:** Presentation
- **Layer 5:** Session
- **Layer 4:** Transport
- **Layer 3:** Network
- **Layer 2:** Data Link
- **Layer 1:** Physical

To help remember this sequence (from top to bottom), the English **mnemonic** often used is: _"All People Seem To Need Data Processing"_.

---

## Detailed Breakdown of the Seven Layers

### Layer 1: Physical Layer

The Physical layer describes the **physical signals** sent over cables, fiber optics, or wireless networks. At this layer, we do not discuss complex protocols but rather the pure transmission of signals from one point to another on the network. Layer 1 issues usually involve damaged cables, wireless interference, or faulty network interface cards.

### Layer 2: Data Link Layer

This is the fundamental layer for communication between two devices and is often associated with **MAC addresses** (Media Access Control), which are the hardware addresses of network interfaces. Since network switches decide how to forward traffic based on the destination MAC address, this layer is commonly referred to as the **"switching layer"**.

### Layer 3: Network Layer

Also known as the **"routing layer"**, this is the layer where routers operate to determine the best path for data based on the destination **IP address**. Packet fragmentation into smaller pieces also occurs at this layer, if necessary, to allow transit across different networks. Any issue related to IP addresses, subnet masks, or routing belongs to Layer 3.

### Layer 4: Transport Layer

This layer is responsible for transporting information between devices and is comparable to a **"post office"**. The main protocols operating here are **TCP** (Transmission Control Protocol) and **UDP** (User Datagram Protocol). Layer 4 handles the encapsulation of data into manageable pieces and uses **port numbers** (such as port 80 or 443) to direct traffic.

### Layer 5: Session Layer

The Session layer manages communication between point A and point B, handling **starting, stopping, or restarting sessions**. It is used for controlling communication protocols and for tunneling information within existing data streams.

### Layer 6: Presentation Layer

This layer formats data into a form that is understandable to the user, handling character encoding and **encryption/decryption** (such as SSL or TLS). Layer 6 often works closely with the upper Application layer.

### Layer 7: Application Layer

This is the layer that the user interacts with directly through the screen. Any visible message or interface belongs to this layer. Common Layer 7 protocols include **HTTP/HTTPS, FTP, DNS, and POP3**.

---

## Practical Example: Analysis with Wireshark

Using tools like **Wireshark** allows you to see how these layers actually operate within a single network frame. When analyzing a packet of traffic to Google Mail, you can observe the breakdown:

- **Electrical signals:** Associated with Layer 1 (Physical).
- **Ethernet frames:** Containing MAC addresses, associated with Layer 2 (Data Link).
- **IP protocol:** With source and destination IP addresses, associated with Layer 3 (Network).
- **TCP segment:** With associated port numbers, associated with Layer 4 (Transport).
- **SSL/TLS:** Handling encryption and sessions, covering the functions of Layers 5, 6, and 7.
---
