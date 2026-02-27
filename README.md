## SOAR-EDR Automated Incident Response Lab

##  Project Overview

This project demonstrates the integration of an Endpoint Detection and Response (EDR) platform with a Security Orchestration, Automation, and Response (SOAR) system to build an automated incident response pipeline.

The objective is to automatically detect suspicious activity on endpoints and trigger automated containment actions without manual intervention.

---

##  Architecture

The lab integrates:

- LimaCharlie (EDR)
- Tines (SOAR)
- Slack (Notification System)

### Workflow:

1. Endpoint monitored by EDR agent.
2. Suspicious process behavior detected.
3. Alert sent to SOAR via webhook.
4. SOAR enriches alert context.
5. Automated endpoint isolation triggered.
6. Notification sent to SOC team.

---

##  Technologies Used

- LimaCharlie (EDR)
- Tines (SOAR Automation)
- Slack Webhooks
- REST APIs
- JSON Playbooks
- Detection Engineering Rules

---

##  Detection Logic

The detection rule monitors:

- Suspicious PowerShell execution
- Encoded commands
- Unusual parent-child process relationships

Example:
- powershell.exe with encoded commands
- Suspicious command-line arguments

---

##  SOAR Playbook Logic

The automated workflow performs:

- Alert validation
- Context enrichment
- Conditional logic (if severity high)
- Endpoint isolation via API
- Notification to Slack

---

##  MITRE ATT&CK Mapping

- T1059 – Command and Scripting Interpreter
- T1562 – Impair Defenses
- T1071 – Application Layer Protocol

---

## Key Skills Demonstrated

- Incident Response Automation
- Detection Engineering
- API Integration
- SOC Workflow Design
- Endpoint Containment
- Threat Enrichment
- Security Architecture Design

---

##  Results

- Reduced response time from manual (~15 minutes) to automated (<30 seconds)
- Automated containment of compromised endpoint
- Improved SOC efficiency

---

##  Future Improvements

- VirusTotal enrichment integration
- Automated ticket creation (JIRA)
- Threat intelligence correlation
- Multi-endpoint orchestration

---

## Author

[Abdullah Mustafa]
Cybersecurity | SOC | DFIR
