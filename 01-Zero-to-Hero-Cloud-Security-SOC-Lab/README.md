# Project 01 — Cloud-Centric Security Lab with SOC Integration

## Project Overview
This project documents my hands-on experience designing, building, securing, monitoring, and automating a **cloud-centric enterprise environment** using Microsoft security technologies and Infrastructure as Code.

The lab was intentionally designed to mirror how **real organizations operate a Security Operations Center (SOC)** — focusing on **identity-first security**, **endpoint protection**, **centralized visibility**, **threat detection**, and **automated response**.

Rather than listing configurations alone, this project emphasizes:
- **Why** each security control exists  
- **How** Microsoft security services integrate end-to-end  
- **How** attacks are detected, enriched, visualized, and automatically contained  

This reflects structured learning, deliberate design decisions, and real operational thinking aligned with **cloud security and SOC roles**.

---

## Key Outcomes
- Deployed Microsoft Sentinel and Log Analytics using **Terraform (IaC)**  
- Centralized identity, endpoint, email, and cloud telemetry  
- Detected real-world RDP brute-force attacks (Event ID 4625)  
- Enriched logs with **GeoIP intelligence** and visualized attack origins  
- Automated containment using **SOAR (Logic Apps + Automation Runbooks)**  

---

## Technologies Used
- **Cloud Platform:** Microsoft Azure  
- **Identity & Access Management:** Microsoft Entra ID (Azure AD)  
- **Device Management:** Microsoft Intune (Windows & Android)  
- **Endpoint & Email Security:** Microsoft Defender Suite  
- **SIEM / SOAR:** Microsoft Sentinel  
- **Infrastructure as Code:** Terraform (GitHub + Terraform Cloud)  
- **DNS & Zero Trust Foundation:** Cloudflare  

---

## Lab Checklist
- [x] Custom domain and DNS configuration  
- [x] Secure Microsoft 365 tenant setup  
- [x] Automated licensing and dynamic groups  
- [x] Windows Autopilot onboarding  
- [x] CIS-aligned security baselines  
- [x] Endpoint Detection & Response (EDR/XDR)  
- [x] Mobile security (Android BYOD)  
- [x] Email and SaaS protection  
- [x] Conditional Access (Zero Trust)  
- [x] SIEM, SOAR, and automated incident response  

---

## Implementation Journey

### Step 1: Domain Purchase & DNS Foundation (Cloudflare)
🔍 **Overview**  
Established a secure DNS foundation to support identity, email, and Zero Trust services.

🛠️ **What I Did**
- Purchased a custom domain
- Transferred DNS to Cloudflare
- Verified nameserver propagation

📚 **What I Learned**
- How DNS underpins cloud identity and security
- Why Cloudflare is common in Zero Trust designs

🧠 **Skills Demonstrated**
- DNS configuration
- Third-party integration

![Domain and DNS configuration evidence](evidence/Screenshot%20(79).jpg)

---

### Step 2: Microsoft 365 Tenant Setup & Custom Domain Integration
🔍 **Overview**  
Created a secure Microsoft 365 tenant and integrated the custom domain.

🛠️ **What I Did**
- Created tenant with `onmicrosoft.com`
- Enforced MFA for administrators
- Verified custom domain ownership
- Configured Exchange, SharePoint, Teams, and Intune DNS records

📚 **What I Learned**
- Microsoft 365 identity and tenant architecture
- Importance of securing admin access from day one

🧠 **Skills Demonstrated**
- Entra ID administration
- MFA enforcement
- Microsoft 365 DNS configuration

![Cloudflare DNS Records](./evidence/Screenshot-12.jpg)
![DNS Authorization via Cloudflare](./evidence/Screenshot-13.jpg)

---

### Step 3: Licensing Strategy & Security Feature Enablement
🔍 **Overview**  
Enabled enterprise security capabilities through licensing.

🛠️ **What I Did**
- Activated required trial licenses:
  - EMS E5
  - Defender for Endpoint P2
  - Defender for Office 365 P2
  - Microsoft 365 Business Premium

📚 **What I Learned**
- Licensing directly controls security posture
- Security requirements should drive license selection

🧠 **Skills Demonstrated**
- License planning
- Security enablement

![Domain and DNS verification](./evidence/Screenshot%20(24)%20-%20Copy.png)

---

### Step 4: Dynamic Groups, Auto-Licensing & Break-Glass Admin
🔍 **Overview**  
Automated identity management and ensured emergency access.

🛠️ **What I Did**
- Created dynamic user/device groups
- Automated license assignment
- Created break-glass Global Admin excluded from CA policies

📚 **What I Learned**
- Automation improves consistency and scalability
- Emergency access is a security best practice

🧠 **Skills Demonstrated**
- Identity automation
- Group-based access control

![Domain and DNS configuration confirmation](./evidence/Screenshot%20(81)%20-%20Copy.jpg)

---

### Step 5: Intune Enrollment & Windows Autopilot Configuration
🔍 **Overview**  
Secured endpoints from first boot using Intune and Autopilot.

🛠️ **What I Did**
- Enabled automatic Intune enrollment
- Created Autopilot deployment profile
- Validated compliance and policy application

📚 **What I Learned**
- Device security begins at enrollment
- Licensing impacts endpoint workflows

🧠 **Skills Demonstrated**
- Endpoint provisioning
- Windows Autopilot

![Cloudflare nameserver update confirmation](./evidence/Screenshot%20(56)%20-%20Copy.jpg)
![Cloudflare DNS overview](./evidence/Screenshot92.png)

---

### Step 6: CIS Security Baselines & Endpoint Hardening
🔍 **Overview**  
Hardened endpoints using CIS-aligned baselines.

🛠️ **What I Did**
- Deployed AV, firewall, encryption, ASR, and compliance policies

📚 **What I Learned**
- Baselines reduce configuration drift
- User vs device enforcement differences

🧠 **Skills Demonstrated**
- Endpoint hardening
- Policy management

![Domain DNS propagation status](./evidence/Screenshot%20(82)%20-%20Copy.jpg)

---


### Step 7: Defender for Endpoint & XDR Integration

#### 🔍 Overview
Enabled endpoint detection and response and validated XDR telemetry integration across enrolled devices.

#### 🛠️ What I Did
- Integrated Defender for Endpoint with Intune.
- Enabled EDR, tamper protection, and live response.
- Verified endpoint protection status across enrolled devices.

#### 📚 What I Learned
- How endpoint telemetry supports XDR investigations.
- How Intune and Defender work together for enforcement + visibility.

#### 🧠 Skills Demonstrated
- Endpoint security  
- Security tool integration  

![Domain added to Microsoft 365 tenant](./evidence/Screenshot%20(36)%20-%20Copy.jpg)
![Microsoft 365 domain verification](./evidence/Screenshot%20(69)%20-%20Copy.jpg)

---

### Step 8: Mobile Security — Android Enterprise (BYOD)

#### 🔍 Overview
Implemented BYOD controls using Android Enterprise and app protection to separate corporate and personal data.

#### 🛠️ What I Did
- Configured Android Enterprise and Managed Google Play.
- Created app protection and compliance policies.
- Enforced Conditional Access for mobile users.
- Tested onboarding using Company Portal.

#### 📚 What I Learned
- BYOD risks and how app-level controls reduce data exposure.
- Differences between device management and app protection policies.

#### 🧠 Skills Demonstrated
- Mobile device management  
- App protection policies  

<p align="center">
  <img src="evidence/WhatsApp%20Image%202025-12-18%20at%205.04.38%20PM.jpeg" width="280">
</p>

<p align="center">
  <em>Android Work Profile separating personal and corporate data</em>
</p>

---

### Step 9: Microsoft Defender for Office 365 — Email Threat Protection

#### 🔍 Overview
Hardened email security using Defender for Office 365 policies to reduce phishing, malware, and spam risk.

#### 🛠️ What I Did
- Configured Defender for Office 365.
- Enabled Microsoft-recommended presets.
- Created custom phishing, malware, spam, Safe Links, and Safe Attachments policies.

#### 📚 What I Learned
- Why email remains the most common initial access vector.
- How layered controls reduce both credential theft and malware delivery.

#### 🧠 Skills Demonstrated
- Email security administration  
- Threat policy configuration  

![Screenshot 61](./evidence/Screenshot%20(61)%20-%20Copy.jpg)
![Screenshot 62](./evidence/Screenshot%20(62)%20-%20Copy.jpg)
![Screenshot 67](./evidence/Screenshot%20(67)%20-%20Copy.jpg)
![Screenshot 68](./evidence/Screenshot%20(68)%20-%20Copy.jpg)

---

### Step 10: Defender for Cloud Apps (CASB) & SaaS Security

#### 🔍 Overview
Improved SaaS visibility and reduced shadow IT risk using CASB controls and discovery.

#### 🛠️ What I Did
- Connected Microsoft 365 and Entra ID to Defender for Cloud Apps.
- Enabled Cloud Discovery.
- Reviewed and tagged unsanctioned cloud applications.
- Integrated Defender for Endpoint for access control.

#### 📚 What I Learned
- How CASB provides governance and visibility across cloud apps.
- Why unsanctioned SaaS usage can increase data leakage risk.

#### 🧠 Skills Demonstrated
- CASB  
- SaaS risk assessment  

![Screenshot 50](./evidence/Screenshot%20(50)%20-%20Copy.jpg)
![Screenshot 71](./evidence/Screenshot%20(71)%20-%20Copy.jpg)

---

### Step 11: Conditional Access Enforcement & Zero Trust Alignment

#### 🔍 Overview
Implemented identity-driven access controls using Conditional Access with safe staged rollout.

#### 🛠️ What I Did
- Disabled Microsoft Security Defaults.
- Created Conditional Access policies in Report-only mode.
- Validated policy impact before enforcement.

#### 📚 What I Learned
- How Conditional Access enforces Zero Trust based on risk and device posture.
- Why staged rollout prevents business disruption.

#### 🧠 Skills Demonstrated
- Zero Trust enforcement  
- Identity governance  

![Microsoft Defender security overview](./evidence/S88.png)
![Screenshot 90](./evidence/Screenshot%20(90).png)

---

### Step 12: SIEM Deployment with Infrastructure as Code (Microsoft Sentinel)

#### 🔍 Overview
In this step, I deployed **Microsoft Sentinel** as a cloud-native SIEM using **Terraform (Infrastructure as Code)**.  
I used a DevOps-style workflow (**GitHub + Terraform Cloud**) to keep the deployment repeatable, auditable, and easy to rebuild.

#### 🛠️ What I Did
- Created a Terraform repository and connected it to **Terraform Cloud**.
- Stored Azure authentication values securely using Terraform Cloud variables.
- Deployed via Terraform:
  - Resource Group
  - Log Analytics Workspace
  - Microsoft Sentinel instance
- Verified successful deployment using Terraform run output and Azure Portal.

#### 📚 What I Learned
- How to deploy SIEM infrastructure using IaC
- How Terraform Cloud workflows simulate enterprise deployments
- Sentinel architecture basics (Workspace + SIEM layer)

#### 🧠 Skills Demonstrated
- Terraform (IaC)
- Azure resource provisioning
- SIEM deployment
- GitHub + Terraform Cloud integration

![Screenshot 106](./evidence/Screenshot%20(106)%20-%20Copy.jpg)
![Screenshot 110](./evidence/Screenshot%20(110)%20-%20Copy.jpg)
![Screenshot 113](./evidence/Screenshot%20(113)%20-%20Copy.jpg)
![Screenshot 118](./evidence/Screenshot%20(118)%20-%20Copy.jpg)
![Screenshot 120](./evidence/Screenshot%20(120)%20-%20Copy.jpg)
![Screenshot 121](./evidence/Screenshot%20(121)%20-%20Copy.jpg)

---

### Step 13: Centralized Log Collection & Security Visibility

#### 🔍 Overview
In this step, I configured **centralized security telemetry ingestion** into Microsoft Sentinel by onboarding core Microsoft identity, endpoint, and cloud data sources.  
This created a single place to investigate security activity across the environment.

#### 🛠️ What I Did
- Installed required solutions from the **Microsoft Sentinel Content Hub**.
- Connected and validated key data sources:
  - Microsoft Entra ID
  - Microsoft Defender for Endpoint
  - Microsoft Defender for Office 365
  - Microsoft Defender for Cloud Apps
  - Microsoft Defender XDR
  - Microsoft 365
  - Azure Activity Logs
  - Windows Security Events (via AMA)
- Verified logs were flowing into Log Analytics using **KQL** and Sentinel views.

#### 📚 What I Learned
- How SIEM platforms aggregate logs into a central investigation view
- Common connector requirements (permissions, roles, onboarding steps)
- How to validate ingestion and confirm event availability using KQL

#### 🧠 Skills Demonstrated
- Log ingestion & normalization
- Microsoft Sentinel Content Hub
- KQL (Kusto Query Language)
- Security visibility & monitoring

![Screenshot 124](./evidence/Screenshot%20(124)%20-%20Copy.jpg)
![Screenshot 126](./evidence/Screenshot%20(126)%20-%20Copy.jpg)
![Screenshot 127](./evidence/Screenshot%20(127)%20-%20Copy.jpg)
![Screenshot 128](./evidence/Screenshot%20(128)%20-%20Copy.jpg)
![Screenshot 159](./evidence/Screenshot%20(159)%20-%20Copy.jpg)
![Screenshot 160](./evidence/Screenshot%20(160)%20-%20Copy.jpg)

---

### Step 14: Azure Virtual Machine Deployment using Terraform

#### 🔍 Overview
In this step, I deployed an **Azure Virtual Machine** using **Terraform**.  
This VM was intentionally exposed on **RDP (3389)** for a controlled period so I could generate real attack telemetry and test detection + response workflows safely.

#### 🛠️ What I Did
- Created a separate Terraform repo/workspace for VM deployment.
- Connected the repo to Terraform Cloud and configured variables securely.
- Deployed:
  - Azure Virtual Machine
  - NIC
  - VNet
  - NSG
- Connected the VM to the existing **Log Analytics Workspace** for monitoring.
- Generated test telemetry using intentional failed logons (Event ID **4625**).

#### 📚 What I Learned
- How to deploy compute infrastructure via Terraform Cloud
- How to prepare workloads for security monitoring and detection testing

#### 🧠 Skills Demonstrated
- Terraform
- Azure compute + networking
- Infrastructure as Code

![Screenshot 598](./evidence/Screenshot%20(598)%20-%20Copy.png)

---

### Step 15: Threat Detection, GeoIP Enrichment & Incident Creation

#### 🔍 Overview
In this step, I created detection rules in Microsoft Sentinel, enriched attacker telemetry using **GeoIP**, and visualized real-world brute-force attempts on a world map.

#### 🛠️ What I Did
- Built **Analytics Rules** in Microsoft Sentinel.
- Detected **RDP brute-force attempts** using:
  - Event ID **4625**
  - Threshold-based detection logic within a time window
- Enabled automatic incident creation and validated incident generation.

#### 🧠 GeoIP Log Enrichment
- Uploaded a **GeoIP watchlist** (IP ranges + geographic data) to Sentinel.
- Enriched attacker IPs with:
  - Country, City
  - Latitude/Longitude
- Used enrichment to make investigations faster and more meaningful.

#### 🌍 Attack Visualization
- Built a Sentinel **Workbook** to map attacker origins globally.
- Confirmed real brute-force activity and visualized sources by country/region.

#### 📚 What I Learned
- Detection engineering using KQL + Sentinel analytics rules
- Enrichment improves investigation speed and context
- How dashboards/workbooks support SOC reporting and monitoring

#### 🧠 Skills Demonstrated
- Threat detection engineering
- KQL analytics rules
- GeoIP enrichment
- Sentinel Workbooks
- SOC investigation workflows

![Screenshot 163](./evidence/Screenshot%20(163)%20-%20Copy.jpg)
![Screenshot 227](./evidence/Screenshot%20(227)%20-%20Copy.jpg)
![Screenshot 229](./evidence/Screenshot%20(229)%20-%20Copy.jpg)

![Screenshot 277](./evidence/Screenshot%20(277)%20-%20Copy.jpg)

![Screenshot 311](./evidence/Screenshot%20(311)%20-%20Copy.jpg)

---

### Step 16: SOAR Playbooks & Automated Incident Response

#### 🔍 Overview
In this step, I implemented **SOAR automation** so that Microsoft Sentinel could automatically trigger response actions to contain attacks without manual intervention.

#### 🛠️ What I Did
- Created a **Logic App playbook** triggered by Sentinel incidents.
- Parsed incident payload using **Parse JSON**.
- Triggered an **Azure Automation Runbook** using managed identity.
- Automated response actions:
  - Identify impacted VM
  - Locate associated NSG
  - Block attacker IP on **RDP (3389)** using a deny rule

#### 🔁 Automated Response Flow
1. Sentinel detects suspicious RDP activity  
2. Incident is created automatically  
3. Playbook triggers (Logic App)  
4. Runbook applies NSG deny rule  
5. Threat is contained without manual action  

#### 📚 What I Learned
- How SOAR reduces response time and human workload
- How managed identities enable secure automation
- How network-level controls (NSGs) can be used for containment

#### 🧠 Skills Demonstrated
- SOAR (Microsoft Sentinel)
- Logic Apps
- Azure Automation Runbooks
- NSG-based containment
- Automated incident response

![Screenshot 230](./evidence/Screenshot%20(230)%20-%20Copy.jpg)
![Screenshot 232](./evidence/Screenshot%20(232)%20-%20Copy.jpg)
![Screenshot 233](./evidence/Screenshot%20(233)%20-%20Copy.jpg)
![Screenshot 236](./evidence/Screenshot%20(236)%20-%20Copy.jpg)
![Screenshot 237](./evidence/Screenshot%20(237)%20-%20Copy.jpg)
![Screenshot 260](./evidence/Screenshot%20(260)%20-%20Copy.jpg)
![Screenshot 273](./evidence/Screenshot%20(273)%20-%20Copy.jpg)
![Screenshot 331](./evidence/Screenshot%20(331)%20-%20Copy.jpg)
![Screenshot 2025-12-19 153537](./evidence/Screenshot%202025-12-19%20153537.png)

---

## Project Summary
This project demonstrates my ability to **design, secure, monitor, detect, enrich, visualize, and automate** security operations in a modern cloud environment.

It showcases:
- Identity-first security
- Endpoint and email protection
- Centralized logging and SIEM operations
- Threat detection and GeoIP enrichment
- Automated SOAR-based incident response

---

## Why This Project Matters
This project reflects my readiness for **SOC Analyst, Cloud Security, and Junior Security Engineer roles**.

It demonstrates:
- Practical hands-on execution  
- Security reasoning and design thinking  
- Clear documentation and communication  
- A strong operational mindset aligned with real-world security teams  

