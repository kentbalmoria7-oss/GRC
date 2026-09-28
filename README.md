# 🛡️ Home Network Asset Inventory & Security Risk Matrix

> **Scenario:** Setting up an asset management baseline for a home-based small business network to identify connected devices, assess sensitive data exposure, and apply appropriate security controls.

---

## 📌 Executive Summary

In security operations and IT management, **information is the core asset**, and networks serve as the primary medium to access it. Every connected device—from workstations to IoT hardware—represents a potential entry point for unauthorized access or lateral movement.

This project documents a home network inventory to categorize assets based on ownership, function, and access scope, assigning a clear **Sensitivity Level** to prioritize network defense efforts.

---

## 📊 Asset Inventory & Classification Table

| Asset ID | Device Name & Description | Owner / Role | Location | Connection | Sensitive Data / Access Scope | Sensitivity Level |
| :---: | :--- | :--- | :--- | :--- | :--- | :---: |
| `AST-001` | **Workstation Laptop**<br>*(Primary PC)* | Small Business Owner | Home Office | Ethernet / Wi-Fi | Client records, financial files, admin portal access, SOC lab tools. | `HIGH` |
| `AST-002` | **Personal Smartphone**<br>*(Mobile Device)* | Small Business Owner | Mobile / Housewide | Wi-Fi (5 GHz) | Business email, MFA authenticator app, payment verification tokens. | `MEDIUM` |
| `AST-003` | **Smart TV / Streaming Unit**<br>*(IoT Device)* | Shared / Household | Living Room | Wi-Fi (2.4 GHz) | Entertainment stream accounts. No business or local file storage. | `LOW` |

---

## 🏷️ Sensitivity Classification Guide

* 🔴 **`HIGH`**
  * **Criteria:** Devices storing or directly accessing confidential business data, financial records, or system administrative credentials.
  * **Impact:** High probability of severe operational and financial damage if compromised.
* 🟡 **`MEDIUM`**
  * **Criteria:** Devices handling secondary authentication, communication tools (email/chat), or partial administrative rights.
  * **Impact:** Moderate operational risk; could be leveraged as a stepping stone to reach High-sensitivity assets.
* 🟢 **`LOW`**
  * **Criteria:** Non-essential smart home or consumer IoT devices with no direct access to business files or critical services.
  * **Impact:** Minimal direct risk of data loss, but poses potential lateral movement risk if left unsegmented.

---

## 🔐 Security Control Recommendations

1. **Network Segmentation (VLANs):**
   * Isolate `AST-003` (Smart TV) onto a dedicated IoT/Guest VLAN to prevent traffic sniffing or lateral movement toward `AST-001`.
2. **Access & Endpoint Protection:**
   * Enforce Full Disk Encryption (e.g., BitLocker/FileVault) and strong local authentication on `AST-001`.
   * Enable mandatory Multi-Factor Authentication (MFA) on `AST-002` for all business account access.
3. **Patch & Vulnerability Management:**
   * Enable automated firmware and OS updates across all inventoried devices.

---

## 📁 Repository Structure

```text
.
├── docs/
│   └── network-diagram.png   # Optional topology map
└── README.md                 # Primary documentation
