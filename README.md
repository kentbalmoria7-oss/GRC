# 🛡️ Cybersecurity & IT Infrastructure Portfolio

Welcome to my cybersecurity portfolio. This repository serves as a centralized showcase of my technical projects, incident response investigations, risk assessments, and security architecture documentation. 

My work bridges **hands-on technical analysis** (packet analysis, access control investigation, network scripts) with **governance and analytical frameworks** (NIST CSF, Least Privilege audits, Risk Registers) to protect organization assets and maintain operational resilience.

---

## 📂 Portfolio Directory & Project Index

| Project File | Category / Domain | Core Focus & Skills Demonstrated |
| :--- | :--- | :--- |
| **`Access Controls Investigation & Incident Analysis.md`** | Identity & Access Management (IAM) | Investigating privilege escalation, broken access controls, and unauthorized resource access events. |
| **`Home Network Asset Inventory.md`** | Asset Management | Mapping, classifying, and securing personal/lab network endpoints to minimize attack surface area. |
| **`Information Privacy Audit & Least Privilege Analysis.md`** | GRC & Data Privacy | Auditing system permissions, evaluating compliance with data privacy standards, and enforcing Least Privilege. |
| **`NIST CSF Incident Response & ICMP Flood Mitigation Plan.md`** | Incident Response / Network Defense | Mapping a DoS/DDoS event across the 5 NIST CSF pillars with defensive Python/Scapy automation. |
| **`Risk Assessment & Risk Register.md`** | Governance, Risk & Compliance (GRC) | Identifying vulnerabilities, scoring likelihood and impact, and establishing risk mitigation strategies. |
| **`SOC Level 1 Incident Report — Phishing & Malware Escalation.md`** | SOC Operations & Triage | Analyzing suspicious emails, payload delivery mechanisms, indicators of compromise (IOCs), and escalation workflows. |
| **`Security Infrastructure Design Document.md`** | Security Architecture | Designing secure network topologies, firewall placements, segmentation rules, and defensive architecture. |

---

## 🎯 Core Competencies & Key Technical Domains

### 1. 🚨 SOC Operations & Incident Response
* **Triage & Threat Analysis:** Analyzing phishing vectors, malicious attachments, and indicators of compromise (IOCs) as documented in `SOC Level 1 Incident Report — Phishing & Malware Escalation.md`.
* **Framework Alignment:** Applying the **NIST Cybersecurity Framework (Identify, Protect, Detect, Respond, Recover)** to structure response workflows during network degradation and flood events.

### 2. 🛡️ Identity, Access Management & Privacy
* **Access Control Audits:** Evaluating authentication logs, permission structures, and broken access controls to remediate identity vulnerabilities.
* **Least Privilege Enforcement:** Conducting data privacy and privilege audits to ensure users and applications operate strictly within authorized operational scopes.

### 3. 📊 Governance, Risk & Compliance (GRC)
* **Risk Register Development:** Quantifying organizational risk using structured likelihood and impact metrics, developing clear remediation roadmaps.
* **Asset Discovery & Inventory:** Maintaining accurate hardware/software inventories to ensure complete security monitoring coverage across network environments.

### 4. 🌐 Security Infrastructure & Network Defense
* **Defensive Architecture:** Designing resilient network topologies featuring proper micro-segmentation, perimeter firewalls, and IDS/IPS positioning.
* **Packet & Traffic Analysis:** Inspecting network traffic for volumetric anomalies, spoofed source IP headers, and unauthorized connections.

---
        print("\n[*] Monitoring terminated by operator.")
        sys.exit(0)


if __name__ == "__main__":
    main()
