# 13 — Copper Cabling

> 📚 **Course:** CompTIA Network+ (N10-009)
> 
> 📅 **Last modified:** 2026-08-02

---

## **The Importance of Cabling in Networks**

Cabling represents the **foundation of every network infrastructure**, whether it involves routers, switches, or wireless access points. It is essential to choose the correct cable from the start, because once installed, it is extremely difficult and expensive to remove or replace. Even predominantly wireless networks ultimately depend on a wired connection to ensure the best possible throughput.

## **Twisted Pair Copper Cables**

Twisted pair cable is the most widespread type for wired Ethernet connections and consists of multiple copper wires twisted together within a single sheath.

- **Signal management:** The wires are paired to send the same signal in different forms (e.g., "transmit plus" and "transmit minus"), allowing the receiver to **recognize and correct any interference**.
- **Physical structure:** The twisting ensures that at least one of the wires is constantly moving away from the interference source. Additionally, different pairs within the same cable have **different twist rates** (some are tighter than others) to improve performance.

## **Network Standards and Cable Categories**

It is important to understand that the cable itself does not possess an intrinsic "speed," but rather supports a signal that enables data transmission.

- **IEEE 802.3 Standards:** These standards determine the amount of data that can traverse the link and specify the minimum type of cable required for each technology (e.g., 1000Base‑T requires at least a Category 5 cable).
- **Cable categories:** To simplify selection, cables are classified into categories (such as **Cat 5, Cat 6, or Cat 7**). Using a cable of a higher category than the minimum required will work correctly.

## **Coaxial and Twinax Cables**

In addition to twisted pair, other types of copper cables are used in specific contexts:

- **Coaxial Cable:** In this cable, the center conductor, insulator, shielding, and outer jacket all share the same axis. The **RG6** type is common for cable modem Internet connections.
- **Twinax (Twinaxial) Cable:** It features two inner conductors and is often associated with **10 Gigabit Ethernet** via SFP+ interfaces. It offers full‑duplex communication, low cost, and lower latency compared to twisted pair, but is limited to short distances, approximately **5 meters**.

## **Fire Safety: The Plenum**

The "plenum" is the space between the drop ceiling and the actual ceiling, often used for running cables and infrastructure.

- **Fire hazards:** If this space is used for air circulation (without closed ducts), it becomes a shared area where a fire could spread toxic fumes throughout the building via the ventilation system.
- **Cable materials:** Standard cables often have a **PVC** (polyvinyl chloride) jacket, which produces a lot of smoke and toxic gases when burned.
- **Plenum‑rated cables:** In these areas, it is mandatory to use "plenum"‑rated cables, made from **FEP** (fluorinated ethylene propylene) or low‑smoke PVC. These cables are safer in the event of a fire, although they may be less flexible and therefore more difficult to install in tight corners.

In summary, it is essential to always verify where the cable will be installed in order to select the correct type and ensure both performance and building safety.
---
