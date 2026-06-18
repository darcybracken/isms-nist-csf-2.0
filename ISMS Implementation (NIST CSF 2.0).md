# Lab-003: ISMS Implementation (NIST CSF 2.0)

![NIST CSF](https://img.shields.io/badge/NIST-CSF_2.0-darkblue)
![ISO 27001](https://img.shields.io/badge/ISO-27001-blue)
![SOC 2](https://img.shields.io/badge/SOC_2-Type_II_Ready-green)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

> A 14-document Information Security Management System (ISMS) for a mock financial services organization, mapped to NIST CSF 2.0 with cross-compliance traceability to SOC 2, ISO 27001, GLBA, and GDPR.

## What This Lab Delivers

A complete, audit-ready ISMS including:

- Governance Framework and Risk Appetite Statement
- Acceptable Use Policy (FC-POL-001)
- Logging and Monitoring Policy (FC-POL-002)
- Incident Response Plan
- Ransomware Playbook
- RACI Matrix
- NIST CSF 2.0 Master Crosswalk
- Data Flow Architecture with NIST Control Overlay
- Threat Model
- Policy Review Cadence
- Obsidian Knowledge Base with YAML frontmatter, tag taxonomy, and wikilink traceability

For the full artifact list and audit trail, see the [Findings & Outcomes Summary](./Findings-Outcomes-Summary.md).

## Connection to Lab-009

FC-POL-002 commits to detecting brute force attacks (AC-7) and tracking admin account changes (AU-9). Lab-009 provides the technical proof: a live Splunk dashboard that operationalizes those policy statements.

## Supporting Documentation

| Document                                                       | What It Covers                                                                                  |
| -------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [THREAT-MODEL.md](./THREAT-MODEL.md)                           | Threat identification, likelihood × impact prioritization, and control mapping for the mock org |
| [Findings-Outcomes-Summary.md](./Findings-Outcomes-Summary.md) | Full artifact inventory, gap analysis, lessons learned, and audit evidence                      |
