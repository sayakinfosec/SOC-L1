## 🧭 SOC Metrics and Objectives

### 1️⃣ Room Overview

SOC Metrics and Objectives focuses on how to measure, evaluate, and improve the efficiency of a Security Operations Centre (SOC). It introduces key metrics such as MTTD, MTTA, MTTR, and FPR - and highlights their importance in both operational success and analyst performance evaluation.

---

### 2️⃣ Learning Objectives

1. Understand the core concepts of SLA, MTTD, MTTA, and MTTR.
2. Learn the importance of the False Positive Rate (FPR).
3. Recognize how metrics reflect SOC team efficiency.
4. Apply practical methods to improve metrics as an L1 analyst.
5. Gain hands-on experience with SOC performance management.

---

### 3️⃣ Core SOC Metrics

| **Metric**                      | **Formula**                      | **Measures**                             |
| ------------------------------- | -------------------------------- | ---------------------------------------- |
| **Alerts Count (AC)**           | Total Count of Alerts Received   | SOC workload and alert volume            |
| **False Positive Rate (FPR)**   | False Positives / Total Alerts   | Alert noise level                        |
| **Alert Escalation Rate (AER)** | Escalated Alerts / Total Alerts  | L1 experience and independence           |
| **Threat Detection Rate (TDR)** | Detected Threats / Total Threats | SOC reliability and detection efficiency |

---

### 4️⃣ Insights on Metrics

1. **Alerts Count:** Ideal range - 5–30 alerts/day per analyst.
2. **False Positive Rate:** 0% ideal but unrealistic; ≥80% signals poor tuning.
3. **Alert Escalation Rate:** Should be **below 50%**, ideally **under 20%**.
4. **Threat Detection Rate:** Must target **100%**, as missed threats can be catastrophic.

---

### 5️⃣ Triage Metrics & SLAs

**Key Service Metrics:**

| **Metric**           | **Common SLA** | **Description**                  |
| -------------------- | -------------- | -------------------------------- |
| **SOC Availability** | 24/7           | Continuous operational coverage  |
| **MTTD**             | 5 mins         | Time to detect an attack         |
| **MTTA**             | 10 mins        | Time for L1 to start triage      |
| **MTTR**             | 60 mins        | Time to remediate/contain attack |

---

### 6️⃣ Scenario-Based Example

🧩 **Scenario:**

1. SOC received the “Connection to Redline Stealer C2” alert after **12 minutes**.
2. L1 analyst moved alert to *In Progress* **10 minutes later**.
3. After **6 minutes**, alert escalated to L2, who spent **35 minutes cleaning** malware.

**Calculated Metrics:**

* **MTTD:** 12 minutes
* **MTTA:** 10 minutes
* **MTTR:** 51 minutes

✅ **Final Answer:** `12,10,51`

---

### 7️⃣ Performance Improvement Strategies

| **Issue**                     | **Recommendation**                                                    |
| ----------------------------- | --------------------------------------------------------------------- |
| **False Positive Rate > 80%** | Tune SIEM/EDR rules, exclude trusted activities, use SOAR automation. |
| **MTTD > 30 min**             | Optimize detection rules, ensure real-time log collection.            |
| **MTTA > 30 min**             | Enable instant analyst notifications, balance alert queue workload.   |
| **MTTR > 4 hours**            | Escalate rapidly, use predefined incident playbooks.                  |

---

### 8️⃣ Key Takeaways

1. Zero alerts ≠ good sign - could indicate SIEM misconfiguration or lack of visibility.
2. Maximum acceptable **False Positive Rate:** **80%**.
3. Metrics are vital for both **SOC efficiency** and **career progression**.
4. All SOC roles must collaborate to continuously improve these numbers.

---

### 9️⃣ Assessment Summary

| **Question**                                       | **Answer** |
| -------------------------------------------------- | ---------- |
| Zero alerts for one month - good sign?             | ❌ Nay      |
| FPR if 10 out of 50 are real threats               | ✅ 80%      |
| SOC 8/5 receives weekend alert - acknowledge when? | ✅ Monday   |
| MTTD, MTTA, MTTR for given scenario                | ✅ 12,10,51 |
| Highest acceptable FPR                             | ✅ 80%      |
| Should all SOC roles work together?                | ✅ Yea      |

---

### 🔟 Final Reflection

This room reinforced that numbers tell a story in SOC operations - whether it’s how fast threats are detected, how efficiently analysts act, or how noise impacts alert fatigue. As an L1 analyst, mastering these metrics means understanding not just *what you detect*, but *how effectively* you respond.
