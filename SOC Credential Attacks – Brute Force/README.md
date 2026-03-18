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

## 📚 SOC Incident Workflow Overview

| Step | Description |
|------|-------------|
| 1 | **Attack Simulation:** Attacker performs brute-force attempts against target (RDP/SMB) to gain credentials. |
| 2 | **Log Generation:** Target system generates Windows Security (4625/4624) and Sysmon logs. |
| 3 | **Detection:** SIEM platform monitors logs and triggers alerts on abnormal login patterns. |
| 4 | **Investigation:** Analyst validates alerts, checks source IP, target accounts, and logon events. |
| 5 | **Threat Classification:** Attack identified as Credential Access (MITRE ATT&CK T1110). |
| 6 | **Response:** Block attacker, secure accounts, enforce password policies, and reset passwords. |
| 7 | **Lessons Learned:** Improve detection rules, strengthen authentication, and review weak passwords. |

---

## Project Structure

- [1-Architecture & Lab Setup](1-Architecture%20&%20Lab%20Setup)
  - [1.1 Lab Overview.md](1-Architecture%20&%20Lab%20Setup/1.1%20Lab%20Overview.md)
  - [1.2 Network Diagram.png](1-Architecture%20&%20Lab%20Setup/1.2%20Network%20Diagram.png)
  - [1.3 VM Roles.md](1-Architecture%20&%20Lab%20Setup/1.3%20VM%20Roles.md)
  - [1.4 Lab Setup Details.md](1-Architecture%20&%20Lab%20Setup/1.4%20Lab%20Setup%20Details.md)
- [2-Attack Simulation](2-Attack%20Simulation)
  - [2.1 Scenario Description.md](2-Attack%20Simulation/2.1%20Scenario%20Description.md)
  - [2.2 Attack Execution.md](2-Attack%20Simulation/2.2%20Attack%20Execution.md)
  - [2.3 Tools & Commands.md](2-Attack%20Simulation/2.3%20Tools%20&%20Commands.md)
- [3-Log Collection & Validation](3-Log%20Collection%20&%20Validation)
  - [3.1 Sysmon Configuration.md](3-Log%20Collection%20&%20Validation/3.1%20Sysmon%20Configuration.md)
  - [3.2 Windows Event Analysis.md](3-Log%20Collection%20&%20Validation/3.2%20Windows%20Event%20Analysis.md)
  - [3.3 Log Forwarding to Splunk.md](3-Log%20Collection%20&%20Validation/3.3%20Log%20Forwarding%20to%20Splunk.md)
  - [3.4 Log Validation.md](3-Log%20Collection%20&%20Validation/3.4%20Log%20Validation.md)
- [4-Detection & Analysis](4-Detection%20&%20Analysis)
  - [4.1 Splunk Search Queries.md](4-Detection%20&%20Analysis/4.1%20Splunk%20Search%20Queries.md)
  - [4.2 Detection Logic.md](4-Detection%20&%20Analysis/4.2%20Detection%20Logic.md)
  - [4.3 IOC Extraction.md](4-Detection%20&%20Analysis/4.3%20IOC%20Extraction.md)
  - [4.4 MITRE Mapping.md](4-Detection%20&%20Analysis/4.4%20MITRE%20Mapping.md)
- [5-Incident Case Studies](5-Incident%20Case%20Studies)
  - [5.1 Case 1 – RDP Brute Force](5-Incident%20Case%20Studies/5.1%20Case%201%20–%20RDP%20Brute%20Force)
    - [5.1.1 Scenario Description.md](5-Incident%20Case%20Studies/5.1%20Case%201%20–%20RDP%20Brute%20Force/5.1.1%20Scenario%20Description.md)
    - [5.1.2 Attack Execution.md](5-Incident%20Case%20Studies/5.1%20Case%201%20–%20RDP%20Brute%20Force/5.1.2%20Attack%20Execution.md)
    - [5.1.3 Alert Triage.md](5-Incident%20Case%20Studies/5.1%20Case%201%20–%20RDP%20Brute%20Force/5.1.3%20Alert%20Triage.md)
    - [5.1.4 Deep Investigation.md](5-Incident%20Case%20Studies/5.1%20Case%201%20–%20RDP%20Brute%20Force/5.1.4%20Deep%20Investigation.md)
    - [5.1.5 Timeline Analysis.md](5-Incident%20Case%20Studies/5.1%20Case%201%20–%20RDP%20Brute%20Force/5.1.5%20Timeline%20Analysis.md)
    - [5.1.6 IOC Extraction.md](5-Incident%20Case%20Studies/5.1%20Case%201%20–%20RDP%20Brute%20Force/5.1.6%20IOC%20Extraction.md)
    - [5.1.7 Threat Level.md](5-Incident%20Case%20Studies/5.1%20Case%201%20–%20RDP%20Brute%20Force/5.1.7%20Threat%20Level.md)
    - [5.1.8 Impact Assessment.md](5-Incident%20Case%20Studies/5.1%20Case%201%20–%20RDP%20Brute%20Force/5.1.8%20Impact%20Assessment.md)
    - [5.1.9 Response Playbook.md](5-Incident%20Case%20Studies/5.1%20Case%201%20–%20RDP%20Brute%20Force/5.1.9%20Response%20Playbook.md)
  - [5.2 Case 2 – SMB Brute Force](5-Incident%20Case%20Studies/5.2%20Case%202%20–%20SMB%20Brute%20Force)
    - [5.2.1 Scenario Description.md](5-Incident%20Case%20Studies/5.2%20Case%202%20–%20SMB%20Brute%20Force/5.2.1%20Scenario%20Description.md)
    - [5.2.2 Attack Execution.md](5-Incident%20Case%20Studies/5.2%20Case%202%20–%20SMB%20Brute%20Force/5.2.2%20Attack%20Execution.md)
    - [5.2.3 Alert Triage.md](5-Incident%20Case%20Studies/5.2%20Case%202%20–%20SMB%20Brute%20Force/5.2.3%20Alert%20Triage.md)
    - [5.2.4 Deep Investigation.md](5-Incident%20Case%20Studies/5.2%20Case%202%20–%20SMB%20Brute%20Force/5.2.4%20Deep%20Investigation.md)
    - [5.2.5 Timeline Analysis.md](5-Incident%20Case%20Studies/5.2%20Case%202%20–%20SMB%20Brute%20Force/5.2.5%20Timeline%20Analysis.md)
    - [5.2.6 IOC Extraction.md](5-Incident%20Case%20Studies/5.2%20Case%202%20–%20SMB%20Brute%20Force/5.2.6%20IOC%20Extraction.md)
    - [5.2.7 Threat Level.md](5-Incident%20Case%20Studies/5.2%20Case%202%20–%20SMB%20Brute%20Force/5.2.7%20Threat%20Level.md)
    - [5.2.8 Impact Assessment.md](5-Incident%20Case%20Studies/5.2%20Case%202%20–%20SMB%20Brute%20Force/5.2.8%20Impact%20Assessment.md)
    - [5.2.9 Response Playbook.md](5-Incident%20Case%20Studies/5.2%20Case%202%20–%20SMB%20Brute%20Force/5.2.9%20Response%20Playbook.md)
  - [Cases Plan.md](5-Incident%20Case%20Studies/Cases%20Plan.md)
- [6- Splunk Dashboard](6-%20Splunk%20Dashboard)
  - [6.1 Top Attacking IPs.md](6-%20Splunk%20Dashboard/6.1%20Top%20Attacking%20IPs.md)
  - [6.2 Failed vs Successful Login Trend.md](6-%20Splunk%20Dashboard/6.2%20Failed%20vs%20Successful%20Login%20Trend.md)
  - [6.3 Targeted Users.md](6-%20Splunk%20Dashboard/6.3%20Targeted%20Users.md)
  - [6.4 Post-login Process Activity.md](6-%20Splunk%20Dashboard/6.4%20Post-login%20Process%20Activity.md)
- [7-Incident Response](7-Incident%20Response)
  - [7.1 Containment Actions.md](7-Incident%20Response/7.1%20Containment%20Actions.md)
  - [7.2 Mitigation Recommendations.md](7-Incident%20Response/7.2%20Mitigation%20Recommendations.md)
  - [7.3 Lessons Learned.md](7-Incident%20Response/7.3%20Lessons%20Learned.md)
- [8-Screenshots](8-Screenshots)
  - [8.1. RDP Brute Force](8-Screenshots/8.1.%20RDP%20Brute%20Force)
    - [Event-4624.png](8-Screenshots/8.1.%20RDP%20Brute%20Force/Event-4624.png)
    - [Event-4625.png](8-Screenshots/8.1.%20RDP%20Brute%20Force/Event-4625.png)
    - [Event-4634.png](8-Screenshots/8.1.%20RDP%20Brute%20Force/Event-4634.png)
    - [Event-4648.png](8-Screenshots/8.1.%20RDP%20Brute%20Force/Event-4648.png)
    - [Event-4672.png](8-Screenshots/8.1.%20RDP%20Brute%20Force/Event-4672.png)
    - [Event-Sysmon-1.png](8-Screenshots/8.1.%20RDP%20Brute%20Force/Event-Sysmon-1.png)
    - [Event-Sysmon-10.png](8-Screenshots/8.1.%20RDP%20Brute%20Force/Event-Sysmon-10.png)
    - [Event-Sysmon-3.png](8-Screenshots/8.1.%20RDP%20Brute%20Force/Event-Sysmon-3.png)
    - [Kali-Hydra.png](8-Screenshots/8.1.%20RDP%20Brute%20Force/Kali-Hydra.png)
  - [8.2. SMB Brute Force](8-Screenshots/8.2.%20SMB%20Brute%20Force)
    - [Event-4624.png](8-Screenshots/8.2.%20SMB%20Brute%20Force/Event-4624.png)
    - [Event-4625.png](8-Screenshots/8.2.%20SMB%20Brute%20Force/Event-4625.png)
    - [Event-Sysmon-1.png](8-Screenshots/8.2.%20SMB%20Brute%20Force/Event-Sysmon-1.png)
    - [Event-Sysmon-3.png](8-Screenshots/8.2.%20SMB%20Brute%20Force/Event-Sysmon-3.png)
    - [Kali-Crackmapexec.png](8-Screenshots/8.2.%20SMB%20Brute%20Force/Kali-Crackmapexec.png)
  - [BruteForceScreenshots.md](8-Screenshots/BruteForceScreenshots.md)


**Summary:**  
This lab simulates a full SOC workflow for credential brute-force attacks—from attack simulation, log collection, detection, and investigation to response and hardening. It provides hands-on experience in monitoring, analyzing, and responding to credential-based attacks.
