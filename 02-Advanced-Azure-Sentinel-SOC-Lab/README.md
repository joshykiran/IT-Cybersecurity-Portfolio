# 📘 Project 02 — Advanced Azure Sentinel SOC Lab 

---

## Project Overview

This project documents my hands-on experience using **Microsoft Sentinel** to simulate real SOC workflows across detection, incident investigation, enrichment, threat hunting, watchlists, and threat intelligence.

The lab was designed to reflect how SOC analysts work in production environments:

- Ingesting security signals from multiple sources  
- Creating and tuning detection rules  
- Investigating incidents using entities, logs, and workbooks  
- Preserving investigation findings using hunting + bookmarks  
- Reducing alert noise using watchlists (allowlisting)  
- Managing IOC lifecycle using Threat Intelligence  


---

## Key Outcomes

By completing this lab, I was able to:

- Deploy a Sentinel training environment with realistic pre-ingested security data  
- Enable and validate key Sentinel data connectors (Azure Activity, Defender products, Threat Intelligence)  
- Create analytics rules (template-based + custom scheduled query detection)  
- Perform incident triage: assign ownership, change status, investigate evidence, and close with classification  
- Enrich incidents using playbooks (Geo-IP tagging) and investigation workbooks  
- Hunt for additional threats and promote findings into incidents using bookmarks  
- Create a watchlist of penetration test IPs and tune analytics rules to reduce false positives  
- Explore and manage Threat Intelligence indicators and enhance TI visualization using workbooks  

---

## Technologies Used

- **SIEM / SOAR:** Microsoft Sentinel  
- **Query Language:** KQL (Kusto Query Language)  
- **Threat Intelligence:** Microsoft Defender Threat Intelligence (MDTI)  
- **Automation:** Playbooks + Automation Rules  
- **SOC Investigation Tools:** Incidents, Entities, Workbooks, Hunting, Bookmarks  
- **Azure Platform:** Azure Portal + Log Analytics Workspace  

---


### ✅ Module 1 — Training Lab Deployment + Playbook Authorization
- Deployed the Microsoft Sentinel Training Lab solution into my workspace  
- Authorized the playbook API connection for later enrichment actions  
- Verified that incidents and training data were ingested successfully  

📌 Evidence: `Evidence/Module1/`

---

### ✅ Module 2 — Data Connectors (Ingestion Readiness)
- Installed and configured Azure Activity connector via Azure Policy assignment  
- Connected Microsoft Defender for Cloud alerts to Sentinel  
- Enabled Microsoft Defender Threat Intelligence ingestion  

📌 Evidence: `Evidence/Module2/`

---

### ✅ Module 3 — Analytics Rules & Detection Engineering
- Enabled rule templates (Suspicious Resource Deployment)  
- Created Microsoft incident creation rule (Defender for Cloud: Medium + High)  
- Built a custom scheduled query rule for malicious inbox rule creation  
- Configured entity mapping (Account, Host, IP) + alert grouping  

📌 Evidence: `Evidence/Module3/`

---

### ✅ Module 4 — Incident Investigation, Enrichment & Allowlisting
- Took ownership of incidents and managed lifecycle (New → Active → Closed)  
- Investigated raw events using Alert timeline + Link to Log Analytics  
- Ran a Geo-IP enrichment playbook and applied tagging  
- Used workbooks to validate suspicious IP activity and confirm Red Team behavior  
- Created a time-bound automation rule to reduce investigation noise  

📌 Evidence: `Evidence/Module4/`

---

### ✅ Module 5 — Threat Hunting + Bookmarks → Incident Evidence
- Ran the Solorigate inventory hunting query  
- Bookmarked findings and added them into the incident for investigation continuity  
- Promoted hunting results into an incident as evidence  

📌 Evidence: `Evidence/Module5/`

---

### ✅ Module 6 — Watchlists for Noise Reduction (PenTest IP Allowlisting)
- Created a watchlist from PenTestsIPaddresses.csv  
- Queried watchlist ingestion in Log Analytics  
- Tuned an analytics rule to exclude watchlist IPs from detections  

📌 Evidence: `Evidence/Module6/`

---

### ✅ Module 7 — Threat Intelligence Operations + Workbook Enhancements
- Validated indicator ingestion into the `ThreatIntelIndicators` table  
- Reviewed IOC metadata inside Threat Intelligence menu  
- Added and removed a manual IOC (URL) to understand lifecycle management  
- Reviewed TI-based analytics rule templates and enabled applicable rules  
- Updated the Threat Intelligence workbook by adding a custom visualization  

📌 Evidence: `Evidence/Module7/`

---

## Project Summary

This project demonstrates SOC-ready capability using Microsoft Sentinel — covering ingestion, detection engineering, investigation, enrichment, hunting, allowlisting, and threat intelligence workflows.

It reflects practical skills aligned with:

✅ SOC incident investigation and closure discipline  
✅ KQL querying and detection tuning  
✅ Threat hunting and evidence preservation  
✅ Automation rules and playbook-based enrichment  
✅ Watchlists for false positive reduction  
✅ IOC management and TI visualization  

---
