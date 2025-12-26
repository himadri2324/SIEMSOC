# SIEMSOC: Real-Time Threat Detection and Investigation Using Elastic SIEM
**SIEMSOC** is a hands-on Security Operations Center project using Elastic SIEM to collect, correlate, and investigate Windows security events, enabling real-time threat detection and analyst-driven incident analysis.

---

## 🎬 Demonstration
<p align="center">
  <a href="" target="_blank">
    <img src="https://img.icons8.com/color/96/video.png" alt="Watch Demo" />
    <br>
    <strong>Click to watch the demonstration video</strong>
  </a>
</p>

---

## 📘 Project Overview
**SIEMSOC** is a practical Security Operations Center project demonstrating real-time threat detection and investigation using Elastic SIEM. It ingests Windows Event Logs through Winlogbeat, correlates security events in Elasticsearch, and enables SOC analysts to investigate authentication-based attacks using Kibana dashboards and alerts.

---

## 🎯 **Key Objectives:**
* **Centralized Log Collection:** Collect Windows security events centrally using Winlogbeat for unified analysis.
* **Real-Time Threat Detection:** Detect suspicious authentication activity through SIEM correlation rules and alerts.
* **Event Correlation and Analysis:** Correlate multiple security events to identify attack patterns accurately.
* **SOC Investigation Workflow:** Enable analysts to investigate alerts using timelines, fields, and event context.
* **Security Visibility Improvement:** Enhance visibility into system activity for faster and informed security decisions.

---

## 🖥️ **Virtual Machines (VMware Workstation):**
| VM Name | Operating System | Role | 
| :--- | :--- | :--- |
| **SIEM VM** | Ubuntu 22.04LTS | Hosts Elastic Stack for log ingestion, correlation, and SOC investigation |
| **Windows-Host** | Windows Server | Generates security events and acts as monitored endpoint |

---

## 🔧 **Tools and Roles per Component:**
| Component | Tools/Services | Purpose |
| :--- | :--- | :--- |
| **Log Generation** | Windows Event Logs | Records authentication and security-related system events |
| **Log Collection** | Winlogbeat | Forwards Windows security logs to the SIEM server | 
| **SIEM Processing** | Elasticsearch | Stores, indexes, and correlates ingested security events | 
| **Detection & Alerting** | Elastic SIEM | Applies detection rules to identify suspicious activity | 
| **Visualization & Analysis** | Kibana | Provides dashboards, alerts, and investigation timelines | 
| **SOC Investigation** | Elastic Security UI | Enables analyst-driven alert investigation and event analysis | 

---

## 🖧 **Network Architecture Diagram:**
<p align="center">
<img src=""
  alt="SIEMSOC Network Architecture Diagram" width="750"/>
  </p>

---

## 🏗️ **Architecture Flow Diagram:**
<p align="center">
  <img src="" 
       alt="SIEMSOC Architecture Diagram" width="750"/>
</p>

---

## ⚙️ **Detailed Setup Steps**
1.  **Environment Preparation:**
    * Install VMware Workstation on the host system
    * Create two virtual machines: Ubuntu 22.04 LTS and Windows 10 / Windows Server
    * Allocate adequate resources (CPU, RAM, disk) for stable SIEM performance
    * Configure NAT-based networking to enable secure internal communication between VMs
    * Verify network connectivity between Windows and Ubuntu virtual machines
2.  **Elastic Stack Deployment:**
    * Update the Ubuntu system and install required dependencies
    * Install Elasticsearch on the Ubuntu virtual machine
    * Configure Elasticsearch to listen on the VM’s internal IP address
    * Install Kibana and configure it to connect with Elasticsearch
    * Start Elasticsearch and Kibana services and verify they are running successfully
    * Access the Kibana web interface through a browser
3.  **Elastic SIEM Configuration:**
    * Enable Elastic Security (SIEM) within the Kibana interface
    * Configure index patterns for security event ingestion
    * Verify default detection rules are available and active
    * Ensure the Security dashboard is accessible for SOC monitoring
4.  **Windows Log Collection Setup:**
    *  Install Winlogbeat on the Windows virtual machine
    *  Configure Winlogbeat to collect Windows Security Event Logs
    *  Set Elasticsearch as the output destination in Winlogbeat configuration
    *  Start Winlogbeat service and confirm logs are being forwarded successfully
    *  Validate log ingestion by checking Security events in Kibana
5. **Detection and Investigation Validation:**
    * Generate failed login attempts on the Windows machine
    * Confirm authentication failure events (Event ID 4625) appear in Elasticsearch
    * Verify Elastic SIEM generates alerts for suspicious activity
    * Investigate alerts using Kibana timelines and event details
    * Analyze source IPs, usernames, and event frequency for SOC-style investigation

---

## 🔍 **Detection (SIEM – Elastic Security)**
* **Authentication Failure Monitoring:** Detect repeated failed login attempts using Windows security event logs.
* **Event ID Correlation:** Correlate Event ID 4625 occurrences to identify suspicious authentication behavior.
* **Threshold-Based Alerting:** Trigger alerts when failed login attempts exceed defined frequency thresholds.
* **Source and User Analysis:** Identify suspicious source IP addresses and targeted user accounts.
* **Timeline Pattern Detection:** Analyze event timelines to recognize brute-force or credential abuse patterns.

---

## 🛠️ **Response (SOC Analyst – Manual Investigation)**
* **Alert Validation:** Review SIEM alerts to confirm true positives and eliminate false positives.
* **Authentication Analysis:** Investigate failed login events using Kibana timelines and detailed event metadata.
* **Source & User Review:** Analyze source IP addresses and targeted usernames for suspicious behavior.
* **Attack Pattern Identification:** Identify brute-force or credential abuse patterns through event frequency analysis.
* **Incident Documentation:** Document investigation findings clearly for reporting, auditing, and future reference.
  
---

## 🚀 Future Enhancements
* **Advanced Detection Rules:** Create custom SIEM rules for lateral movement and privilege escalation detection.
* **Brute-Force Correlation:** Correlate authentication failures across multiple hosts for distributed attack detection.
* **Threat Intelligence Integration:** Integrate external threat feeds to enrich alerts with malicious IP context.
* **Automated Alert Enrichment:** Enrich alerts with geolocation, host details, and historical event context.
* **Dashboard Optimization:** Build custom SOC dashboards for faster monitoring and investigation workflows.

---

## 🔚 Conclusion
This project demonstrates practical SOC operations using Elastic SIEM for detecting, investigating, and analyzing Windows authentication threats. It showcases real-world log ingestion, alerting, and analyst-driven investigation workflows essential for entry-level SOC and blue team roles.
