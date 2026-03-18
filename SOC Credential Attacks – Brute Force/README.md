# 🛡 SOC-Credential-Attacks – Brute Force Home Lab

## 📌 Project Overview

This project demonstrates a **brute-force credential attack simulation** in a controlled home lab environment.
It focuses on how a SOC analyst detects and analyzes multiple failed login attempts followed by a successful compromise using **Windows Event Logs, Sysmon, and Splunk SIEM**.

### 🔎 Lab Summary

| Component   | Description                        |
| ----------- | ---------------------------------- |
| Attack Type | Brute Force (Credential Attack)    |
| Attacker    | Kali Linux                         |
| Target      | Windows 11                         |
| SIEM        | Splunk Enterprise                  |
| Logs        | Windows Security + Sysmon          |
| Objective   | Detect and analyze login anomalies |

---

# SOC Credential Brute-Force Lab – Workflow Overview

| Step | Description |
|------|-------------|
| 1 | **Attack Simulation:** Attacker performs brute-force attempts against target (RDP/SMB) to gain credentials. |
| 2 | **Log Generation:** Target system generates Windows Security (4625/4624) and Sysmon logs. |
| 3 | **Detection:** SIEM platform monitors logs and triggers alerts on abnormal login patterns. |
| 4 | **Investigation:** Analyst validates alerts, checks source IP, target accounts, and logon events. |
| 5 | **Threat Classification:** Attack identified as Credential Access (MITRE ATT&CK T1110). |
| 6 | **Response:** Block attacker, secure accounts, enforce password policies, and reset passwords. |
| 7 | **Lessons Learned:** Improve detection rules, strengthen authentication, and review weak passwords. |

**Summary:**  
This lab simulates a full SOC workflow for credential brute-force attacks—from attack simulation, log collection, detection, and investigation to response and hardening. It provides hands-on experience in monitoring, analyzing, and responding to credential-based attacks.
