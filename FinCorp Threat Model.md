---
Title: FinCorp Threat Model
Type: .md
Repo: ISMS Portfolio Project
Status: Approved
Created_date: 2026-05-13
Reviewed_date: 2026-05-19
Author: D'Arcy Bracken
Version: "1.0"
---
---

## Structure

- **Organization:** FinCorp (mock financial services organization)
- **Framework:** NIST CSF 2.0 IDENTIFY function (ID.RA)
- **Version:** 1.0 May 2026

> This threat model identifies the threats FinCorp faces, prioritizes them using a likelihood × impact framework, and maps each threat to the ISMS controls designed to counter it. It operationalizes the IDENTIFY function of NIST CSF 2.0 and provides the evidentiary basis for the control decisions throughout this ISMS.


## Organization Context

FinCorp is a mid-size financial services organization subject to GLBA (handling consumer financial data) and GDPR (processing EU resident personal data). It operates a mix of cloud-hosted and on-premises infrastructure, maintains a customer-facing web portal, and employs approximately 200 staff across three offices.

**Risk appetite:** Low. The cost of a breach, including regulatory fines, reputational damage, and customer notification obligations, far exceeds the cost of preventive controls.

**Crown jewels:** Customer PII and financial records, payment processing systems, employee credentials, internal network access.

## Threat Identification

### Social Engineering and Phishing

**Mechanism:** Fraudulent communications, email, phone, or text, designed to manipulate employees into revealing credentials, clicking malicious links, or transferring funds. Exploits human trust, not technical vulnerabilities.

**Relevance to FinCorp:** Financial services organizations are high-value targets for phishing. Wire transfer fraud (business email compromise) is a direct financial risk. A single compromised credential can provide the initial foothold for a broader breach.

**ISMS controls:** Security Awareness Training is a planned ISMS control (see GAP-007 in the Findings and Outcomes Summary) an annual training curriculum with phishing simulations is the recommended action. MFA (FC-POL-001 §3.5) means stolen credentials alone are insufficient without the second factor.

### Credential-Based Attacks (Brute Force and Credential Stuffing)

**Mechanism:** Brute force systematically tries password combinations until one works. Credential stuffing uses real username/password pairs stolen from unrelated breaches, banking on password reuse across sites. Credential stuffing is more efficient and harder to detect because the credentials are valid-looking.

**Relevance to FinCorp:** Customer and employee portals are exposed to the internet. Credential-based attacks against these surfaces are automated and continuous. A successful attack yields direct account access without any exploit.

**ISMS controls:** Account lockout policy (FC-POL-001) limits brute force attempts. MFA (FC-POL-001 3.5), a second factor from a different authentication category (e.g., possession: smartphone code), blocks credential stuffing even when a valid password is known. Anomalous login pattern detection is addressed in the Logging and Monitoring Policy (FC-POL-002, in development) via the AAA Accounting function. This threat is the direct basis for the AC-7 control validated in Lab-009.


### Ransomware

**Mechanism:** Malware encrypts files and demands payment for decryption. Modern ransomware typically involves a multi-stage attack: initial compromise (often phishing), lateral movement to high-value systems, data exfiltration, and then encryption. The exfiltration stage creates a secondary extortion vector even if backups exist.

**Relevance to FinCorp:** Financial services organizations are a primary ransomware target due to their ability to pay and the regulatory pressure to restore operations quickly. GLBA notification requirements create additional urgency and reputational risk.

**ISMS controls:** Endpoint protection and patch management (FC-POL-001 §3.5). Network segmentation limits lateral movement. Backup and recovery procedures ensure operational continuity. The Incident Response Plan and Ransomware Playbook provide a structured response. Security awareness training addresses the phishing vector that typically initiates the attack.


### Insider Threat

**Mechanism:** A current or former employee, contractor, or trusted third party misuses their authorized access either maliciously (data theft, sabotage) or negligently (accidental exposure, misconfiguration). Insider threats are difficult to detect because the actor has legitimate credentials and access.

**Relevance to FinCorp:** Financial data is high-value on the secondary market. Employees with access to customer PII, payment systems, or financial records are potential insider threat actors. Contractors with temporary elevated access represent a secondary surface.

**ISMS controls:** Least Privilege limits the damage any individual can cause. Separation of Duties prevents single-actor fraud on high-risk transactions. RBAC ensures every employee's access is scoped to their job function with no inherited or residual permissions from previous roles. Account deprovisioning procedures (FC-POL-001 3.1) require access to be removed promptly on departure. The Accounting component of the AAA framework is the primary detection mechanism: the Logging and Monitoring Policy (FC-POL-002, in development) requires logging of every login, privilege use, and administrative action, creating an attributable audit trail. AU-9 in Lab-009 validates this control. Honeypots on the internal network are a recommended control for early detection of lateral movement; deployment is out of scope for this documentation project.


### Man-in-the-Middle (MitM) and Interception

**Mechanism:** An attacker positions themselves between two communicating endpoints to intercept, read, or modify data in transit. Can be executed via ARP spoofing on a local network, DNS poisoning (pharming), or by luring users onto a rogue access point or evil twin Wi-Fi network.

**Relevance to FinCorp:** Customer-facing web traffic contains credentials and financial data. Internal network traffic may include unencrypted administrative communications. Any unencrypted channel is a potential interception surface.

**ISMS controls:** TLS/HTTPS enforced for all customer-facing and administrative web traffic (FC-POL-001 §3.4). VPN required for remote access to internal systems (FC-POL-001 §3.5). MFA limits the value of intercepted credentials. DNSSEC and certificate validation mitigate pharming and rogue access point vectors.


### SQL Injection and Web Application Attacks

**Mechanism:** Malicious input submitted through web form fields is interpreted as database commands. A successful SQL injection attack can expose, modify, or delete database contents, including the entire customer PII and financial records store.

**Relevance to FinCorp:** The customer-facing web portal directly interfaces with the customer database. Financial services web applications are a high-value target. A single injection vulnerability in an input field can bypass all network-level controls.

**ISMS controls:** WAF (Web Application Firewall) deployed in front of the customer portal blocks injection attempts at the application layer. Input validation requirements in the secure development lifecycle. OWASP Top 10 referenced in architecture standards.


### Denial-of-Service (DoS/DDoS)

**Mechanism:** Flooding a target with traffic to exhaust its resources and make it unavailable. Distributed DoS uses a botnet of many compromised systems attacking simultaneously, making source-based blocking ineffective.

**Relevance to FinCorp:** Customer portal unavailability has direct revenue and regulatory implications. Under GLBA, prolonged service disruption may trigger notification obligations. DDoS attacks are sometimes used as a distraction while a separate, lower-profile attack proceeds.

**ISMS controls:** IPS with anti-DDoS capability at the perimeter. Uptime SLA is defined in the Risk Appetite Statement (99.5% target). The Incident Response Plan covers availability incidents. Monitoring baseline detects traffic anomalies before they become outages.


## Threat Prioritization

Risk is assessed using likelihood × impact. Controls address the highest-priority combinations first.

| Threat | Likelihood | Impact | Priority | Primary ISMS Control |
|--------|-----------|--------|----------|---------------------|
| Phishing / Social Engineering | High | High | **Critical** | Security Awareness Training + MFA |
| Credential Stuffing / Brute Force | High | High | **Critical** | MFA + Account Lockout + Monitoring |
| Ransomware | Medium | Critical | **Critical** | Backups + IR Playbook + Endpoint Protection |
| SQL Injection | Medium | High | **High** | WAF + Input Validation |
| Insider Threat | Low | High | **High** | Least Privilege + SoD + Audit Logging |
| MitM / Interception | Medium | Medium | **Medium** | TLS Everywhere + VPN + MFA |
| DoS / DDoS | Medium | Medium | **Medium** | IPS + Monitoring + IR Plan |

**Risk response logic:** High likelihood + high impact = address first. Low likelihood + high impact = controls are warranted but lower priority than high-likelihood threats. The goal is not zero risk: it is acceptable residual risk managed by documented controls.


## Connection to Lab-009

The credential-based attack row, which includes brute force and credential stuffing is the direct basis for the technical validation performed in Lab-009. FC-POL-002 3.4 commits to detecting 10+ failed logins from a single IP in a 24-hour window. Lab-009's Splunk dashboard implements and proves that commitment: Panel 1 (failed login count) and Panel 2 (brute force source table) operationalize the AC-7 control.

**The chain:** Threat identified here → policy written in FC-POL-002 → control mapped in the NIST CSF Crosswalk → detection logic built in Lab-009 → dashboard provides audit evidence.

---

*This document will be updated as the ISMS matures and additional threat intelligence is incorporated.*
