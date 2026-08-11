# 28 — Zero Trust

> 📚 **Course:** CompTIA Network+ (N10-009)
> 
> 📅 **Last modified:** 2026-08-11

---

## **1. Introduction to Zero Trust**

Traditionally, cybersecurity has focused on protecting the **network perimeter**, controlling who enters and who exits. However, once the perimeter was breached, networks tended to be fully accessible, creating serious security risks.

**Zero Trust** is a holistic security approach that radically changes this paradigm:

- **No default trust:** Every user, device, and application is considered inherently untrusted.
- **Constant verification:** Every type of traffic must be inspected and verified to ensure that only the correct users access the appropriate data.
- **Technologies involved:** Implementation includes authentication, encryption, additional firewalls, and continuous network monitoring.

## **2. Authentication and Adaptive Identity**

The access process begins with authentication (username, password, and other factors), but Zero Trust introduces the concept of **Adaptive Identity** within a context‑based policy.

To determine the risk level of an access attempt, the system evaluates several factors:

- **Who the user is:** For example, whether they are a long‑standing employee or a newly hired external vendor.
- **Geographic location:** Whether the user is connecting from the local area or from a foreign country.
- **Technical details:** The IP address and connection type (e.g., VPN) are analyzed.
- **Behavior:** If a user enters correct credentials but at an **unusual time** or from a **suspicious location**, authentication may be denied or an additional verification factor may be required.

## **3. Authorization and Access Control**

Once the identity has been successfully verified, Zero Trust defines what specific permissions the user should have.

- **Role‑based access:** For example, a helpdesk technician may only be able to view a database, while their manager may have permissions to modify it.
- **Device context:** If a user is using a **verified corporate laptop** via certificate, they may receive greater permissions than someone using an unrecognized device.
- **Principle of Least Privilege:** This is a fundamental practice that consists of providing only the rights necessary to perform one's job. Arbitrary administrative rights must not be assigned, because if a device becomes infected with **malware**, that malware would obtain the same administrative privileges as the user, putting the entire system at risk.

## **4. SASE (Secure Access Service Edge)**

With users and applications distributed everywhere (office, home, public cloud, or private data centers), a secure communication mechanism that is independent of physical location is required.

**SASE** represents the evolution of VPN and moves security technologies directly into the **cloud**, close to where the data resides.

- **SASE client:** Installed on every user device to ensure protection wherever the user is located.
- **Services offered:** SASE combines networking capabilities (Network as a Service, such as routing and QoS) with security capabilities (Security as a Service).
- **Security components:** Includes Firewall as a Service, DNS security, and Zero Trust Network Access (ZTNA).
- **User experience:** The connection occurs automatically and transparently; the user does not have to manually enable or disable functions, because security is built into the entire process.
