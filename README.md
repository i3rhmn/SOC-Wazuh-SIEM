🛡️ SOC Monitoring & Wazuh SIEM Project
=======================================

A practical **Security Operations Center (SOC)** project developed for the **IT8510 – Threat Intelligence and Threat Hunting** course.

The project demonstrates the design and implementation of a controlled SOC environment using **Wazuh SIEM** as the central security monitoring and detection platform, integrated with **Threat Intelligence, XDR, IDS, and SOAR automation**.

**Security Monitoring Lifecycle**

Data Collection → Detection → Analysis → Response → Continuous Monitoring

🎯 Project Objectives
---------------------

*   Design and implement a functional SOC architecture
    
*   Deploy and configure **Wazuh SIEM**
    
*   Monitor Windows and Linux endpoints
    
*   Collect and analyze security events
    
*   Create and validate custom detection rules
    
*   Perform controlled threat detection scenarios
    
*   Integrate Cyber Threat Intelligence (CTI)
    
*   Implement automated response mechanisms
    
*   Integrate **Wazuh with Shuffle SOAR**
    
*   Validate detection and response using security evidence
    

🏗️ SOC Architecture
--------------------

### Core Components

ComponentPurpose**Wazuh SIEM**Centralized monitoring, detection, alerting, and investigation**Wazuh Agents**Endpoint monitoring and log collection**Snort IDS**Network intrusion detection**Sysmon**Windows process and system activity monitoring**VirusTotal**File and hash threat intelligence**AbuseIPDB**IP reputation intelligence**AlienVault OTX**IOC and threat intelligence investigation**Shuffle SOAR**Security automation and alert notification**Kali Linux**Controlled security testing**Virtual Machines**Isolated security laboratory

The architecture follows a continuous security operations workflow:

Collect → Detect → Investigate → Respond → Monitor

🖥️ Lab Environment
-------------------

The project was implemented in an isolated virtual laboratory using:

*   **Windows Server 2022**
    
*   **Bodhi Linux**
    
*   **Kali Linux**
    
*   **Wazuh SIEM**
    
*   **Snort IDS**
    
*   **Sysmon**
    
*   **Shuffle SOAR**
    
*   **Virtual Machines**
    

Wazuh served as the central platform for collecting, correlating, and analyzing security events.

🔍 XDR Detection & Automated Response
-------------------------------------

Three controlled security scenarios were implemented to demonstrate detection and automated response.

### 1\. SMB Brute-Force Detection

**Detection**

*   Windows Security Logs
    
*   Event ID **4625**
    
*   Custom Wazuh detection rule
    

**Response**

*   Windows Firewall blocking of the identified source
    

The response was validated through controlled testing.

### 2\. Malware Detection – EICAR

The **EICAR test file** was used as a safe malware-detection test case.

**Detection Chain**

File Creation → FIM Detection → VirusTotal Analysis → Wazuh Alert → Automated Response

The test file was automatically removed after detection.

### 3\. Suspicious PowerShell Activity

Suspicious PowerShell activity was generated in the controlled environment and monitored using **Sysmon and Wazuh**.

**Detection**

*   Sysmon process creation events
    
*   Custom Wazuh rule
    
*   Wazuh Dashboard
    

**Response**

*   Windows Firewall outbound restriction
    

Network connectivity was then tested to validate the response.

🌐 Threat Intelligence Integration
----------------------------------

The SOC environment incorporated multiple external CTI sources:

*   **VirusTotal** – File and hash analysis
    
*   **AbuseIPDB** – IP reputation and malicious IP intelligence
    
*   **AlienVault OTX** – Investigation of IPs, domains, hashes, and IOCs
    

**Threat Intelligence Workflow**

Indicator → Intelligence Lookup → Threat Verdict → Security Investigation

⚙️ SOAR Automation with Shuffle
-------------------------------

Wazuh was integrated with **Shuffle SOAR** to automate security alert processing and notification.

The demonstrated scenario involved **SSH brute-force detection** on the Bodhi Linux system.

```
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
```
The workflow was tested successfully, including alert processing and email notification.

📊 Detection & Response
-----------------------

Security ScenarioDetectionResponse**SMB Brute Force**Wazuh + Windows LogsWindows Firewall Blocking**EICAR Test File**Wazuh FIM + VirusTotalAutomated File Removal**Suspicious PowerShell**Sysmon + WazuhFirewall Outbound Blocking**SSH Brute Force**Wazuh Custom RuleShuffle Notification

🔎 Threat Hunting & Investigation
---------------------------------

The project also involved practical security investigation activities:

*   Security alert analysis
    
*   Windows and Linux log analysis
    
*   Authentication failure investigation
    
*   Process creation analysis
    
*   Suspicious file investigation
    
*   IOC analysis
    
*   Event correlation
    
*   Detection-rule validation
    
*   Response verification
    

The objective was to understand the activity behind security alerts rather than simply generate alerts.

🧰 Technologies & Tools
-----------------------

**SOC / SIEM**

*   Wazuh SIEM
    
*   Wazuh Dashboard
    
*   Wazuh Agents
    
*   SIEM Monitoring
    
*   Log Analysis
    

**Security Monitoring**

*   Windows Server 2022
    
*   Bodhi Linux
    
*   Sysmon
    
*   Snort IDS
    
*   File Integrity Monitoring
    

**Threat Intelligence**

*   VirusTotal
    
*   AbuseIPDB
    
*   AlienVault OTX
    
*   Cyber Threat Intelligence
    
*   Indicators of Compromise
    

**Automation**

*   Shuffle SOAR
    
*   Webhooks
    
*   Automated Email Notifications
    
*   Wazuh Active Response
    

**Laboratory**

*   Kali Linux
    
*   Virtual Machines
    
*   Controlled Security Testing Environment
    

👨‍💻 My Contribution
---------------------

As a member of the project team, my primary contribution focused on:

### XDR Detection & Automated Response

*   Configured and validated XDR detection scenarios
    
*   Worked with Wazuh detection rules
    
*   Investigated security events and alerts
    
*   Configured response actions
    
*   Validated detection and response results
    
*   Documented technical evidence and findings
    

### Shuffle SOAR Automation

*   Integrated Wazuh alerts with Shuffle
    
*   Configured the webhook-based workflow
    
*   Designed the automated notification process
    
*   Tested SSH brute-force detection
    
*   Verified alert processing and email notification
    

My assigned project workload covered **XDR Detection & Automated Response and Shuffle SOAR Automation**.

📈 Project Results
------------------

The project successfully demonstrated a functional SOC environment centered around Wazuh, including:

*   Centralized SIEM monitoring
    
*   Windows and Linux security monitoring
    
*   Snort IDS integration
    
*   XDR detection and automated response
    
*   Threat intelligence enrichment
    
*   VirusTotal, AbuseIPDB, and AlienVault OTX integration
    
*   Shuffle SOAR automation
    
*   Automated security notifications
    
*   Security event investigation and validation
    

📁 Project Structure
--------------------

```text
SOC-Wazuh-SIEM/
│
├── README.md
│
└── SOC Project Report.docx
```
🎓 Learning Outcomes
--------------------

Through this project, I gained practical experience in:

*   Building a SOC monitoring environment
    
*   Deploying and configuring a SIEM
    
*   Investigating security alerts
    
*   Analyzing Windows and Linux security logs
    
*   Creating and validating detection rules
    
*   Applying threat intelligence to investigations
    
*   Implementing automated security responses
    
*   Integrating SIEM with SOAR
    
*   Documenting security incidents and technical evidence
    

👤 Author
---------

**Abdulrahman Altairey**Cybersecurity Student**Bahrain Polytechnic**

> This project was conducted in a **controlled virtual laboratory environment** for educational and cybersecurity learning purposes.
