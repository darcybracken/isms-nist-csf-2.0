---
Title: Findings & Outcomes Summary
Type: .md
Repo: ISMS Portfolio Project
Status: Approved
Created_date: 2026-05-06
Reviewed_date: 2026-05-19
Author: D'Arcy Bracken
Version: "1.0"
---
---

## Outcome

This document is intended for technical reviewers, hiring managers, and auditors evaluating the scope and quality of this ISMS project. This project produced a security documentation package demonstrating the design and implementation of an **Information Security Management System** aligned to **NIST CSF 2.0.** The package is structured for audit readability, searchability, and continuous improvement.

## What Was Built

| Artifact                  | Purpose                                                      | NIST Function | Location                                                   |
| ------------------------- | ------------------------------------------------------------ | ------------- | ---------------------------------------------------------- |
| ISMS Project Overview     | Define scope, methodology, mock org context                  | GV (Govern)   | Project-Overview                                           |
| Governance Framework      | Risk appetite, roles, policy structure                       | GV (Govern)   | 01_Governance/Governance-Index                             |
| Acceptable Use Policy     | Define acceptable behavior and data handling rules           | GV, PR        | 01_Governance/Policies/Acceptable-Use-Policy               |
| RACI Matrix               | Assign accountability for all security activities            | GV            | 01_Governance/Roles/RACI-Matrix                            |
| NIST CSF Master Crosswalk | Map all controls to NIST subcategories with cross-compliance | All 6         | 02_Framework-Mapping/NIST-CSF-Master-Crosswalk             |
| Data Flow Architecture    | Visualize data journey with control overlay                  | ID, PR        | Architecture-Index                                         |
| Incident Response Plan    | 6-stage response lifecycle with severity matrix              | RS, RC        | 04_Incident-Response/Incident-Response-Plan                |
| Ransomware Playbook       | Scenario-specific procedures for ransomware                  | RS, RC        | 04_Incident-Response/Incident-Response-Playbook-Ransomware |
| Obsidian Knowledge Base   | Centralized, tagged, linked documentation system             | GV            | Entire vault                                               |

## Key Actions Taken

### 1. Standardized Governance
Eliminated policy ambiguity by adhering strictly to the NIST CSF 2.0 structure. Every policy and control maps to a specific NIST subcategory, ensuring no gaps between organizational intent and documented practice. The crosswalk table serves as the single source of truth for auditors.

### 2. Enhanced Auditability
Built an Obsidian-based documentation system where every document carries YAML frontmatter for version control, authorship, NIST mapping, and status. Tag taxonomy and wikilinks connect policies to controls, controls to procedures, and procedures to evidence, creating a traceable compliance chain that supports rapid retrieval during an audit.

### 3. Strategic Visualization
Bridged the gap between technical infrastructure and management policy through a Data Flow Diagram that overlays NIST controls at every enforcement point. This demonstrates that security controls are integral to the architecture, not retrofitted after the fact.

### 4. Unified Compliance
Demonstrated that a single ISMS can satisfy multiple frameworks simultaneously. The crosswalk maps NIST CSF to SOC 2, ISO 27001, GLBA, and GDPR, showing that a well-built program does not need to be rebuilt for each regulation.

## Gap Analysis

The following gaps were identified during the documentation process. In a production ISMS, these would be tracked on a formal Plan of Action and Milestones (POA&M).

| Gap ID | Description | NIST Reference | Priority | Recommended Action | Scope | Status |
|--------|-------------|----------------|----------|--------------------|-------|--------|
| GAP-001 | No asset inventory exists | ID.AM-01, ID.AM-02 | High | Create hardware and software inventory with criticality ratings | In scope | Open |
| GAP-002 | Technical controls not yet deployed | PR.AA-01, PR.DS-01 | High | Deploy MFA, encryption, EDR | Out of scope | Open |
| GAP-003 | SIEM not deployed | DE.CM-01, DE.AE-02 | High | Deploy SIEM with log sources configured | Out of scope | Open |
| GAP-004 | IRP not yet tested via exercise | RS.MA-01, ID.IM-02 | Medium | Conduct tabletop exercise using ransomware scenario | In scope | Open |
| GAP-005 | Backup procedures not formalized | RC.RP-03 | Medium | Create backup SOP with monthly test schedule | In scope | Open |
| GAP-006 | Supply chain risk not fully addressed | GV.SC-01, GV.SC-02 | Low | Develop third-party risk assessment questionnaire | In scope | Open |
| GAP-007 | No security awareness training program | PR.AT-01 | Medium | Design annual training curriculum with phishing simulations | In scope | Open |

## Lessons Learned

### What Worked Well
- **Starting with governance before controls** meant that every subsequent document had a clear purpose and authority. The risk appetite statement drove control prioritization naturally.
- **Using Obsidian's linking and tagging** created a living document set rather than a collection of isolated files. Searching `#compliance/nist/respond` instantly surfaces every document related to incident response.
- **Writing for a mock organization** forced realistic decisions. Choosing FinCorp as a regulated financial company meant every control had to justify itself against actual compliance requirements.
- **Following NIST CSF 2.0's structure** provided a natural organizing principle. The six functions tell a story that flows logically from governance through recovery.

### What Could Be Improved
- **The DFD needs to be created in Lucidchart or Visio.** The text-based version communicates the concept but is not presentation-ready. The diagram should be the first evidence attachment produced.
- **Testing the IRP** would significantly strengthen the portfolio. Even a solo tabletop walkthrough with timestamped notes would demonstrate practical application.
- **Adding an asset inventory** would complete the Identify function. A simple spreadsheet with hostname, IP, OS, owner, classification, and criticality would be sufficient.

## Evidence & Attachments

| Artifact               | Format                               | Location                                                                                                                                       |
| ---------------------- | ------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| NIST Mapping Matrix    | PNG (Lucidchart)                     | [NIST Mapping Matrix](https://raw.githubusercontent.com/darcybracken/isms-nist-csf-2.0/main/99_Attachments/Lab-002/NIST_Mapping_Table.png)     |
| Data Flow Architecture | PNG (Lucidchart)                     | [Data Flow Architecture](https://raw.githubusercontent.com/darcybracken/isms-nist-csf-2.0/main/99_Attachments/Lab-002/ISMS_Architecture.png)   |
| Knowledge Base Graph   | PNG (Obsidian graph view screenshot) | [Knowledge Base Graph](https://raw.githubusercontent.com/darcybracken/isms-nist-csf-2.0/main/99_Attachments/Lab-002/Obsidian_Policy_Graph.png) |

## Conclusion

This project covers the full process of building an ISMS: selecting a framework, establishing governance and risk appetite, mapping controls, drafting policies, designing architecture, and documenting findings. The resulting knowledge base is searchable, interconnected, version-controlled, and structured to support audit presentation. This documentation package is Version 1.0, a foundation to be tested, refined, and improved.

An ISMS is not a binder on a shelf. It is a system: a connected set of documents, processes, and feedback loops that work together. The value is not in any single policy but in the relationships between them. The AUP requires incident reporting. The IRP defines how to respond. The lessons learned update the AUP. The crosswalk tracks it all. Break any link in that chain and the system degrades.

[[Governance-Index]]
[[NIST-CSF-Master-Crosswalk]]
[[Incident-Response-Plan]]