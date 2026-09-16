# SOC Monitoring & Wazuh SIEM Project

## Overview

A practical Security Operations Center (SOC) project focused on deploying and configuring Wazuh as a centralized SIEM platform.

The project demonstrates security monitoring, threat detection, threat intelligence integration, automated response, and SOAR automation in a controlled virtual lab environment.

## Project Objectives

- Design and implement a functional SOC environment.
- Deploy Wazuh as a centralized SIEM platform.
- Collect and analyze security events from Windows and Linux systems.
- Detect simulated cyber threats and investigate security alerts.
- Integrate external threat intelligence sources.
- Automate security notifications and response actions.

## SOC Environment

The environment included:

- Wazuh SIEM
- Windows Server 2022
- Bodhi Linux
- Snort IDS
- Kali Linux
- Shuffle SOAR

Wazuh was used to centralize logs, generate alerts, and support security investigation and response. :contentReference[oaicite:1]{index=1}

## Threat Detection & Response

The project simulated multiple attacks and investigated their detection through Wazuh, including:

- SMB brute-force attacks
- Malware detection using the EICAR test file
- Suspicious PowerShell activity
- SSH brute-force attacks

Detection rules, logs, and response actions were validated through the Wazuh dashboard and system logs. :contentReference[oaicite:2]{index=2}

## Threat Intelligence

Integrated threat intelligence sources:

- VirusTotal
- AbuseIPDB
- AlienVault OTX

These sources were used to enrich Wazuh alerts with additional information about malicious IP addresses, domains, and file hashes. :contentReference[oaicite:3]{index=3}

## SOAR Automation

Wazuh was integrated with Shuffle to automate alert notifications.

Example workflow:

`Wazuh Alert → Shuffle Webhook → Alert Processing → Email Notification`

The workflow was successfully tested using an SSH brute-force detection scenario. :contentReference[oaicite:4]{index=4}

## Technologies & Tools

- Wazuh SIEM
- Shuffle SOAR
- Snort IDS
- Kali Linux
- Windows Server 2022
- Bodhi Linux
- VirusTotal
- AbuseIPDB
- AlienVault OTX
- Virtual Machines
- Threat Hunting
- Log Analysis
- Incident Response

## Key Skills Demonstrated

- SOC Operations
- SIEM Deployment & Monitoring
- Security Alert Investigation
- Threat Detection
- Threat Intelligence
- Threat Hunting
- Log Analysis
- Automated Response
- SOAR Automation
- Incident Investigation

## Project Documentation

The complete project report is available in this repository.

## Author

**Abdulrahman Altairey**

Cybersecurity Student  
Bahrain Polytechnic
