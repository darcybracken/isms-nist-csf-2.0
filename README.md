# Title: ISMS Project - NIST CSF 2.0 



## What This Is

A student-built **Information Security Management System (ISMS)** designed from scratch for a mock financial services organization (FinCorp) aligned to **NIST Cybersecurity Framework 2.0** (September 2025).

This project answers one practical question: *What does it actually take to protect organizational data in a structured, auditable way?*

The result is a complete documentation package that includes governance policies, control mappings, architecture diagrams, and incident response procedures, structured the way a GRC analyst would build it in a real organization. As information security evolves, so should an organization's **ISMS.** This package will continue to grow as new developments emerge. Research and continuous learning should always drive what controls and policies are right for the organization, ensuring the documentation remains current and comparable to industry standards.
## Mock Organization

| Field | Value |
|-------|-------|
| **Organization** | FinCorp (mock) |
| **Industry** | Financial Services |
| **Size** | 200 employees |
| **Regulatory Environment** | SOC 2, GLBA Safeguards Rule |
| **Data Sensitivity** | PII, financial records, internal communications |
| **IT Environment** | Hybrid on-premises + AWS, Microsoft 365 |
| **Risk Appetite** | Low / conservative |


## Architecture Overview

The diagram below shows how data flows through FinCorp's four security zones, highlighting NIST CSF 2.0 controls at each point where they’re enforced.

FinCorp Data Flow Architecture NIST CSF 2.0 Control Overlay

![FinCorp Data Flow Architecture NIST CSF 2.0 Control Overlay](./99_%20Attachment/ISMS_Architecture.png)


## What Was Built

| Artifact                  | Purpose                                                                                                      | NIST Function     |
| ------------------------- | ------------------------------------------------------------------------------------------------------------ | ----------------- |
| Acceptable Use Policy     | Defines acceptable behavior, data handling, and prohibited activities                                        | Govern (GV)       |
| RACI Matrix               | Assigns accountability across 14 security activities and 6 roles                                             | Govern (GV)       |
| NIST CSF Master Crosswalk | Maps every control to NIST subcategories with SOC 2, ISO 27001, and GLBA cross-references                    | All 6 functions   |
| Data Flow Architecture    | Four-zone DFD with NIST control overlay at every boundary and enforcement point                              | Identify, Protect |
| Incident Response Plan    | Six-stage response lifecycle (NIST SP 800-61), severity matrix, evidence chain of custody                    | Respond, Recover  |
| Ransomware Playbook       | Scenario-specific procedures: containment, eradication, recovery, ransom decision framework                  | Respond, Recover  |
| Gap Analysis & Findings   | POA&M style gap tracking across all six NIST functions                                                       | All 6 functions   |
| Policy Review Cadence     | Quarterly review schedule with PDCA improvement cycle                                                        | Govern (GV)       |
| Threat Model              | Identifies organizational threats, likelihood × impact prioritization, and maps each threat to ISMS controls | dentify (ID)      |

## Frameworks Covered

| Framework | How It's Applied |
|-----------|-----------------|
| **NIST CSF 2.0** | Primary framework for all six functions (Govern, Identify, Protect, Detect, Respond, Recover) |
| **NIST SP 800-61 Rev. 2** | Incident response lifecycle structure |
| **SOC 2 (AICPA TSC 2017)** | Cross-referenced in the Master Crosswalk |
| **ISO 27001** | Cross-referenced in the Master Crosswalk |
| **GLBA Safeguards Rule** | Regulatory driver for the mock org's ISMS requirement |
| **GDPR (EU 2016/679)** | Cross-referenced in the Master Crosswalk for data subject rights, breach notification, and data handling controls |

## Repository Structure

```
├── 01_Governance/             # AUP, RACI Matrix, risk appetite
├── 02_Framework-Mapping/      # NIST CSF Master Crosswalk (all 6 functions)
├── 03_Architecture/           # Data Flow Diagram with control overlay
├── 04_Incident-Response/      # IRP + Ransomware Playbook
├── 05_Remediation-Findings/   # Gap analysis, POA&M, lessons learned
├── 06_Templates/              # Policy review cadence, reusable templates
└── 99_Attachments/            # Exported diagrams and evidence
```


## Key Design Decisions

**Governance before controls.** Each document in this project comes from a risk appetite statement and an understanding of the organization. Controls are there to help guide governance, not the other way around.

**One ISMS, multiple frameworks.** The Master Crosswalk shows that a single, well-designed control program can handle NIST CSF, SOC 2, ISO 27001, and GLBA compliance at the same time. It’s all about mapping out what you need, not starting from scratch.

**Audit-ready documentation.** Each policy includes a header capturing the version, author, NIST control mapping, and current status. Every control in the crosswalk links directly to its supporting evidence. Auditors can trace a clear path from risk appetite to policy, control, and evidence, all within the repository.

## About

**D'Arcy Bracken**
[LinkedIn](https://linkedin.com/in/darcyvbracken)
