## Introduction to EDR

### 1. Introduction
Endpoint Detection and Response (EDR) is a security solution designed to monitor, detect, and respond to advanced threats at the endpoint level. As a SOC analyst, understanding EDR is essential because it provides deep visibility, advanced detection, and response capabilities beyond traditional antivirus tools.

---

### 2. Learning Objectives
1. Understand the basics of EDR and how it works  
2. Differentiate EDR from traditional antivirus solutions  
3. Examine EDR architecture  
4. Analyze endpoint telemetry collected by EDR  
5. Understand detection and response capabilities  
6. Investigate a realistic alert in an EDR  

---

### 3. What is an EDR?
The rise of digital devices and remote work exposes endpoints beyond traditional perimeter defenses. EDR provides continuous monitoring, advanced threat detection, and response capabilities regardless of where the endpoint is located.

Common EDR solutions:
- CrowdStrike Falcon  
- SentinelOne ActiveEDR  
- Microsoft Defender for Endpoint  
- OpenEDR  
- Symantec EDR  

---

### 4. Core Features of EDR

#### 4.1 Visibility
EDR collects rich telemetry including:
- Process modifications  
- Registry changes  
- File/folder modifications  
- User actions  
- Network connections  

It presents complete context through features like process trees, historical activity, and event timelines.

**Answer:** *Visibility provides complete context for detections.*

#### 4.2 Detection
EDR combines:
- Signature-based detection  
- Behavior-based detection  
- Machine learning  
- Custom IOCs  

It detects suspicious behavior, parent-child anomalies, fileless malware, and more.

**Answer:** *sc.exe was spawned by cmd.exe.*

#### 4.3 Response
Analysts can:
- Isolate endpoints  
- Terminate processes  
- Quarantine files  
- Remotely access endpoints  

EDRs centralize powerful remediation actions within the console.

---

### 5. Beyond the Antivirus

#### 5.1 AV vs EDR Analogy
- **Antivirus = Immigration Check**  
- **EDR = Security Officers Inside Airport**

AV identifies known threats; EDR identifies suspicious behavior and responds in real time.

#### 5.2 Scenario Comparison
EDR detects:
- Macro execution anomalies  
- Obfuscated PowerShell  
- Process injection  
- Lateral movement indicators  

**Answers:**  
- AV represents: *immigration check*  
- Hijacked process: *svchost.exe*  
- Might mark activity as clean: *Antivirus*  

---

### 6. How an EDR Works

#### 6.1 Agents
Agents (sensors) collect and send telemetry to the EDR console.

**Answer:**  
- Telemetry collector: *Agent*  
- Another name: *Sensor*  

#### 6.2 EDR Console
Correlates telemetry, applies ML, evaluates threats, assigns severity, and presents alerts.

#### 6.3 Integration With Other Tools
EDR works alongside firewalls, DLP, IAM, email gateways, and is aggregated within SIEM for unified investigations.

---

### 7. EDR Telemetry

#### 7.1 What is Telemetry?
Telemetry includes endpoint events required for detection and investigation.

#### 7.2 Types of Telemetry
- **Process Execution**  
- **Network Connections** → Helps detect C2 communications  
- **Command Line Activity**  
- **File/Folder Modifications**  
- **Registry Modifications** → Windows configuration store  

**Answers:**  
- C2 detection: *Network Connections*  
- Windows config store: *Registry*  

---

### 8. Detection and Response Capabilities

#### 8.1 Detection Techniques
- Behavioral detection  
- Anomaly detection  
- IOC Matching → identifies known malicious behavior  
- MITRE ATT&CK Mapping  
- Machine Learning  

**Answer:** *IOC Matching*

#### 8.2 Response Techniques
- Host isolation  
- Process termination  
- File quarantine  
- Remote shell access  
- Artefact collection (memory dumps, logs, registry hives)

---

### 9. Investigating an Alert

#### Answers to Scenario Questions
1. Tool launched by CMD.exe: **CURL.exe**  
2. Path to downloaded malware: **C:\Users\Public\install.exe**  
3. Path to suspicious syncsvc.exe: **C:\Users\haris.khan\AppData\Local\Temp\syncsvc.exe**  
4. Exfiltration URL: **https://files-wetransfer.com/upload/session/ab12cd34ef56/dump_2025.dmp**  
5. UpdateAgent.exe label: **Known internal IT utility tool**  

---

### 10. Summary
EDR delivers advanced visibility, behavior-based detection, and powerful response capabilities, far surpassing traditional antivirus. It forms a critical part of modern SOC operations by enabling complete endpoint monitoring, rapid triage, and effective containment of threats.

