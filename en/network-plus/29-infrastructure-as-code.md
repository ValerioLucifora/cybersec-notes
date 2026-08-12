# 29 — Infrastructure as Code (IaC)

> 📚 **Course:** CompTIA Network+ (N10-009)
> 
> 📅 **Last modified:** 2026-08-13

---

## **1. What is Infrastructure as Code (IaC)**

**Infrastructure as Code (IaC)** is a concept that allows you to describe networking technologies and the entire IT infrastructure using configuration files, i.e., in the form of **code**. Instead of manually installing and configuring each individual device, you create a file that defines every component: servers, firewalls, switches, routers, and applications.

### **Key Benefits:**

- **Automation:** You can instruct the cloud to build the entire system based on the code specifications.
- **Duplication:** It is extremely simple to create an exact duplicate of an entire infrastructure in another data center simply by moving and applying the code.
- **Versioning:** You can create different versions of the infrastructure, make minor changes, and redeploy the updated configuration.

**Example**:

```
all:
	hosts:
		mail.example.com:
	children:
		webservers:
			hosts:
				foo.example.com:
				bar.example.com:
		dbservers:
			hosts:
				one.example.com:
				two.example.com:
				three.example.com:
```

## **2. Response Automation: Playbooks**

Beyond building infrastructure, you can automate **incident response** through **Playbooks**. A Playbook is a defined sequence of steps to follow to resolve or address a specific issue.

- **Use cases:** Investigating a data breach or recovering systems after a ransomware attack.
- **Automated process:** A system can identify malware, consult the Playbook, and autonomously proceed to isolate the device, wipe the data, reinstall the operating system, and reintegrate the device into the infrastructure.
- **SOAR (Security Orchestration, Automation, and Response):** Playbooks are commonly implemented within SOAR platforms, centralized consoles that allow you to manage, monitor, and automate all security operations in a single environment.

## **3. Infrastructure Management and Standardization**

IaC addresses several issues related to managing large machine fleets:

- **Configuration Drift:** Prevents small configuration differences from arising between different instances of an application.
- **Compliance:** Ensures that all systems adhere to the same standards, since they are created from the same code definitions.
- **Test and Production Environments:** Ensures that the test environment is identical to production, facilitating transitions between the two stages.
- **Simplified Updates:** To update software or modify a configuration, simply change the definition in the IaC file and redeploy it; the system will detect the differences and apply only the necessary changes.
- **Documentation:** IaC can be used to scan an existing system and translate its configuration into a file, providing accurate and reproducible documentation.

## **4. Source Code Control (Source/Version Control)**

In complex environments where many people work on the same configuration files, it is essential to use **Source Control** (or Version Control) systems.

- **Centralized Repository:** All changes are stored in a single location, preventing individual administrators from making isolated modifications.
- **Git:** It is one of the most popular version control systems for managing source code among multiple users.
- **Conflict Management:** If two people modify the same line of code, the version control software detects the conflict and allows an administrator to decide which change to keep.
- **Branching:** This feature allows you to create a "branch" of the production code to perform tests or optimizations in a separate environment. Once the validity of the changes is verified, they can be **merged** back into the main code to update the production environment.
