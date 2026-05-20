---
Title: RACI Matrix - Information Security
Type: .md
Repo: 01_Governance
Status: Approved
Created_date: 2026-03-12
Reviewed_date: 2026-05-19
Author: D'Arcy Bracken
Version: "1.0"
---
---

## RACI Key

| Letter | Meaning | Definition |
|--------|---------|------------|
| **R** | Responsible | Does the work |
| **A** | Accountable | Owns the outcome; makes final decisions (only one per row) |
| **C** | Consulted | Provides input before a decision is made |
| **I** | Informed | Notified after a decision or action is taken |

## FinCorp - Security RACI

| Activity | CEO | CISO | IT Director | Security Team | HR | All Staff |
|----------|-----|------|-------------|---------------|----|-----------|
| Approve security policies | I | A | C | R | C | I |
| Define risk appetite | A | R | C | I | I | I |
| Conduct risk assessments | I | A | C | R | I | I |
| Implement technical controls | I | A | R | R | I | I |
| Monitor security events (SIEM) | I | A | I | R | I | I |
| Respond to security incidents | I | A | C | R | C | I |
| Manage user access | I | A | R | R | C | I |
| Security awareness training | I | A | C | R | R | R |
| Audit and compliance review | C | A | C | R | I | I |
| Third-party risk assessment | I | A | C | R | I | I |
| Incident post-mortem review | I | A | R | R | C | I |
| Policy exception approval | I | A | C | I | I | I |
| Data classification decisions | I | A | R | C | I | R |
| Backup and recovery testing | I | A | R | R | I | I |

## Key Observations

**The CISO is Accountable for nearly everything.** In smaller to medium-sized organizations, this structure is intentional. The CISO is the primary owner of security decisions regardless of who performs the work. This is consistent with NIST CSF GV.RR-01, which requires organizational leaders to be responsible and accountable for cybersecurity risk.

**All Staff is Responsible for training and data classification.** Security is not solely an IT function. Every employee plays a role in managing and categorizing data appropriately, consistent with the NIST CSF principle that a strong security culture is a core governance requirement.

**HR is Consulted on incidents and enforcement.** When security policy violations occur, HR involvement ensures that personnel actions are handled through proper channels and that decisions are not made unilaterally by the security team.

## NIST CSF Alignment

| NIST Subcategory | How This Matrix Supports It                                                                |
| ---------------- | ------------------------------------------------------------------------------------------ |
| GV.RR-01         | Leadership accountability is explicitly assigned through the CEO and CISO rows             |
| GV.RR-02         | Roles, responsibilities, and authorities are defined for every security activity           |
| GV.RR-03         | Resource allocation is reflected in the Responsible column, showing where work is assigned |
