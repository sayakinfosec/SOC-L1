# SOC L1 Alert Triage

### 1. Introduction

An alert is a SOC team’s early-warning signal. Proper handling determines whether a breach is detected and contained - or missed with serious impact. This primer is an entry-level, practical guide for SOC L1 analysts covering the alert lifecycle: from event generation to triage and resolution.

---

### 2. Learning Objectives

* Understand what a SOC alert is and how it is formed
* Read and interpret core alert fields, statuses, and verdicts
* Triage alerts as an L1 analyst using practical steps
* Practice with real alerts and SOC workflows
* Prepare for SOC Simulator and SAL1 certification

---

### 3. Prerequisites

* Basic knowledge of common attacks on networks, Windows, and Linux
* Familiarity with SOC roles and responsibilities, especially L1 duties

---

### 4. Events → Alerts (Quick Flow)

1. **Event occurs:** e.g., user login, process launch, file download.
2. **Event logged** by OS, firewall, cloud provider, etc.
3. **Logs shipped** to security platforms (SIEM, EDR, NDR).
4. **Detection rules** trigger when suspicious patterns appear → **Alert created**.

> Alerts reduce millions of raw logs to a manageable queue of suspicious items for analysts.

---

### 5. Alert Management Platforms (Examples)

| Solution  |                        Examples | Role                                              |
| --------- | ------------------------------: | ------------------------------------------------- |
| SIEM      |         Splunk ES, Elastic SIEM | Central alert aggregation, correlation and triage |
| EDR / NDR | Microsoft Defender, CrowdStrike | Endpoint/network detections (feeds into SIEM)     |
| SOAR      |       Splunk SOAR, Cortex XSOAR | Orchestrate and automate responses                |
| ITSM      |                   Jira, TheHive | Ticketing / incident tracking                     |

---

### 6. L1 Analyst: Role at a Glance

* First line of defence: review, validate, and filter alerts.
* Escalate confirmed threats to L2 for deeper analysis and remediation.
* Keep alert metadata and comments clear so escalations are efficient.
* Work with SOC engineers to improve detection signal quality.

---

### 7. Core Alert Properties (Read Every Alert for These)

* **Alert time / Event time** - when the alert was created vs. when the event occurred.
* **Name** - summary derived from the detection rule (e.g., *Unusual Login Location*).
* **Severity** - Low / Medium / High / Critical (initially set by detection engineering).
* **Status** - New, In Progress, Closed / Resolved (team-defined statuses may vary).
* **Verdict / Classification** - True Positive / False Positive (or custom verdicts).
* **Assignee / Owner** - who is responsible for the triage.
* **Description** - detection logic, why it matters, triage hints.
* **Fields / Indicators** - hostnames, IPs, commandlines, user IDs, etc.

---

### 8. Prioritisation - Which Alert to Pick

1. **Filter**: skip alerts already being handled or closed.
2. **Severity**: handle Critical → High → Medium → Low.
3. **Time**: older relevant alerts first (older breaches can cause more damage).

> Prioritisation rules are often automated in the SIEM - understand your team’s ordering.

---

### 9. Alert Triage: Step-by-Step (L1)

#### 9.1 Initial Actions

* Assign the alert to yourself and set status to *In Progress*.
* Read the alert name, description, and key fields.
* Confirm you won’t duplicate work another analyst is doing.

#### 9.2 Investigation (Actionable Checks)

* Identify the affected assets (user, hostname, cloud account).
* Note the activity type (suspicious login, malware, phishing, lateral movement).
* Review surrounding events (before & after) for context and escalation indicators.
* Use available workbooks/playbooks when present; follow runbook steps.
* Consult threat intelligence or known indicators if needed.

#### 9.3 Final Actions

* Decide verdict: **True Positive** (malicious) or **False Positive** (benign/no threat).
* Add a clear, concise comment describing your evidence and reasoning.
* If malicious: escalate to L2 and follow escalation playbook (attach logs, IOCs, timeline).
* If benign: document why and close the alert with the chosen status.

---

### 10. Practical Tips

* Be concise but thorough in comments - a later analyst depends on your notes.
* Preserve timestamps and raw event IDs when attaching evidence.
* When unsure, escalate rather than close prematurely.
* Keep learning detection logic: knowing how rules work improves triage speed.

---

### 11. Quick Checklist (L1)

* [ ] Assigned to self and status set to In Progress
* [ ] Read description, fields, and verdict hints
* [ ] Reviewed surrounding events and assets
* [ ] Applied workbook/runbook steps (if available)
* [ ] Documented findings, verdict, and next steps
* [ ] Closed or escalated with clear evidence

---

### 12. Closing Note

Effective alert handling is disciplined, repeatable work. As an L1 analyst, your decisions form the backbone of timely detection and response. Practice with sample alerts, follow playbooks, and keep your notes crisp - this is how you ensure attackers are found, not missed.
