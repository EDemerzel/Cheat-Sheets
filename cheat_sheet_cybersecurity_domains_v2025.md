# Cyber‑Security Domains (v2025)

## Legend

- H2 = Top‑level domain
- H3 w/grey bar = Primary sub‑area
- UL = Detailed activity / control / concept

## Security Architecture & Engineering

> ### Data Protection & Hardening

- Data Leakage Prevention (DLP) - Network Security - Patch / Vulnerability Management
- Baseline Configuration - Secure System Build (CIS, DISA STIG)
- MFA & SSO - Federated Identity - Zero‑Trust Principles

> ### Cryptography & Key Management

- Encryption Standards (TLS 1.3, AES‑GCM, ChaCha20‑Poly1305)
- Certificate / PKI Lifecycle Management - HSM / KMS / Cloud HSM
- Vaulting, Secret Rotation, BYOK / HYOK

> ### Cloud & Container Security

- Cloud Security Posture Management (CSPM) - Container Runtime Hardening
- Image Scanning, Build‑time Signing, SBOMs

> ### Access Control & IAM

- Role‑, Attribute‑, and Policy‑Based Access Control (RBAC / ABAC / PBAC)
- Privileged Access Management (PAM)
- Identity Governance & Administration (IGA)

> ### Endpoint & Edge Hygiene

- EDR / XDR Agents - Mobile Threat Defense - Secure Boot / TPM 2.0

> ### Security Engineering

- Threat Modeling - Security Design Reviews - Secure SDLC Alignment

## Application Security (Shift‑Left)

> ### Secure SDLC Integration

- CI/CD Hooks - Code Review Gates - “Shift‑Left” Testing

> ### Automated Scanning

- **SAST** (static) - **DAST** (dynamic) - **SCA / OSS Scan**
- Source‑Code Scan for secrets - Data‑Flow / Architectural Diagram review

> ### API Security

- OWASP Top 10 (API) mitigation - Schema Validation (OpenAPI, JSON‑Schema)
- Abuse & Business‑Logic Protection

> ### Security QA / UX

- Misuse/abuse test cases - Secure defaults - User‑centric security prompts

## Risk Assessment & Testing

> ### Technical Testing

- Vulnerability Scans - Application Pen‑Tests - Red Team / Purple Team
- Penetration Tests (network & systems) - Social Engineering / Phishing
- Exploit Development / Proof‑of‑Concept (PoC) when warranted

> ### Third‑Party & Supply‑Chain Risk

- 3️⃣ Third‑Party & 4️⃣ Fourth‑Party Assessments - SBOM Review
- Asset Inventory & Dependency Mapping

> ### Risk Monitoring & Scoring

- Continuous Risk‑Score Services - Attack Surface Management (ASM)

> ### Bug Bounty & Disclosure

- Coordinated Vulnerability Disclosure (CVD) - Public / Private Bounty programs

## Governance, Compliance & Enforcement

> ### Policy Framework

- Policy / Standard / Procedure / Guideline hierarchy
- Company‑specific written policies & secure coding standards

> ### Legal & Regulatory

- GDPR, CCPA, GLBA, HIPAA, PCI‑DSS, NYDFS 23 NYCRR 500, Regional Data‑Residency Acts
- Central‑Government & Sector‑Specific Laws (e.g., NERC CIP, FedRAMP)

> ### Executive Oversight

- Board & C‑Suite Risk Appetite - KPI / KRI Scorecards - Risk‑Informed Decision‑Making

> ### Reporting & Evidence

- Audit Trails - Metrics Dashboards - Compliance (SOC 1/2, ISO 27001)

## Enterprise Risk Management (ERM)

> ### Risk Treatment Lifecycle

- Identification → Analysis → Evaluation → Treatment (avoid, mitigate, transfer, accept)
- **Risk Acceptance Statements & Exception Handling**

> ### Lines of Defense Model

- 1️⃣ Process Owners 2️⃣ Risk Management Group 3️⃣ Internal/External Audit

> ### Cyber Insurance (Transfer)

- Policy Selection - Data to Insurer (loss history, controls) - Coverage Gaps

## Security Operations (SOC / Blue Team)

> ### Operational Components

- Security Operations Center (24×7 SOC) - SIEM - SOAR
- Case Management & Ticketing - KPI: MTTR, MTTD

> ### Core Capabilities

- Active Defense / Threat Hunting - Detection Engineering
- Incident Response: *Detect → Contain → Eradicate → Recover → Lessons Learned*
- Digital Forensics & Malware Analysis - Breach Notification

> ### Vulnerability Management

- Discovery → Triage (CVSSv4 / EPSS) → Patch / Compensating Controls

## Threat Intelligence

> ### Collection Types

- **External** (commercial feeds, ISACs, OSINT)
- **Internal** (honeypots, SOC telemetry)

> ### Contextualization & Sharing

- Indicator of Compromise (IOC) / Indicator of Attack (IOA)
- Intelligence Sharing Formats: STIX 2.x, TAXII 2, MISP

> ### Operational Usage

- Detection‑rule enrichment - Campaign Tracking - Threat Modeling inputs

## User Education & Awareness

> ### Awareness (Reinforcement)

- Phishing Simulations - Quarterly Micro‑Learning Modules

> ### Skills Training

- Instructor‑led Live Training - Self‑paced Labs (cloud sandboxes)

> ### Hands‑On Exercises

- Capture‑the‑Flag (CTF) - Cyber Table‑Top Exercises

> ### Metrics

- Phish Click‑Rate, Pre/Post‑Test Scores, Training Completion %

## Physical & Cyber‑Physical Security

> ### ICS / SCADA

- Network Segmentation - Protocol Gateways - Secure Remote Access

> ### IoT Security

- Device Identity & Firmware Signing - OTA Update Integrity

> ### Facility / Environmental Controls

- Access Badges, Surveillance (CCTV), Redundant HVAC & Power

## Career Development (People & Community)

- Traditional & Online Education (B.S., M.S., MOOCs)
- Professional Certification (CISSP, CEH, OSCP, CCSP, CISM…)
- Mentoring, Volunteering, Conferences, Meetups, Personal Branding

## Frameworks & Standards (Cross‑Cutting)

- NIST Cybersecurity Framework (CSF 2.0)
- ISO/IEC 27001 / 27017 / 27018 (Cloud PII)
- CIS Top 18 Critical Security Controls & Benchmarks
- OWASP Top 10 (Web & API)
- MITRE ATT\&CK, D3FEND, CWE
