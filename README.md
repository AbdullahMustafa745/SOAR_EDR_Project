SOC Automation — Wazuh, Shuffle & TheHive Incident Response Lab

Project Overview

This project demonstrates a fully automated Security Operations Center (SOC) pipeline integrating a SIEM, SOAR, and case management platform to detect, enrich, and respond to threats without manual intervention.

The objective is to automatically detect malicious activity on Windows endpoints, orchestrate a response workflow, and notify the SOC analyst all within seconds of detection.

Architecture

The lab integrates:
- Wazuh (SIEM / EDR)
- Shuffle (SOAR)
- TheHive (Case Management)
- VirusTotal (IOC Enrichment)
- Email (Analyst Notification)

 Workflow:
1. Windows 10 endpoint monitored by Wazuh Agent + Sysmon.
2. Suspicious activity detected (e.g., Mimikatz execution).
3. Alert forwarded to Shuffle via webhook.
4. SOAR enriches IOCs using VirusTotal API.
5. Case automatically created in TheHive.
6. SOC analyst notified via email with full alert context.
7. Analyst approves response action via email reply.
8. Wazuh performs active response on the endpoint.


Technologies Used

- Wazuh (SIEM / EDR / Active Response)
- Sysmon (Windows Endpoint Telemetry)
- Shuffle (SOAR Automation)
- TheHive (Case Management)
- VirusTotal API (IOC Enrichment)
- Email / SMTP (Analyst Notification)
- Detection Engineering Rules (XML)
- MITRE ATT&CK Framework


Detection Logic

Custom Wazuh rules monitor:
- Credential dumping tools (Mimikatz)
- SSH authentication failures
- Suspicious process execution via Sysmon event logs
- Unusual parent-child process relationships

Example detections:
- mimikatz.exe executed on endpoint → Rule 100002 triggered (Level 15)
- Repeated SSH failures from same IP → Rule 100001 triggered (Level 5)


SOAR Playbook Logic

The automated Shuffle workflow performs:
- Webhook trigger on Wazuh alert
- IOC hash lookup via VirusTotal API
- Conditional logic (if severity ≥ 10)
- Automatic case creation in TheHive
- Enriched email notification to SOC analyst
- Active response command sent back to Wazuh


MITRE ATT&CK Mapping

T1003 – OS Credential Dumping (Mimikatz)
T1110 – Brute Force (SSH Authentication Failures)
T1059 – Command and Scripting Interpreter
T1071 – Application Layer Protocol


Key Skills Demonstrated

- Incident Response Automation
- Detection Engineering (Custom Wazuh Rules)
- SOAR Workflow Design
- API Integration (VirusTotal, TheHive, Wazuh)
- Endpoint Active Response
- IOC Enrichment
- MITRE ATT&CK Mapping
- Security Architecture Design


Results

- Reduced response time from manual (15 minutes) to automated (<30 seconds)
- Automated case creation and analyst notification on every alert
- Endpoint containment triggered without manual intervention
- Full audit trail maintained in TheHive for every incident


 Author

Abdullah Mustafa
Cybersecurity | SOC 
