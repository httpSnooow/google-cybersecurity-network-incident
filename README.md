# 🛡️ Network Security & Incident Management

> **Project Context:** Google Cybersecurity Professional Certificate

<div align="center">

  ![Google](https://img.shields.io/badge/Google-Cybersecurity-4285F4?style=for-the-badge&logo=google&logoColor=white)
  ![Wireshark](https://img.shields.io/badge/Wireshark-Analysis-1679A7?style=for-the-badge&logo=wireshark&logoColor=white)
  ![NIST](https://img.shields.io/badge/NIST-CSF-003366?style=for-the-badge&logo=nist&logoColor=white)
  ![Linux](https://img.shields.io/badge/Linux-Tcpdump-FCC624?style=for-the-badge&logo=linux&logoColor=black)

</div>

---

## 📄 Project Overview

**Scenario:** As a Cybersecurity Analyst, I investigated multiple security incidents affecting organizational infrastructure, ranging from service interruptions to active malicious breaches.

This repository documents the **technical analysis** of network traffic (using `tcpdump` and `Wireshark`) and the **strategic application** of the NIST Cybersecurity Framework (CSF) to harden the security posture.

---

## 🔍 Incident Case Studies

Detailed analysis of the three major security events handled during this simulation.

### 1. 🌐 DNS & Connectivity Analysis
**Issue:** Users reported a "destination port unreachable" error when accessing the company website.

* **🛠️ Analysis:** Used `tcpdump` to capture traffic, identifying failed UDP queries.
* **🔑 Key Finding:** The logs showed `udp port 53 unreachable` messages.
* **⚠️ Root Cause:** The DNS service was down, or a firewall was improperly blocking **Port 53**.
* **✅ Resolution:** Restored DNS listener services and verified firewall configurations for Port 53.

### 2. 🚦 TCP SYN Flood Attack (DoS)
**Issue:** The web server became unresponsive due to a sudden flood of connection requests.

* **🛠️ Analysis:** Wireshark logs revealed a massive volume of TCP `[SYN]` packets from an unfamiliar IP (`203.0.113.0`) without completing the three-way handshake.
* **💥 Impact:** Legitimate users faced `504 Gateway Time-out` and `[RST, ACK]` errors as server resources were exhausted.
* **✅ Mitigation:** Blocked the malicious IP via firewall and established an **ICMP rate-limiting policy**.

### 3. 🔓 Brute Force & Malware Redirection
**Issue:** A malicious actor gained admin access and injected code to redirect users to a malware-hosting site.

* **🛠️ Analysis:** Network logs showed traffic being rerouted from the legitimate domain to a spoofed IP address (`192.0.2.17`).
* **⚠️ Root Cause:** The attacker exploited default administrative passwords through a **brute-force attack**.
* **✅ Resolution:** Implemented **MFA**, enforced strong password policies (salting/hashing), and cleaned the website source code.

---

## 🛠️ NIST CSF Strategic Implementation

I applied the five core functions of the **NIST Cybersecurity Framework** to remediate current issues and prevent future occurrences.

| Function | Action Taken |
| :--- | :--- |
| 🔎 **Identify** | Audited internal networks to find gaps like unconfigured firewalls and default credentials. |
| 🛡️ **Protect** | Implemented **Multi-Factor Authentication (MFA)** and new firewall rules to limit ICMP packet rates. |
| 📡 **Detect** | Deployed **IDS/IPS systems** and network monitoring software to catch abnormal traffic patterns. |
| 🚨 **Respond** | Established procedures to isolate affected resources and verify source IPs to block spoofing. |
| ♻️ **Recover** | Developed a plan to restore critical services from clean backups and inform stakeholders of breaches. |

---

## 🚀 Security Hardening Recommendations

To improve overall network resilience, the following hardening tasks were prioritized:

* 🛡️ **Network Segmentation:** Divide the network to contain attacks and limit lateral movement.
* 🔑 **Principle of Least Privilege:** Restrict user permissions to minimize the impact of compromised accounts.
* 📏 **Baseline Configurations:** Maintain a "known good" state to easily detect and revert unauthorized changes.
* 🔄 **Regular Patching:** Keep all OS and software updated to close known vulnerabilities.

---

<div align="center">
  <sub><i>Disclaimer: This is a fictional case study completed for educational purposes as part of the Google Cybersecurity Certificate.</i></sub>
</div>
