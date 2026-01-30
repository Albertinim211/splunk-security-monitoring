# 🛡️ Cyber-Sentinel: Splunk SIEM Monitoring Lab
**Enterprise-grade Log Aggregation, Incident Detection, and Security Visualization.**

## 📌 Project Overview
The **Cyber-Sentinel** project is a comprehensive SIEM (Security Information and Event Management) implementation. It demonstrates the ability to ingest raw logs from distributed cloud assets, apply complex analytical logic via **SPL (Search Processing Language)**, and provide actionable security intelligence through real-time dashboards.

This lab monitors the infrastructure built in my **[AWS-Cloud-Infrastructure]** project, closing the loop between System Administration and Security Operations.

---

## 🏗️ Architecture & Data Pipeline
The project follows a standard **Tiered SIEM Architecture**:

1.  **Collection Layer:** Splunk Universal Forwarders (UF) installed on Linux nodes.
2.  **Indexing Layer:** Centralized Splunk instance parsing `syslog`, `auth.log`, and custom audit logs.
3.  **Search Layer:** Custom SPL queries designed to identify "Indicators of Compromise" (IoCs).
4.  **Visualization Layer:** High-level executive dashboards for rapid incident response.



---

## 📂 Repository Contents

| Directory | Content | Purpose |
| :--- | :--- | :--- |
| `queries/` | `security_alerts.spl` | Production-ready detection logic for brute force and privilege escalation. |
| `dashboards/` | `security_overview.json` | Exportable Dashboard Studio configuration for real-time monitoring. |
| `docs/` | `setup_guide.md` | Documentation on configuring Universal Forwarders and inputs. |

---

## 🔍 Key Security Use Cases
This SIEM environment is configured to detect and alert on the following scenarios:

* **Authentication Security:** Detection of SSH Brute Force attacks (MITRE T1110).
* **Access Control:** Monitoring for unauthorized `sudo` attempts and privilege escalation (MITRE T1548).
* **Infrastructure Health:** Real-time tracking of disk exhaustion, CPU spikes, and service crashes.
* **Compliance:** Auditing file system changes and user onboarding/offboarding events.



---

## 🚀 Deployment Summary
1.  **Ingestion:** Configured `inputs.conf` on remote Linux hosts to monitor `/var/log/*.log`.
2.  **Field Extraction:** Utilized Regex (Rex) and Splunk's native CIM (Common Information Model) to map fields like `src_ip` and `dest_user`.
3.  **Visualization:** Imported the `security_overview.json` template into **Splunk Dashboard Studio**.
4.  **Alerting:** Configured email/webhook triggers for "Critical" severity events detected by the SPL library.

---

## 🛠️ Skills Demonstrated
* **SIEM Administration:** Managing the full log lifecycle from ingestion to visualization.
* **Detection Engineering:** Writing high-fidelity SPL queries to reduce "Alert Fatigue."
* **Incident Response:** Identifying and investigating suspicious patterns in raw log data.
* **Linux Auditing:** Deep understanding of Linux logging facilities (`rsyslog`, `systemd-journald`).
* 
