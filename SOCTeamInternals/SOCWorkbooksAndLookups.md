## SOC Workbooks and Lookups

### 1. Introduction

Alert triage is a complex process that often requires analysts to gather additional information about affected users, systems, or servers.
This room introduces **SOC workbooks** and **lookup methods** that simplify and streamline the triage process.

#### Learning Objectives

* Familiarise yourself with SOC investigation workbooks.
* Learn where to find and how to use the asset inventory.
* Understand the importance of corporate network diagrams.
* Practice workflow building inside an interactive interface.

---

### 2. Assets & Identities

To triage effectively, analysts must understand **who** the users are, **what systems** are involved, and **why** an action occurred.

#### 2.1 Identity Inventory

An **identity inventory** is a catalogue of all user and machine accounts in an organisation, including privileges, contacts, and roles.
It helps analysts determine whether a user’s activity is expected or suspicious.

##### Example Scenario

An alert shows **G.Baker** logged into **HQ-FINFS-02**, downloaded a financial report, and shared it with **R.Lund**.
You must verify:

* Who is G.Baker and what’s his role?
* What is HQ-FINFS-02 used for?
* Should R.Lund have access to financial data?

##### Example of Identities

| Full Name     | Username     | Email                                                 | Role                     | Location   | Access           |
| ------------- | ------------ | ----------------------------------------------------- | ------------------------ | ---------- | ---------------- |
| Gregory Baker | G.Baker      | [g.baker@tryhatme.thm](mailto:g.baker@tryhatme.thm)   | Chief Financial Officer  | Europe, UK | VPN, HQ, FINANCE |
| Raymond Lund  | R.Lund       | [r.lund@tryhatme.thm](mailto:r.lund@tryhatme.thm)     | US Financial Adviser     | US, Texas  | VPN, FINANCE     |
| Kate Danner   | K.Danner     | [k.danner@tryhatme.thm](mailto:k.danner@tryhatme.thm) | Chief Technology Officer | Europe, UK | VPN, DA, HQ, AWS |
| svc-veeam-06  | svc-veeam-06 | N/A                                                   | Backup Service Account   | N/A        | VEEAM, DMZ, HQ   |
| svc-nginx-pp  | svc-nginx-pp | N/A                                                   | Web App Service Account  | N/A        | DMZ              |

##### Common Sources of Identity Data

| Source               | Examples               | Description                                     |
| -------------------- | ---------------------- | ----------------------------------------------- |
| **Active Directory** | On-prem AD, Entra ID   | Core identity store for corporate environments. |
| **SSO Providers**    | Okta, Google Workspace | Cloud-based alternatives for managing users.    |
| **HR Systems**       | BambooHR, SAP, HiBob   | Provide detailed employee data.                 |
| **Custom Solutions** | CSV or Excel Sheets    | Often maintained by IT or Security teams.       |

---

### 3. Asset Inventory

An **asset inventory** (or asset lookup) lists all computing resources in the organisation.
It helps determine device purpose, owner, and location when investigating alerts.

##### Example of Assets

| Hostname    | Location      | IP Address   | OS                  | Owner             | Purpose                           |
| ----------- | ------------- | ------------ | ------------------- | ----------------- | --------------------------------- |
| HQ-FINFS-02 | UK Datacenter | 172.16.15.89 | Windows Server 2022 | Central IT        | File server for financial records |
| HQ-ADDC-01  | UK Datacenter | 172.16.15.10 | Windows Server 2019 | Central IT        | Primary AD domain controller      |
| PC-891D     | London Office | 192.168.5.13 | Windows 11 Pro      | Tech Support      | Workstation for accountants       |
| L007694     | Remote        | N/A          | macOS 13            | A. Kelly (DevOps) | Corporate laptop                  |
| L005325     | Remote        | N/A          | macOS 13            | J. Eldridge (HR)  | Corporate laptop                  |

##### Common Sources of Asset Data

| Source               | Examples             | Description                                      |
| -------------------- | -------------------- | ------------------------------------------------ |
| **Active Directory** | On-prem AD, Entra ID | Contains both identity and asset data.           |
| **SIEM / EDR**       | Elastic, CrowdStrike | Collect host information from monitored systems. |
| **MDM Solutions**    | MS Intune, Jamf MDM  | Manage endpoints and maintain device lists.      |
| **Custom Solutions** | CSV or Excel Sheets  | Frequently used for smaller organisations.       |

---

### 4. Network Diagrams

Network diagrams provide **context on network structure and relationships** between subnets, firewalls, and services - essential for network-related alerts.

#### 4.1 Example Scenario

A series of firewall logs show suspicious connections:

* 08:00 → External IP `103.61.240.174` connects to port `TCP/10443`.
* 08:23 → Translated to internal IP `10.10.0.53`.
* 08:25 → `10.10.0.53` scans the `172.16.15.0/24` subnet.
* 08:32 → Moves to `172.16.23.0/24`.

A network diagram helps analysts:

* Identify the exposed service on port 10443.
* Determine subnets involved.
* Reconstruct the **attack path** from VPN → Database → Office network.

#### 4.2 Key Insight

Even complex networks can be understood faster with accurate visual diagrams, helping SOC analysts map intrusion flows and containment strategies.

---

### 5. Workbooks Theory

While lookups and inventories provide context, **workbooks** ensure analysts follow the right **investigation sequence** without skipping critical steps.

#### 5.1 What Are SOC Workbooks?

A **SOC workbook** (or **playbook**, **runbook**, **workflow**) is a structured guide defining how to handle specific alerts - ensuring consistency, quality, and completeness.

Senior analysts create these for L1 analysts to reduce errors and improve efficiency.

#### 5.2 Example Workbook: “Unusual Login Location”

This workbook guides analysts through:

1. **Enrichment:** Use Threat Intel and HR data (e.g., BambooHR) to understand the user context.
2. **Investigation:** Review SIEM logs and behavioural data to determine if the login is expected.
3. **Escalation:** Escalate to L2 or communicate with the user if required.

##### Platforms Mentioned

* **Identity Source:** BambooHR
* **Context Gathering Process:** Enrichment
* **Primary Users of Workbooks:** SOC L1 Analysts

---

### 6. Key Takeaways

* **Identity and asset inventories** are critical for contextual alert triage.
* **Network diagrams** help visualise connections and spot unusual network paths.
* **Workbooks** provide structure and standardisation for incident investigations.
* Effective **lookup and workbook use** enhances consistency and decision-making speed in SOC operations.

