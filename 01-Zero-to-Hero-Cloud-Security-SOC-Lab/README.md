# Project 01 — Cloud-Centric Security Lab with SOC Integration

## Project Overview
This project documents my hands-on experience designing, building, securing, monitoring, and automating a **cloud-centric enterprise environment** using Microsoft security technologies and Infrastructure as Code (IaC).

The lab was intentionally designed to mirror how **real organizations operate a Security Operations Center (SOC)**, with a strong focus on:
- Identity-first security
- Endpoint and device protection
- Centralized logging and visibility
- Threat detection and investigation
- Automated incident response

Rather than listing configurations alone, this project emphasizes:
- **Why** each security control exists  
- **How** Microsoft security services integrate end-to-end  
- **How** attacks are detected, enriched, visualized, and automatically contained  

This approach reflects structured learning, deliberate design decisions, and operational thinking aligned with **cloud security and SOC roles**.

---

## Key Outcomes
- Deployed Microsoft Sentinel and Log Analytics using **Terraform (Infrastructure as Code)**
- Centralized identity, endpoint, email, and cloud telemetry
- Detected real-world RDP brute-force attacks (Event ID **4625**)
- Enriched security logs with **GeoIP intelligence** and visualized attack origins
- Implemented automated containment using **SOAR (Logic Apps + Automation Runbooks)**

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

## Lab Coverage Checklist
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
**Overview**  
Established a secure DNS foundation to support identity, email, and Zero Trust services.

**What I Did**
- Purchased a custom domain
- Transferred DNS management to Cloudflare
- Verified nameserver propagation

**What I Learned**
- How DNS underpins cloud identity and security
- Why Cloudflare is commonly used in Zero Trust designs

**Skills Demonstrated**
- DNS configuration  
- Third-party service integration  

![Domain and DNS configuration evidence](evidence/Screenshot%20(79).jpg)

---

### Step 2: Microsoft 365 Tenant Setup & Custom Domain Integration
**Overview**  
Created a secure Microsoft 365 tenant and integrated the custom domain.

**What I Did**
- Created a tenant using `onmicrosoft.com`
- Enforced MFA for administrative accounts
- Verified custom domain ownership
- Configured Exchange, SharePoint, Teams, and Intune DNS records

**What I Learned**
- Microsoft 365 tenant and identity architecture
- Importance of securing admin access from day one

**Skills Demonstrated**
- Entra ID administration  
- MFA enforcement  
- Microsoft 365 DNS configuration  

![Cloudflare DNS Records](./evidence/Screenshot-12.jpg)  
![DNS Authorization via Cloudflare](./evidence/Screenshot-13.jpg)

---

### Step 3: Licensing Strategy & Security Feature Enablement
**Overview**  
Enabled enterprise security features through appropriate licensing.

**What I Did**
- Activated required trial licenses:
  - EMS E5  
  - Defender for Endpoint P2  
  - Defender for Office 365 P2  
  - Microsoft 365 Business Premium  

**What I Learned**
- Licensing decisions directly impact security capabilities
- Security requirements should drive license selection

**Skills Demonstrated**
- License planning  
- Security feature enablement  

![License verification](./evidence/Screenshot%20(24)%20-%20Copy.png)

---

### Step 4: Dynamic Groups, Auto-Licensing & Break-Glass Admin
**Overview**  
Automated identity management and implemented emergency access controls.

**What I Did**
- Created dynamic user and device groups
- Automated license assignment
- Configured a break-glass Global Admin excluded from Conditional Access

**What I Learned**
- Automation improves consistency and scalability
- Emergency access is a critical security best practice

**Skills Demonstrated**
- Identity automation  
- Group-based access control  

![Dynamic group configuration](./evidence/Screenshot%20(81)%20-%20Copy.jpg)

---

### Step 5: Intune Enrollment & Windows Autopilot
**Overview**  
Secured endpoints from first boot using Intune and Autopilot.

**What I Did**
- Enabled automatic Intune enrollment
- Created Windows Autopilot deployment profiles
- Validated compliance and policy application

**What I Learned**
- Device security begins at enrollment
- Licensing impacts endpoint workflows

**Skills Demonstrated**
- Endpoint provisioning  
- Windows Autopilot  

![Autopilot confirmation](./evidence/Screenshot%20(56)%20-%20Copy.jpg)

---

### Step 6: CIS Security Baselines & Endpoint Hardening
**Overview**  
Hardened endpoints using CIS-aligned security baselines.

**What I Did**
- Deployed antivirus, firewall, encryption, ASR, and compliance policies

**What I Learned**
- Baselines reduce configuration drift
- Differences between user-based and device-based enforcement

**Skills Demonstrated**
- Endpoint hardening  
- Policy management  

![Security baseline deployment](./evidence/Screenshot%20(82)%20-%20Copy.jpg)

---

### Step 7: Defender for Endpoint & XDR Integration
**Overview**  
Enabled endpoint detection and response and validated XDR telemetry integration.

**What I Did**
- Integrated Defender for Endpoint with Intune
- Enabled EDR, tamper protection, and live response
- Verified protection status across devices

**What I Learned**
- How endpoint telemetry supports XDR investigations
- How Intune and Defender work together for enforcement and visibility

**Skills Demonstrated**
- Endpoint security  
- Security tool integration  

![Defender integration](./evidence/Screenshot%20(36)%20-%20Copy.jpg)

---

### Step 8: Mobile Security — Android Enterprise (BYOD)
**Overview**  
Implemented BYOD controls using Android Enterprise and app protection policies.

**What I Did**
- Configured Android Enterprise and Managed Google Play
- Created app protection and compliance policies
- Enforced Conditional Access for mobile users
- Tested onboarding using Company Portal

**What I Learned**
- BYOD risks and mitigation using app-level controls
- Differences between device management and app protection

**Skills Demonstrated**
- Mobile device management  
- App protection policies  

<p align="center">
  <img src="evidence/WhatsApp%20Image%202025-12-18%20at%205.04.38%20PM.jpeg" width="280">
</p>
<p align="center"><em>Android Work Profile separating personal and corporate data</em></p>

---

## Project Summary
This project demonstrates my ability to **design, secure, monitor, detect, enrich, visualize, and automate** security operations in a modern cloud environment.

It highlights:
- Identity-first security architecture
- Endpoint, email, and SaaS protection
- Centralized logging and SIEM operations
- Threat detection with contextual enrichment
- Automated SOAR-driven incident response

---

## Why This Project Matters
This lab reflects my readiness for **SOC Analyst**, **Cloud Security**, and **Junior Security Engineer** roles.

It demonstrates:
- Practical, hands-on execution  
- Security reasoning and design thinking  
- Clear documentation and communication  
- An operational mindset aligned with real-world security teams  
