# soc-siem-threat-monitoring



# 🛡️ Enterprise SOC Threat Monitoring & Centralized SIEM Infrastructure

A production-ready Security Operations Center (SOC) logging pipeline and Security Information and Event Management (SIEM) architecture deployed using the open-source Wazuh stack via container orchestration.

---

## 📋 Project Overview
The objective of this project was to transition from individual endpoint defense to a unified security operations model. By deploying a multi-component SIEM cluster, this infrastructure ingests, normalizes, and correlates system event logs to surface hidden threat profiles and track active infrastructure exposures in real-time.

---

## 🛠️ Environment & Tooling
* **Deployment Platform:** Kali Linux Environment
* **Orchestration Core:** Docker & Docker-Compose Layout Engine
* **SIEM Core Stack:** Wazuh Indexer, Manager, and Dashboard (v4.9.2)
* **Testing Scope:** Automated network mapping tracking and endpoint log analysis

---

## 🔍 Phase 1: SIEM Infrastructure Orchestration

The cluster was deployed leveraging isolated microservice structures. To ensure structural stability for heavy Java/Elasticsearch processing, the virtual memory allocation of the underlying Linux environment was optimized before initialization.

### System Optimization & Build Commands:
```bash
# 1. Expand virtual memory map limits to prevent indexer database crashes
sudo sysctl -w vm.max_map_count=262144

# 2. Re-initialize container orchestration structures in background detached mode
sudo docker-compose up -d
```

---

## ⚡ Phase 2: Active Threat Tracking & Log Correlation

Once the cluster nodes reached a healthy operational baseline, host logging streams were piped straight into the core management tier. Within the first 24 hours of live monitoring, the correlation engine successfully ingested background system data and parsed security anomalies:

### Log Ingestion Analytics Breakdown:
* **High/Critical Severity Alerts (Level 12-15+):** 0 (Confirmed clean baseline)
* **Medium Severity Alerts (Level 7-11):** 47 Active Events Detected
* **Low Severity Alerts (Level 0-4):** 150 Active Events Logs Sorted

### Centralized Monitoring Dashboard Proof-of-Concept:
The interface screen below verifies successful connection to the security management cluster, showing live metrics processing and structured log grouping modules:

![Wazuh Security Overview Dashboard](./wazuh_siem_dashboard.png)

---

## 🛡️ Phase 3: Technical Insights & Operations Value

Implementing an enterprise-grade SIEM shifts an organization's defense posture from reactive patching to **real-time defensive engineering**. 

* **Log Aggregation:** Standardizes chaotic multi-platform log structures into an easily searchable, unified schema layout.
* **Incident Containment:** Provides security teams with immediate visual warning indicators regarding credential brute-forcing, file tampering, or unpatched service vulnerabilities.
* **Compliance Posture:** Maps raw events directly against global compliance standards (including PCI-DSS, GDPR, and NIST 800-53) to streamline enterprise compliance audits.
