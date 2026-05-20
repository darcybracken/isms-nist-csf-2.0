---
Title: Acceptable Use Policy
Type: .md
Repo: 01_Governance
Status: Approved
Created_date: 2026-03-15
Reviewed_date: 2026-05-19
Author: D'Arcy Bracken
Version: "1.0"
---
---

## Structure

- **Organization:** FinCorp
- **Policy ID:** FC-POL-001
- **Effective Date:** 2026-03-07
- **Last Reviewed:** 2026-04-01
- **Next Review:** Quarterly (see Policy Review Cadence 2026)

## 1. Purpose

This policy outlines how FinCorp’s information technology resources should be used. Its purpose is to safeguard the company’s data, systems, and reputation by setting clear guidelines for everyone who uses company resources.

**NIST CSF Alignment:** This policy directly supports **GV.PO-01** (cybersecurity policy is established based on organizational context) and **GV.PO-02** (policy is reviewed and updated).

## 2. Scope

This policy applies to:

- Everyone at the company, including employees, contractors, and temporary staff
- All devices that the company owns or manages, like laptops, mobile devices, and servers
- All company data, no matter where it’s saved or used
- All network resources, such as VPNs, Wi-Fi, and cloud services (like Microsoft 365 and AWS)
- Personal devices that employees bring to work to access company resources (BYOD)

## 3. Policy Statements
### 3.1 

**All users must:**

- Use company resources only for authorized business activities
- Protect their login credentials and never share passwords
- Lock their workstation when unattended (automatic lock after 5 minutes of inactivity)
- Report suspected security incidents immediately per the 04_Incident-Response/Incident-Response-Plan  
### 3.2 Prohibited Activities

The following activities are prohibited on company resources:

- Accessing, downloading, or distributing illegal content
- Installing unauthorized software without IT approval
- Connecting unauthorized devices to the corporate network
- Attempting to bypass or disable security controls (antivirus, firewall, DLP)
- Sharing company data through unapproved channels (personal email, unauthorized cloud storage)
- Using company resources for cryptocurrency mining or personal commercial ventures
### 3.3 Data Handling

All company data must be handled according to its classification:

| Classification   | Definition                                              | Handling Requirements                                                                                                                |
| ---------------- | ------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| **Confidential** | PII, financial records, credentials, trade secrets      | Encrypted at rest (AES-256) and in transit (TLS 1.2+). Access restricted to need-to-know. No external sharing without CISO approval. |
| **Internal**     | Internal communications, non-public reports, procedures | Store on approved company systems only. Do not share externally without manager approval.                                            |
| **Public**       | Published marketing materials, press releases           | No special handling required.                                                                                                        |

**NIST CSF Alignment:** Data classification supports **PR.DS-01** (data-at-rest protection), **PR.DS-02** (data-in-transit protection), and **ID.AM-07** (data inventory and metadata)

### 3.4 Email and Communications

- Company email must not be used for personal financial transactions
- Sensitive data must not be sent via email without encryption
- Users must verify sender identity before clicking links or opening attachments
- Suspected phishing emails must be reported to the security team immediately
### 3.5 Remote Access

- Remote access to company resources requires VPN with multi-factor authentication (MFA)
- Company data must not be stored on personal devices unless the device is enrolled in the MDM program
- Public Wi-Fi must not be used to access company resources without an active VPN connection
### 3.6 Physical Security

- Laptops must be physically secured when in public spaces
- Removable media (USB drives) are prohibited unless explicitly approved by IT
- Printed confidential documents must be retrieved promptly and shredded when no longer needed

## 4. Enforcement
### 4.1 Monitoring

FinCorp reserves the right to monitor, log, and audit all use of company IT resources. This includes network traffic, email communications, file access, and authentication events. Monitoring data is retained for a minimum of 90 days per the audit logging requirements (see 02_Framework-Mapping/NIST-CSF-Master-Crosswalk - DE.AE).

### 4.2 Violations

Violations of this policy may result in:

- Verbal or written warning
- Temporary suspension of IT access
- Termination of employment
- Legal action, where applicable

The severity of the response is proportional to the violation and is determined by the employee's manager in consultation with HR and the CISO.

## 5. Roles and Responsibilities

| Role | Responsibility |
|------|---------------|
| **All Users** | Read, understand, and comply with this policy |
| **IT Department** | Implement technical controls that enforce this policy, respond to violations |
| **CISO** | Approve policy make risk-based exceptions; oversee compliance |
| **HR** | Ensure policy is acknowledged during onboarding; support enforcement actions |
| **Managers** | Ensure team members are aware of and comply with this policy |

See **01_Governance/Roles/RACI-Matrix**  for the full responsibility assignment matrix

## 6. Exceptions

Exceptions to this policy require written approval from the CISO. Exception requests must include:

- The specific policy provision being excepted
- Business justification
- Duration of the exception
- Compensating controls in place
- Risk assessment

Approved exceptions are logged in the risk register and reviewed quarterly.

## 7. Review and Maintenance

This policy is reviewed **quarterly** and updated as needed based on:

- **Changes** in regulatory requirements
- **Findings** from audits or security incidents
- **Changes** in technology or business operations
- **Results** from the PDCA improvement cycle

The review schedule is tracked in Policy Review Cadence

**NIST CSF Alignment:** Review cadence supports **GV.PO-02** (policy for managing cybersecurity risks is reviewed, updated, communicated, and enforced).

## 8. Acknowledgment
All personnel must sign an acknowledgment confirming they have read, understood, and agree to comply with this policy. Acknowledgment is required at onboarding and annually thereafter.

```

I, _________________________, acknowledge that I have read and understood

the FinCorp Acceptable Use Policy (FC-POL-001).

I agree to comply with all provisions of this policy.

  

Signature: _________________________ Date: _______________

```

