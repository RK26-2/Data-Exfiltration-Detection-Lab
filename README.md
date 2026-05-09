# Data Exfiltration / DLP Detection Lab using Sysmon and Microsoft Sentinel

📌**Executive Summary**

This lab simulates an insider-threat data exfiltration scenario on a Windows endpoint monitored with Sysmon and Microsoft Sentinel. The objective was to detect sensitive file creation, data staging, compression and outbound exfiltration behaviour using custom analytics rules and KQL queries. Sysmon telemetry (EventID 1,3, 11) was ingested into Sentinel via the Azure Monitor Agent and analysed to identify malicious activity.

🛠**Tools & Environment**
   - Azure Windows 11 VM
   - Sysmon (EventID 1, 3, 11)
   - Azure Monitor Agent (AMA)
   - Log Anaytics Workspace
   - Microsoft Sentinel
   - KQL (Kusto Query Language)

🎯**Attack Simulation Overview**
 
 *The following insider-threat behaviours were simulated:*
   - Sensitive files creation
   - File renaming and modification
   - File compression into a ZIP archive
   - Attempted exfiltration to an external service
   - Deleting local evidence
- Sysmon captured the activity and Sentinel was used to analyse and detect the behaviour.

🔍**Detection Logic**

*A custom analytics rule was created to detect:*
- File creation of sensitive data (EventID 11)
- Process execution related to compression (EventID 1)
- Outbound network connections (EventID 3)
- The rule triggered when all three behaviours occurred within a short time window

## 📁 Repository Structure

📦 Data-Exfiltration-Detection-Lab

 ┣ 📄 👉 README.md
 
 ┣ 📄 👉 Full Report: [SOC-Report-DLP.pdf](SOC-Report-DLP.pdf)
 
 ┣ 📁 👉 screenshots : [screenshots](screenshots/)
 
 ┗ 📄 .gitignore


**MITRE ATT&CK Mapping**


| Technique | ID | Description |
| --- | --- | --- |
| Data Staged | T1074 | Sensitive files created and prepared |
| Archive Collected Data | T1560 | ZIP archive created |
| Exfiltration Over Web | T1567 | Outbound connection to external service |


**Sample Screenshots**
https://github.com/RK26-2/Data-Exfiltration-Detection-Lab/tree/main/screenshots


**Lab-Report**
https://github.com/RK26-2/Data-Exfiltration-Detection-Lab/blob/main/SOC-Report-DLP.pdf

📚**What I Learned**
   - Building a full endpoint-to-SIEM telemetry pipeline
   - Using Sysmon to capture security events
   - Writing KQL queries for detection and investigation
   - Creating custom analytics rules in Microsoft Sentinel
   - Mapping activity to MITRE ATT&CK
   - Documenting a SOC-style investigation
