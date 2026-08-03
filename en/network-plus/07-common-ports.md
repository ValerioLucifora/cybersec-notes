# 07 — Common Ports

> 📚 **Course:** CompTIA Network+ (N10-009)
> 
> 📅 **Last modified:** 2026-08-02

---

## **File Transfer Protocols**

### **FTP (File Transfer Protocol)**

FTP is a generic file transfer protocol used across various operating systems such as Windows, Linux, and macOS. Unlike other applications, it uses two distinct ports: **TCP port 20** for data transfer and **TCP port 21** for control information. It supports authentication via username and password and allows remote file management, including renaming, deleting, or listing files in directories.

### **SFTP (Secure FTP)**

SFTP is the secure version of FTP and ensures that all communication is encrypted by default. It uses the **SSH (Secure Shell)** protocol to handle encryption, thus operating on **TCP port 22**. It offers the same file management capabilities as FTP, but with a higher level of security.

### **TFTP (Trivial File Transfer Protocol)**

TFTP is used for very simple and fast file transfers, typically for small configuration files, as it does not require authentication. It runs on **UDP port 69** and is extremely efficient due to its low overhead. A common use case is downloading configuration files for VoIP phones.

---

## **Remote Access and Terminal**

### **SSH (Secure Shell) and Telnet**

**SSH** uses **TCP port 22** to provide secure, encrypted command‑line communication with a remote device. In contrast, **Telnet**, which operates on **TCP port 23**, transmits all information in plaintext. Because Telnet lacks encryption, login credentials can be easily intercepted, which is why it has been largely replaced by SSH in modern networks.

### **RDP (Remote Desktop Protocol)**

RDP allows users to view and manage the desktop of a remote device, typically Windows‑based. It uses **TCP port 3389** and, although associated with Windows, RDP clients are available for many other operating systems including macOS, Linux, iOS, and Android.

---

## **Email Management**

### **SMTP (Simple Mail Transfer Protocol)**

SMTP is the fundamental protocol for transferring email between servers and for sending messages from clients. It commonly uses **TCP port 25** for unencrypted (plaintext) transfers between servers. For enhanced security, many SMTP servers prefer **TCP port 587**, which incorporates TLS encryption.

---

## **Network Infrastructure Services**

### **DNS (Domain Name System)**

DNS translates domain names (e.g., www.professormesser.com) into IP addresses. Standard queries use **UDP port 53**, while larger data transfers between DNS servers occur over **TCP port 53**. It is a critical resource; without DNS, communication with web servers would be extremely difficult.

### **DHCP (Dynamic Host Configuration Protocol)**

DHCP automates IP address configuration for devices joining a network. It uses **UDP ports 67 and 68**. DHCP servers assign addresses from an available pool for a limited time (lease time) and can also reserve specific addresses based on a device's MAC address.

### **NTP (Network Time Protocol)**

NTP is used to synchronize the time across all devices on a network, including routers, switches, and servers. It operates on **UDP port 123**. Time synchronization is essential not only for accuracy but also for managing and analyzing log files from disparate devices.

---

## **Management, Monitoring, and Logging**

### **SNMP (Simple Network Management Protocol)**

SNMP enables network professionals to monitor device performance. It uses **UDP port 161** for queries from managers to devices. There are three versions: **v1** and **v2** send data in plaintext, while **v3** provides authentication and encryption. Additionally, devices can send proactive notifications (traps) to the management server via **UDP port 162**.

### **Syslog**

Syslog is the standard protocol for consolidating log files from routers, firewalls, and servers into a single central database, often a SIEM. It uses **UDP port 514** to transfer these data across the network.

---

## **Data Access and Web Services**

### **HTTP and HTTPS**

Web browsers use **HTTP** on **TCP port 80** for unencrypted communications. To protect data, **HTTPS** encrypts the communication via SSL or TLS on **TCP port 443**.

### **LDAP (Lightweight Directory Access Protocol)**

LDAP is used to query and manage hierarchical databases of users and devices on a network. The standard version uses **TCP port 389**, while the secure version (**LDAPS**) uses **TCP port 636**.

### **SMB (Server Message Block)**

SMB is the protocol integrated into Windows for file and printer sharing, as well as network authentication. Modern versions communicate directly over IP using **TCP port 445**.

### **SQL and SIP**

- **MS SQL Server:** Microsoft SQL databases typically use **TCP port 1433** for query management.
- **SIP (Session Initiation Protocol):** Used for controlling VoIP calls and video conferencing, it operates on **TCP ports 5060 and 5061** to start, manage, and terminate sessions.
---
