# SOC Monitoring & Wazuh SIEM Project

## Overview

A practical Security Operations Center (SOC) project developed as part of the IT8510 Threat Intelligence and Threat Hunting course.

The project focused on designing and implementing a functional SOC environment using **Wazuh SIEM** as the central security monitoring and detection platform. The environment was extended with threat intelligence, XDR-based detection and response, IDS monitoring, and SOAR automation.

The project demonstrates the complete security monitoring lifecycle:

`Data Collection → Detection → Analysis → Response → Continuous Monitoring`

The implementation was performed in a controlled virtual lab environment using Windows and Linux systems.

---

## Project Objectives

- Design a functional SOC architecture.
- Deploy and configure Wazuh as a centralized SIEM platform.
- Collect and analyze security events from multiple systems.
- Monitor Windows and Linux endpoints.
- Detect and investigate simulated security threats.
- Configure custom detection rules.
- Implement automated security response actions.
- Integrate external Cyber Threat Intelligence (CTI) sources.
- Implement SOAR automation using Shuffle.
- Validate detection and response through logs, alerts, and system evidence.

---

## SOC Architecture

The SOC architecture was designed around multiple security components covering different stages of the security operations lifecycle.

### Core Components

- **SIEM:** Wazuh
- **Threat Intelligence:** VirusTotal, AbuseIPDB, AlienVault OTX
- **Log Management:** Centralized collection and analysis of security logs
- **Endpoint Monitoring:** Wazuh agents
- **IDS/IPS:** Snort
- **File Integrity Monitoring:** Wazuh FIM
- **XDR:** Detection and automated response
- **SOAR:** Shuffle
- **Vulnerability Management:** Security assessment and remediation support

The architecture follows a continuous workflow:

`Data Collection → Detection → Analysis → Response → Continuous Monitoring`

---

## Lab Environment

The project was implemented using a virtualized security environment consisting of:

| System / Tool | Purpose |
|---|---|
| **Wazuh SIEM** | Centralized security monitoring, alerting, and investigation |
| **Windows Server 2022** | Windows endpoint and security event source |
| **Bodhi Linux** | Linux endpoint and SSH monitoring |
| **Snort IDS** | Network intrusion detection |
| **Kali Linux** | Controlled security testing and event generation |
| **Shuffle SOAR** | Security alert automation and notification |
| **Virtual Machines** | Isolated laboratory environment |

Wazuh was deployed as the central platform for collecting, correlating, and analyzing security events from the monitored infrastructure.

---

## Wazuh SIEM Implementation

Wazuh was deployed as the main SIEM platform and configured to provide centralized security monitoring.

The implementation included:

- Wazuh Manager
- Wazuh Indexer
- Wazuh Dashboard
- Wazuh agents
- Windows Server monitoring
- Linux endpoint monitoring
- Snort IDS integration
- File Integrity Monitoring (FIM)
- Custom detection rules
- Active response mechanisms

Security events were collected from monitored systems and presented through the Wazuh dashboard for investigation and response.

---

## XDR Detection & Automated Response

The project included three controlled threat scenarios to demonstrate detection and automated response capabilities through Wazuh.

### 1. SMB Brute-Force Detection

A controlled SMB authentication attack was generated against the Windows Server environment.

Wazuh was configured with a custom detection rule to identify repeated failed authentication attempts.

**Detection:**

- Windows Security logs
- Event ID 4625
- Custom Wazuh detection rule

**Response:**

- Windows Firewall blocking of the identified source

**Validation:**

The response was tested to confirm that the suspicious traffic was successfully blocked.

---

### 2. Malware Detection & Automated Response

The **EICAR test file** was used as a safe test case for malware detection.

Wazuh File Integrity Monitoring detected the new file and triggered VirusTotal-based analysis.

The detection chain included:

`File Creation → FIM Detection → VirusTotal Analysis → Wazuh Alert → Automated Response`

The malicious test file was automatically removed from the monitored endpoint after detection.

This demonstrated the integration of:

- File Integrity Monitoring
- VirusTotal
- Wazuh alerting
- Active response

---

### 3. Suspicious PowerShell Activity

Suspicious PowerShell activity was generated in the controlled environment and monitored using **Sysmon** and Wazuh.

Sysmon recorded the process creation event, while a custom Wazuh rule was used to identify the suspicious activity.

**Detection:**

- Sysmon
- Process creation events
- Custom Wazuh rule
- Wazuh Dashboard

**Response:**

A Windows Firewall outbound rule was configured to restrict network communication from PowerShell.

The response was subsequently validated through network connectivity testing.

---

## Threat Intelligence Integration

External Cyber Threat Intelligence sources were integrated into the SOC environment to enrich security alerts and improve investigation.

### VirusTotal

VirusTotal was integrated with Wazuh to analyze file hashes associated with monitored files.

The workflow included:

`File Detection → Hash Extraction → VirusTotal Analysis → Threat Verdict → Wazuh Alert`

This allowed suspicious files to be enriched with external threat intelligence information.

### AbuseIPDB

AbuseIPDB was evaluated and integrated as an external source for IP reputation and malicious IP intelligence.

This information can support the investigation of suspicious network activity and source addresses.

### AlienVault OTX

AlienVault Open Threat Exchange (OTX) was used as another threat intelligence source for investigating indicators such as:

- IP addresses
- Domains
- File hashes
- Indicators of Compromise (IOCs)

The three CTI sources used in the project were:

`VirusTotal + AbuseIPDB + AlienVault OTX`

---

## SOAR Automation with Shuffle

The project implemented a SOAR workflow by integrating **Wazuh with Shuffle**.

The selected scenario involved SSH brute-force detection on the Bodhi Linux system.

### Workflow

```text
Security Event
      ↓
Wazuh Detection
      ↓
Wazuh Alert
      ↓
Shuffle Webhook
      ↓
Alert Processing
      ↓
Automated Email Notification
      ↓
SOC Analyst

A custom Wazuh rule was configured to detect repeated SSH authentication failures.

When the alert was generated, Wazuh forwarded the alert information to Shuffle through a webhook.

Shuffle then processed the alert and automatically sent an email notification containing the security alert details.

The workflow was successfully executed and the notification was received as expected.

Detection & Response Summary
Security Scenario	Detection	Response
SMB Brute Force	Wazuh + Windows Event Logs	Windows Firewall blocking
Malware / EICAR	Wazuh FIM + VirusTotal	Automated file removal
Suspicious PowerShell	Sysmon + Wazuh	Firewall outbound blocking
SSH Brute Force	Wazuh custom rule	Shuffle automated notification

The three XDR scenarios were successfully detected, responded to, and validated using security logs and system evidence.

Threat Hunting & Security Investigation

The project also focused on threat hunting and security event investigation.

Activities included:

Reviewing security alerts
Analyzing Windows and Linux logs
Investigating authentication failures
Reviewing process creation events
Investigating suspicious files
Analyzing indicators of compromise
Correlating security events
Validating detection rules
Verifying response actions

The goal was to move from simple alert generation toward understanding the activity behind each security event.

Technologies & Tools
SIEM & SOC
Wazuh SIEM
Wazuh Dashboard
Wazuh Agents
SIEM Monitoring
Log Analysis
Security Monitoring
Windows Server 2022
Bodhi Linux
Sysmon
Snort IDS
File Integrity Monitoring
Threat Intelligence
VirusTotal
AbuseIPDB
AlienVault OTX
Cyber Threat Intelligence (CTI)
Indicators of Compromise (IOCs)
Automation
Shuffle SOAR
Webhooks
Automated Email Notifications
Wazuh Active Response
Laboratory
Kali Linux
Virtual Machines
Controlled Security Testing Environment
Key Skills Demonstrated
SOC Operations
SIEM Deployment
Security Monitoring
Alert Investigation
Log Analysis
Threat Detection
Threat Hunting
Cyber Threat Intelligence
XDR Detection & Response
SOAR Automation
Incident Investigation
Security Event Analysis
Detection Rule Configuration
Automated Response
Security Documentation
My Contribution

As part of the project team, I contributed to the technical implementation and documentation of the SOC environment.

My main contributions included:

XDR Detection & Automated Response
Configured and validated XDR detection scenarios.
Worked with Wazuh detection rules.
Investigated security events and alerts.
Configured response actions.
Validated detection and response results.
Documented technical evidence and findings.
Shuffle SOAR Automation
Integrated Wazuh alerts with Shuffle.
Configured the webhook-based alert workflow.
Designed the automated notification process.
Tested the workflow using an SSH brute-force detection scenario.
Verified successful alert processing and email notification.

According to the project peer-review table, my assigned workload covered XDR detection/response and Shuffle SOAR automation, with the assigned work completed.

Project Results

The project successfully demonstrated a functional SOC environment centered around Wazuh.

The final implementation included:

Centralized SIEM monitoring
Windows and Linux security monitoring
Snort IDS integration
XDR detection and automated response
Threat intelligence enrichment
VirusTotal, AbuseIPDB, and AlienVault OTX integration
Shuffle SOAR automation
Automated security notifications
Security event investigation and validation

The overall project demonstrated how open-source security technologies can be combined to create a layered SOC monitoring and response environment.

Project Documentation

The complete project report and supporting evidence are available in this repository.

The documentation contains:

SOC architecture
Threat intelligence analysis
Wazuh deployment
XDR detection and response
SOAR automation
Threat intelligence integration
Detection evidence
Response validation
Project results
Project Structure
SOC-Wazuh-SIEM/
│
├── README.md
│
├── Documentation/
│   └── SOC-Project-Report.pdf
│
├── Evidence/
│   ├── Wazuh/
│   ├── Shuffle/
│   ├── Threat-Intelligence/
│   └── Detection-Response/
│
└── Screenshots/
    ├── Wazuh-Dashboard/
    ├── Shuffle-Workflow/
    └── Security-Alerts/
Learning Outcomes

Through this project, I gained practical experience in:

Building a SOC monitoring environment
Deploying and configuring a SIEM
Investigating security alerts
Working with Windows and Linux security logs
Creating and validating detection rules
Applying threat intelligence to security investigations
Implementing automated security responses
Integrating SIEM with SOAR
Documenting security incidents and technical evidence
Author

Abdulrahman Altairey

Cybersecurity Student
Bahrain Polytechnic

LinkedIn
GitHub


### One important thing

I would **keep this level of detail for GitHub**, but I would **not make it much longer than this**. Your README now tells a recruiter exactly what matters:

**Architecture → Wazuh → Detection → Investigation → CTI → Automated Response → SOAR → Your Contribution**

And importantly, your personal contribution is clearly separated from the group's work, which is useful because the original report shows that your assigned work was specifically **XDR Detection & Automated Response + Shuffle SOAR**. :contentReference[oaicite:7]{index=7}

Also, I deliberately l
