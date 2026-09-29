# NIST CSF Incident Response & ICMP Flood Mitigation Plan

## Executive Summary
This repository documents an incident response and network security improvement plan following a Denial of Service (DoS) attack against a multimedia company specializing in web design, graphic design, and social media marketing. The incident involved an incoming ICMP ping flood that rendered internal network resources unavailable for two hours.

The analysis and security strategy are structured according to the **National Institute of Standards and Technology (NIST) Cybersecurity Framework (CSF)**.

---

## Incident Overview & Summary
* **Target:** Multimedia Company Internal Network
* **Attack Type:** ICMP Flood (Denial of Service)
* **Root Cause:** Unconfigured perimeter firewall permitting unfiltered ICMP traffic
* **Impact:** 2-hour total outage of internal network resources and client service platforms
* **Initial Response:** Blocked inbound ICMP traffic, isolated non-critical services, and prioritized critical service recovery.

---

## NIST Cybersecurity Framework Alignment

### 1. Identify
* **Targeted Assets:** Internal network, core servers, and employee access nodes.
* **Threat Actor:** External malicious actor exploiting perimeter firewall misconfigurations.
* **Vulnerability:** Unfiltered ICMP packet handling allowing network bandwidth and resource exhaustion.

### 2. Protect
* **Firewall Rate Limiting:** Applied rules to cap incoming ICMP packet rates.
* **IDS/IPS Deployment:** Configured Intrusion Detection/Prevention rules to filter suspicious ICMP signatures.
* **Hardening:** Closed unneeded ports and hardened default firewall policies.

### 3. Detect
* **Anti-Spoofing Verification:** Enabled Source IP address validation at the firewall edge to detect forged packet origins.
* **Network Monitoring:** Integrated traffic monitoring tools to establish baseline behavior and flag anomalous spikes.

### 4. Respond
* **Containment:** Isolate affected segments immediately upon detection.
* **Triage & Analysis:** Review firewall and IDS/IPS logs to trace attack vectors and impact scope.
* **Reporting:** Escalate incidents to executive leadership and relevant legal authorities as required.

### 5. Recover
* **Restoration Sequence:** 
  1. Filter/block malicious flood traffic at the edge.
  2. Suspend non-critical services to preserve bandwidth.
  3. Bring core critical services back online first.
  4. Restore remaining systems once ICMP traffic levels normalize.
