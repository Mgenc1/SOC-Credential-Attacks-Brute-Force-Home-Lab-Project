# 🔐 SOC Credential Attacks – Brute Force Home Lab Project

## 📌 Overview

This project demonstrates a **realistic brute-force credential attack simulation** within a controlled home lab environment. The objective is to simulate attacker behavior, generate logs, detect malicious activity using SIEM, and perform SOC-level investigation and response.

The project is designed to reflect the workflow of a **Tier 1 SOC Analyst**, including:

* Attack simulation
* Log collection
* Detection & analysis
* Incident response

---

## 🎯 Objectives

* Simulate a brute-force attack against a Windows system
* Analyze authentication logs (Event IDs 4624 / 4625)
* Detect suspicious login patterns
* Map activity to MITRE ATT&CK framework
* Demonstrate SOC investigation workflow

---

## 🏗️ Lab Architecture

| Component        | Description                        |
| ---------------- | ---------------------------------- |
| Attacker Machine | Kali Linux (Brute-force attack)    |
| Target Machine   | Windows 11 (Victim system)         |
| SIEM             | Splunk Enterprise                  |
| Logging          | Sysmon + Windows Event Logs        |
| Network          | Internal lab network (192.168.x.x) |

---

## ⚔️ Attack Scenario

A brute-force attack is launched from a Kali Linux machine targeting a Windows 11 system over RDP.

### Attack Details

| Attribute      | Value                           |
| -------------- | ------------------------------- |
| Attack Type    | Brute Force (Credential Access) |
| Protocol       | RDP (TCP 3389)                  |
| Tool Used      | Hydra / CrackMapExec            |
| Target Account | testuser                        |
| Outcome        | Multiple failures → Success     |

---

## 📊 Log Analysis

### Key Windows Event IDs

| Event ID | Description        | Meaning              |
| -------- | ------------------ | -------------------- |
| 4625     | Failed Login       | Brute-force attempt  |
| 4624     | Successful Login   | Potential compromise |
| Sysmon 1 | Process Creation   | Post-login activity  |
| Sysmon 3 | Network Connection | Outbound connections |

---

## 🔎 Detection Logic

The detection is based on identifying abnormal authentication behavior:

### Indicators of Compromise (IOCs)

* High number of failed logins (Event ID 4625)
* Rapid login attempts within short time
* Successful login after multiple failures
* Suspicious source IP address

### Detection Rule Example (Conceptual)

| Condition           | Threshold        |
| ------------------- | ---------------- |
| Failed Logins       | > 10 attempts    |
| Time Window         | 5 minutes        |
| Followed by Success | Yes (Event 4624) |

---

## 🧠 MITRE ATT&CK Mapping

| Tactic            | Technique ID | Technique Name |
| ----------------- | ------------ | -------------- |
| Credential Access | T1110        | Brute Force    |
| Initial Access    | T1078        | Valid Accounts |

---

## 🧪 Investigation Process

### Step-by-Step Analysis

1. Identify alert (multiple failed logins)
2. Verify source IP and target account
3. Check for successful login event (4624)
4. Analyze post-login activity (Sysmon logs)
5. Determine if compromise occurred
6. Escalate if necessary

---

## 🚨 Incident Response

### Response Actions

| Action             | Description                    |
| ------------------ | ------------------------------ |
| Account Lock       | Disable compromised account    |
| Password Reset     | Enforce strong password policy |
| Source IP Blocking | Block attacker IP              |
| Log Review         | Investigate further activity   |
| Monitoring         | Increase alert sensitivity     |

---

## 📈 Key Findings

* Multiple failed login attempts detected
* Successful login achieved after brute-force
* Suspicious activity confirmed
* Attack aligns with MITRE T1110

---

## ⚠️ Business Impact

If this attack occurred in a real environment:

* Unauthorized access to user accounts
* Potential data breach
* Lateral movement risk
* Loss of confidentiality and integrity

---

## 🛡️ Recommendations

* Implement account lockout policies
* Enforce strong password requirements
* Enable multi-factor authentication (MFA)
* Monitor login anomalies in SIEM
* Use automated alerting rules

---

## 📸 Screenshots

> (Add your Splunk dashboards, logs, and attack screenshots here)

---

## 📚 Skills Demonstrated

* SOC Analysis (Tier 1)
* Log Analysis (Windows + Sysmon)
* SIEM (Splunk)
* Threat Detection
* Incident Response
* MITRE ATT&CK Mapping

---

## 🧾 Conclusion

This project demonstrates the end-to-end lifecycle of a brute-force attack from detection to response. It highlights the importance of monitoring authentication logs and implementing proactive security controls.

