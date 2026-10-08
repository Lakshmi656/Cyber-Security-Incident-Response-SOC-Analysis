# Cyber Security Incident Response & SOC Analysis

## 📌 Project Overview

This project simulates the role of a **Security Operations Center (SOC) Analyst** investigating a suspected security incident on a Windows endpoint.

The investigation focuses on detecting and analyzing **repeated failed authentication attempts**, investigating Windows Security Event ID **4625**, classifying the incident, performing containment and recovery, and documenting preventive security controls.

This project was performed in a **controlled laboratory environment** for cybersecurity learning and portfolio development.

---

## 🎯 Objectives

- Detect suspicious authentication activity
- Analyze Windows Security Event Logs
- Investigate Event ID 4625
- Identify the affected user account and source
- Classify the security incident
- Perform incident containment
- Perform recovery
- Develop an incident timeline
- Identify root cause and lessons learned
- Recommend preventive security controls
- Document the complete incident response lifecycle

---

## 🧪 Lab Environment

| Component | Details |
|---|---|
| Operating System | Windows 11 |
| Hostname | `DESKTOP-IC8QE5D` |
| Test Account | `soc-test` |
| Log Source | Windows Security Event Log |
| Event ID | `4625` |
| Logon Type | `2 - Interactive` |
| Source Address | `::1` (localhost) |
| Environment | Controlled Security Lab |
| Analyst Role | SOC Analyst |

---

## 🚨 Incident Scenario

A simulated security incident was created by generating multiple failed authentication attempts against a test account named `soc-test`.

The Windows Security logs were then examined to determine:

- What happened
- Which account was affected
- Why authentication failed
- Where the request originated
- Whether repeated activity was present
- What containment action should be taken
- How the account could be safely recovered

---

## 🔍 Incident Detection

Windows Security Event ID **4625** was identified during the investigation.

Event ID 4625 indicates that an account failed to log on.

Three relevant failed authentication events were identified:

| Date | Time | Event |
|---|---|---|
| 07-Oct-2026 | 3:16:55 PM | Failed logon |
| 07-Oct-2026 | 3:21:32 PM | Failed logon |
| 07-Oct-2026 | 5:49:12 PM | Failed logon |

---

## 🔎 Investigation Findings

The detailed Event ID 4625 information showed:

| Field | Finding |
|---|---|
| Event ID | `4625` |
| Affected Account | `soc-test` |
| Logon Type | `2 - Interactive` |
| Failure Reason | Unknown username or bad password |
| Status | `0xC000006D` |
| Sub Status | `0xC000006A` |
| Source Network Address | `::1` |
| Workstation | `DESKTOP-IC8QE5D` |
| Logon Process | `seclogo` |
| Authentication Package | `Negotiate` |

### Interpretation

The events indicate repeated failed authentication attempts against the `soc-test` account.

The source address `::1` represents the **localhost**, meaning the activity originated from the same Windows system used for the controlled laboratory exercise.

The evidence does **not** establish a confirmed external attacker or a confirmed brute-force attack.

---

## 🏷️ Incident Classification

**Incident Category:** Authentication / Account Access

**Incident Type:** Suspected repeated failed authentication attempts

**Severity:** Low–Medium

**Confidence:** Moderate

**Status:** Contained and Recovered

The incident was classified based on the available Windows Security log evidence.

---

## ⏱️ Incident Timeline

| Time | Event | SOC Action |
|---|---|---|
| 3:16:55 PM | First Event ID 4625 detected | Authentication failure identified |
| 3:21:32 PM | Second Event ID 4625 detected | Repeated failure investigated |
| 5:49:12 PM | Third Event ID 4625 detected | Repeated authentication activity confirmed |
| After detection | Event details reviewed | Account, logon type, failure reason and source investigated |
| After investigation | `soc-test` disabled | Containment performed |
| After containment | `soc-test` re-enabled | Recovery completed |

---

## 🛡️ Containment

The suspected test account was temporarily disabled to prevent further authentication attempts while the incident was being investigated.

Command used:

```cmd
net user soc-test /active:no
```

The account status was verified as:

```text
Account active               No
```

This demonstrated a basic account-level containment procedure.

---

## 🔄 Recovery

After the investigation and containment stage, the test account was re-enabled.

Command used:

```cmd
net user soc-test /active:yes
```

The account status was verified as:

```text
Account active               Yes
```

This restored the test account after the simulated incident response process was completed.

---

## 🧠 Root Cause Analysis

This project was performed as a **controlled cybersecurity laboratory simulation**.

The failed authentication activity was intentionally generated using incorrect credentials to simulate suspicious login behavior.

Therefore, the investigation did not establish evidence of a real external compromise.

### Root Cause

**Simulated incorrect authentication attempts against the `soc-test` account.**

---

## 📚 Lessons Learned

The investigation demonstrated several important SOC concepts:

- Windows Security logs provide valuable authentication evidence.
- Event ID 4625 can be used to identify failed authentication attempts.
- Authentication events should be investigated using account, logon type, failure reason and source information.
- Repeated failed authentication activity should be monitored.
- Suspicious accounts can be temporarily disabled during investigation.
- Recovery should be performed after appropriate investigation and containment.
- SOC analysts should avoid classifying an incident as a confirmed attack without sufficient evidence.
- Proper documentation is an important part of incident response.

---

## 🔐 Preventive Security Controls

The following controls are recommended for a production environment:

| Security Control | Recommendation |
|---|---|
| Account Lockout | Configure appropriate failed-login thresholds |
| Multi-Factor Authentication | Enable MFA for important accounts |
| Password Policy | Enforce strong password requirements |
| SIEM | Centralize Windows security logs |
| Alerting | Monitor repeated Event ID 4625 events |
| Least Privilege | Limit unnecessary account privileges |
| Log Retention | Maintain security logs for investigation |
| Monitoring | Continuously monitor authentication activity |
| Incident Response | Maintain documented SOC response procedures |
| Security Awareness | Train users on secure authentication practices |

---

## 🖼️ Evidence

The project includes screenshots demonstrating the major stages of the investigation.

### Evidence 1 — Test Account Setup

Shows creation and verification of the controlled SOC test account.

### Evidence 2 — Failed Authentication

Shows Windows Security Event ID 4625 associated with the failed authentication activity.

### Evidence 3 — Event Investigation

Shows detailed Event ID 4625 information including the affected account, failure reason and source address.

### Evidence 4 — Incident Timeline

Shows the identified failed authentication events and their timestamps.

### Evidence 5 — Containment

Shows the `soc-test` account being disabled during incident containment.

### Evidence 6 — Recovery

Shows the `soc-test` account being re-enabled after the investigation.

---

## 📂 Project Structure

```text
Cyber-Security-Incident-Response-SOC-Analysis/
│
├── README.md
│
├── screenshots/
│   ├── 01_Soc-Test_User_Credential_Setup.png
│   ├── 02_Failed_Login_Event_4625.png
│   ├── 04_SOC_Failed_Login_Event_4625_Details.png
│   ├── 05_Incident_Timeline_4625.png
│   ├── 06_Containment_Disable_Suspicious_Account.png
│   └── 07_Recovery_Reenable_Test_Account.png
│
├── report/
│   └── Cyber_Security_Incident_Response_SOC_Report.pdf
│
└── evidence/
    └── incident-timeline.txt
```

---

## 🛠️ Tools & Technologies

- Windows 11
- Windows Security Event Viewer
- Windows Event ID 4625
- Command Prompt
- PowerShell
- VMware Workstation
- Cybersecurity Incident Response Methodology

---

## 🔄 Incident Response Lifecycle

```text
Detection
    ↓
Investigation
    ↓
Classification
    ↓
Containment
    ↓
Recovery
    ↓
Lessons Learned
    ↓
Preventive Controls
```

---

## ⚠️ Scope & Disclaimer

This project was performed in an isolated and controlled laboratory environment for educational and portfolio purposes.

No unauthorized systems were targeted, and no real malware or external attack was used.

The findings and screenshots represent a simulated incident response exercise rather than a real-world security incident.

---

## 👩‍💻 Author

**Lakshmi Subhaja Kari**

**B.Tech – Cybersecurity**

**Role Simulated:** SOC Analyst

**Project Year:** 2026
