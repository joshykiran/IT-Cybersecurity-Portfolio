# 📘 Project 02 — Advanced Microsoft Sentinel SOC Lab

---

## Project Overview

This project documents my end-to-end, hands-on experience using **Microsoft Sentinel** to simulate real-world SOC operations.  
Across seven modules, I worked through the complete SOC workflow lifecycle — from onboarding data sources and building detections, to investigating incidents, enriching alerts, hunting threats, tuning noise, and managing threat intelligence.

The lab environment is designed to reflect how SOC analysts operate in production:

- Ingesting security telemetry from multiple Microsoft and Azure sources  
- Designing and tuning analytics rules to generate high-fidelity alerts  
- Investigating incidents through entities, timelines, and log pivots  
- Enriching incidents using workbooks and automation (playbooks + rules)  
- Preserving investigation outcomes via hunting queries and bookmarks  
- Reducing false positives using watchlists and allowlisting techniques  
- Managing IOC lifecycle and leveraging Threat Intelligence for detection and investigation  

---

## Key Outcomes

By completing this project, I was able to:

- Deploy a fully functional Sentinel training workspace with realistic pre-ingested data  
- Configure and validate multiple data connectors including Azure Activity, Defender products, and Threat Intelligence  
- Enable built-in analytics rules and create custom scheduled query detections using KQL  
- Perform incident triage and full lifecycle management (assign → investigate → close with classification)  
- Enrich investigations using playbooks (Geo-IP tagging) and investigation workbooks  
- Perform proactive threat hunting and promote findings into incidents using bookmarks  
- Create and operationalize watchlists (allowlisting + correlation) to reduce alert noise  
- Explore and manage IOC metadata and enhance Threat Intelligence visibility using workbooks  

---

## Technologies Used

- **SIEM / SOAR:** Microsoft Sentinel  
- **Query Language:** KQL (Kusto Query Language)  
- **Threat Intelligence:** Microsoft Defender Threat Intelligence (MDTI)  
- **Automation:** Playbooks + Automation Rules  
- **SOC Capabilities:** Incidents, Entities, Workbooks, Hunting, Bookmarks, Watchlists  
- **Platform:** Azure Portal + Log Analytics Workspace  

---


---


### ✅ Module 1 — Training Lab Deployment + Playbook Authorization
- Deployed the Microsoft Sentinel Training Lab solution into my workspace  
- Authorized the playbook API connection for later enrichment actions  
- Verified that incidents and training data were ingested successfully  



![Training Lab Deployment](Evidence/Screenshot%20(346).jpg)
![Deployment Completed](Evidence/Screenshot%20(352).jpg)
![Playbook API Connection Authorized](Evidence/Screenshot%20(355).jpg)



---

### ✅ Module 2 — Data Connectors (Ingestion Readiness)
- Installed and configured Azure Activity connector via Azure Policy assignment  
- Connected Microsoft Defender for Cloud alerts to Sentinel  
- Enabled Microsoft Defender Threat Intelligence ingestion  




![Defender for Cloud Connected](Evidence/Screenshot%20(564).png)
![Defender Threat Intelligence Ingestion Enabled](Evidence/Screenshot%20(565).png)
 


---

### ✅ Module 3 — Analytics Rules & Detection Engineering
- Reviewed Analytics **Rule Templates** and filtered by **Azure Activity** to evaluate available detection content  
- Enabled the template rule **Suspicious Resource Deployment** (Azure Activity) with default parameters  
- Created a **Microsoft Incident Creation Rule** for **Defender for Cloud**, filtering only **Medium + High** severity alerts to reduce alert fatigue  
- Reviewed the built-in **Fusion (Multistage Attack Detection)** rule and its connected data sources (enabled by default)  
- Built a custom **Scheduled Query Analytics Rule** to detect **malicious inbox rule creation** using `OfficeActivity_CL` logs  
- Validated log coverage by confirming **New-InboxRule** events were ingested (`OfficeActivity_CL | distinct Operation_s`)  
- Configured detection enhancements: **Entity mapping (Account, Host, IP)**, **custom alert title formatting**, and **alert grouping into incidents (Account-based)**  
- Verified results by reviewing a generated incident and pivoting through the **Entities** tab for investigation context  



![Analytics Rule Template Enabled](Evidence/Screenshot%20(384).png)
![Custom Analytics Rule Logic (KQL)](Evidence/Screenshot%20(386).png)



---

### ✅ Module 4 — Incident Investigation, Enrichment & Allowlisting
- Took ownership of incidents and managed lifecycle (New → Active → Closed)  
- Investigated alert evidence using the incident timeline and **Link to Log Analytics** for raw event review  
- Executed a Geo-IP enrichment playbook and verified automated incident tagging (e.g., location-based tags)  
- Used **Security Efficiency** and **Investigation Insights** workbooks to pivot on suspicious IP activity and confirm Red Team behavior  
- Created a time-bound automation rule to reduce alert fatigue (temporary allowlisting / auto-close workflow)  
- Triaged a **Solorigate Network Beacon** incident by validating IOC context, pivoting through entities (host/IP/DNS), hunting for additional impacted hosts, bookmarking findings, and documenting actions for incident handover  



![Incident Ownership & Status](Evidence/Screenshot%20(864).png)
![Geo-IP Enrichment Playbook Result](Evidence/Screenshot%20(870).png)
![Investigation Workbook Validation](Evidence/Screenshot%20(907).png)



---

### ✅ Module 5 — Proactive Threat Hunting + Watchlist Correlation + Bookmarks
- Performed MITRE technique-based hunting by filtering queries for **T1098 (Account Manipulation)**
- Ran selected hunting queries in batch and reviewed results for suspicious OAuth credential activity
- Created a **HighRiskApps watchlist** (CSV import) to support risk-based validation of hunting results
- Validated watchlist ingestion using `_GetWatchlist()` and schema checks in Log Analytics
- Correlated hunting results with watchlist data using a **KQL join** to identify **high-risk OAuth applications**
- Bookmarked suspicious results with **entity mapping (Account + IP)** and applied investigation tags
- Verified bookmarks in Sentinel and preserved findings for future investigation / incident escalation



![Solorigate Hunting Query Results](Evidence/Screenshot%20(918).jpg)
![Bookmark Added as Incident Evidence](Evidence/Screenshot%20(921).png)
![Bookmark Added as Incident Evidence](Evidence/Screenshot%20(934).jpg)
 


---

### ✅ Module 6 — Watchlists for Noise Reduction (PenTest IP Allowlisting)
- Created a **PenTestsIPaddresses** watchlist by importing `PenTestsIPaddresses.csv` (SearchKey: `IPAddress`)  
- Verified watchlist ingestion in **Log Analytics** using `_GetWatchlist('PenTestIPaddresses')`  
- Installed the **“High count of connections by client IP on many ports”** analytic rule from **Content hub**  
- Tuned the scheduled analytics rule query to **exclude PenTest IPs** using watchlist correlation (`cIP !in (PenTestIPaddresses)`) to reduce false positives / investigation noise  
- Saved and enabled the modified scheduled analytic rule after successful validation  


![Watchlist Created (PenTest IPs)](Evidence/Screenshot%20(945).png)
![Watchlist Items Loaded](Evidence/Screenshot%20(944).png)
![Analytics Rule Tuned to Exclude Watchlist](Evidence/Screenshot%20(947).png)
  


---

### ✅ Module 7 — Threat Intelligence (TI) Integration & Workflow
- Confirmed **Microsoft Defender Threat Intelligence (MDTI)** data connector status and verified ongoing IOC ingestion  
- Explored the **Threat Intelligence** blade to review IOC metadata (type, source, confidence, tags, validity)  
- Created a **manual IOC (URL: `http://phishing.com`)**, tagged it (Incident reference), verified it was written to Log Analytics, and removed it to understand IOC lifecycle management  
- Reviewed **Threat Intelligence analytics rule templates** and enabled applicable correlation rules for ingested TI sources  
- Opened and customized the **Threat Intelligence workbook**, validating TI table availability and adding a custom visualization for better IOC insights  



![ThreatIntelIndicators Table Validated](Evidence/Screenshot%20(959).jpg)
![Manual IOC Added (New TI Object)](Evidence/Screenshot%20(951).png)
![Threat Intelligence Workbook Visualization](Evidence/Screenshot%20(963).jpg)

---

## Project Summary

This project demonstrates SOC-ready capability using **Microsoft Sentinel**, covering the full operational cycle: ingestion, detection engineering, incident investigation, enrichment, threat hunting, noise reduction, and threat intelligence management.

Through this lab, I gained practical exposure to workflows that closely mirror real production SOC environments, including:

✅ Connector onboarding and validation across Azure + Defender data sources  
✅ Analytics rule enablement and custom detection development using KQL  
✅ Structured incident triage, investigation, and closure discipline  
✅ Automated enrichment using playbooks and workbook-driven investigation  
✅ Threat hunting, entity mapping, and evidence preservation using bookmarks  
✅ Watchlist-based allowlisting and rule tuning to reduce false positives  
✅ IOC lifecycle management and Threat Intelligence visualization for improved detection context  

Overall, this lab strengthened my ability to operate within Microsoft Sentinel as a SOC Analyst — combining technical investigation skills with practical detection tuning and operational workflow management.

---
