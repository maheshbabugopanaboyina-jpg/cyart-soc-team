# SOC Training: Practical Guide - Incident Analysis & Response

## 🛡️ Project Overview
This project demonstrates a complete end-to-end Security Operations Center (SOC) workflow. It includes deploying a SIEM, monitoring real-time attacks, performing threat intelligence-led hunting, and preserving forensic evidence.

## 🛠️ Lab Environment
- **SIEM:** Wazuh (Manager, Indexer, and Dashboard)
- **Monitored Endpoint:** Kali Linux 2024.x
- **Platform:** Oracle VM VirtualBox
- **Tools Used:** Nmap, Netstat, SHA256 Hashing, MITRE ATT&CK Framework

---

## 📋 Completed Tasks

### 1. Advanced Log Analysis & Correlation
- **Detection:** Correlated multiple SSH authentication failures from a single source IP (192.168.56.1).
- **Anomaly Detection:** Identified statistical spikes in login attempts using the Wazuh dashboard visualization.
- **Outcome:** Successfully identified a high-severity Brute Force attack (Rule 2502).

### 2. Threat Intelligence Integration (MITRE ATT&CK)
- **Mapping:** Integrated MITRE ATT&CK Tactic **T1110 (Credential Access)** to validate the brute force attempt.
- **Proactive Hunting:** Conducted a manual threat hunt for **T1078 (Valid Accounts)** by filtering for successful logins during non-standard hours.

### 3. Incident Escalation & SITREP
- **Documentation:** Drafted a professional Situation Report (SITREP) for the detected brute force incident.
- **Workflow:** Simulated the escalation process from Tier 1 (Triage) to Tier 2 (Incident Response) for deep-packet forensic analysis.

### 4. Alert Triage
- **Priority Management:** Triaged over 100 medium-to-high severity alerts.
- **Documentation:** Logged incident ID 004 in a structured triage table, including source/destination details and priority status.

### 5. Evidence Preservation (Forensics)
- **Data Collection:** Captured volatile network connection data (`netstat`).
- **Integrity:** Generated a **SHA256 Hash** for the log file to ensure forensic integrity and chain of custody.

### 6. Capstone Project: Full SOC Workflow Simulation
- **The Attack:** Performed an aggressive reconnaissance scan using Nmap.
- **The Detection:** Identified the scan via Wazuh log monitoring (mapped to MITRE **T1595 - Active Scanning**).
- **Executive Briefing:** Authored a 100-word non-technical summary for management and a detailed 200-word forensic report.

---

## 📊 Summary Tables

### Log Correlation Table
| Timestamp | Event ID | Source IP | Destination IP | Notes |
| :--- | :--- | :--- | :--- | :--- |
| 2026-04-16 17:50 | 2502 | 192.168.56.1 | 192.168.56.102 | Brute Force detected |

### Alert Triage Table
| Alert ID | Description | Source IP | Priority | Status |
| :--- | :--- | :--- | :--- | :--- |
| 004 | SSH Auth Failure | 192.168.56.1 | High (10) | Resolved |

### Capstone Detection Table
| Timestamp | Source IP | Alert Description | MITRE Technique |
| :--- | :--- | :--- | :--- |
| 2026-04-16 18:25 | 192.168.56.1 | Nmap Recon/Scan | T1595 (Active Scan) |

---

## 🚀 Future Improvements
- Implement automated IP blocking using Wazuh Active Response.
- Integrate AlienVault OTX or VirusTotal for automated IP reputation checks.
- Build custom dashboards for real-time visualization of scanning activity.

---

