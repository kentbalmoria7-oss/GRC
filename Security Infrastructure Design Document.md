# 🛡️ Security Infrastructure Design Document

## 📋 Scenario & Assignment Overview

**Role:** Security Consultant  
**Client Organization:** Artisanal Widget Co. (Online Retailer)  
**Company Size:** 50 employees in a single office location  
**Business Profile:** E-commerce business selling hand-crafted widgets to external customers  
**Primary Risk Focus:** Handling customer payment and personal data, protecting against malware infections, preventing data loss from stolen devices, and securing internal engineering workflows.

---

## 🎯 Assignment Requirements

As the Security Consultant hired by Artisanal Widget Co., you are tasked with designing a complete security infrastructure design document that addresses the following core technical and policy requirements:

1. **Authentication System:** Centralized authentication and identity management.
2. **External Web Infrastructure:** Secure customer-facing e-commerce platform.
3. **Internal Web Infrastructure:** Secure intranet access for employees.
4. **Remote Access:** Command-line and network access for engineering staff.
5. **Firewall Architecture:** Basic rules and network protection mechanisms.
6. **Wireless Coverage:** Secure office Wi-Fi implementation.
7. **Network Segmentation:** VLAN recommendations for departmental isolation.
8. **Endpoint Security:** Laptop hardening against theft and malware.
9. **Application & Patch Policies:** Restrictions on unapproved software and patch timelines.
10. **Data Privacy & Security Policies:** Controls for accessing, storing, and handling customer payment data.
11. **Intrusion Detection/Prevention (IDS/IPS):** Monitoring and prevention solutions for critical database systems.

---

## 📝 Submitted Deliverable

### 1. Authentication System
Authentication will be handled centrally by an LDAP server and will incorporate One-Time Password generators as a 2nd factor for authentication.

### 2. External System Security
The customer-facing application will be served via HTTPS, since it will be serving an e-commerce platform permitting visitors to browse and purchase products, as well as create and log into accounts. This application will be publicly accessible.

### 3. Internal System Security
The internal employee resources will also be served over HTTPS, as it will require authentication for employees to access. It will only be accessible from the internal company network and only with an authenticated account.

### 4. Remote Access Solution
Since engineers require remote access to internal resources, as well as remote command line access to workstations, a network-level VPN solution will be needed, like OpenVPN. To make internal resource access easier, a reverse proxy is recommended in addition to the VPN. Both of these rely on the LDAP server for authentication and authorization.

### 5. Firewall Configuration & Basic Rules
A network-based firewall appliance will be required. It will include rules to permit traffic for various services, starting with an **implicit deny** rule, then selectively opening ports. Rules will be needed to allow public access to the external application, and to permit traffic to the reverse proxy server and the VPN server.

### 6. Wireless Security
For wireless security, 802.1X with EAP-TLS should be used. This requires the use of client certificates, which can also be used to authenticate other services like VPN, reverse proxy, and internal authentication. 802.1X is more secure and more easily managed as the company grows, making it a better choice than standard WPA2.

### 7. Network Segmentation (VLAN Configuration)
Incorporating VLANs into the network structure is recommended as a form of network segmentation to make controlling access easier to manage:
* **Engineering VLAN:** Place all engineering workstations and engineering services on this segment.
* **Infrastructure VLAN:** Reserved for all infrastructure devices, including wireless APs, network hardware, and critical servers like authentication.
* **Sales VLAN:** Assigned for non-engineering corporate machines.
* **Guest VLAN:** Strictly isolated for third-party devices and visitors that do not fit standard assignments.

### 8. Endpoint & Laptop Security Configuration
As the company handles payment information and user data, privacy is a primary requirement. Laptops must have Full Disk Encryption (FDE) to protect against unauthorized data access if a device is lost or stolen. Antivirus software is required to avoid infections from common malware. To protect against uncommon attacks and unknown threats, binary whitelisting software is recommended in addition to antivirus software.

### 9. Application & Patch Management Policy
To enhance client security, an application policy will restrict the installation of third-party software to only applications directly related to work functions. Risky and legally questionable application categories—such as pirated software, license key generators, and cracked software—are explicitly banned.

Additionally, a policy mandates the timely installation of software patches, defined as within **30 days** from the wide availability of the patch.

### 10. User Data Privacy & Handling Policy
User data must only be accessed for specific work purposes related to a particular task or project. Requests must be made for specific pieces of data rather than overly broad, exploratory requests. Access requests must be reviewed and approved with a defined expiration date before access is granted.

User data is prohibited on portable storage devices such as USB keys or external hard drives. If an exception is necessary, an encrypted portable drive must be used. All user data at rest must be contained on encrypted media to prevent unauthorized access.

### 11. Corporate Password & Security Policy
The following password policy will be enforced:
* Minimum length of **8 characters**
* Minimum of **one special character or punctuation mark**
* Mandatory password change every **12 months**

Mandatory security training must be completed by every employee once per year, covering phishing detection, physical device security, and emerging security threats.

### 12. Intrusion Detection & Prevention Systems (IDS/IPS)
A Network Intrusion Detection System (NIDS) will monitor network activity for signs of attack or malware infection without interrupting network users. 

A Network Intrusion Prevention System (NIPS) is recommended for the server segment containing customer data, as this high-value data is a primary target. Host-based Intrusion Detection Systems (HIDS) will also be installed on these servers to enhance file integrity and access monitoring.
