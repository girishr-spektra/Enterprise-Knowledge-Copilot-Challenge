# Vendor Onboarding Security Requirements

**Document ID:** IT-003  
**Category:** IT and Information Security - Third Party Risk  
**Version:** 1.8  
**Effective Date:** June 1, 2025  
**Review Date:** June 1, 2026  
**Document Owner:** Chief Information Security Officer  
**Approved By:** Chief Information Officer, VP Procurement, Legal and Compliance  
**Status:** Active

---

## Purpose

This document defines the mandatory security requirements that all third-party vendors, suppliers, and partners must meet before being granted access to Contoso systems, data, or infrastructure. It establishes the assessment process, security tiers, contractual obligations, and ongoing monitoring requirements for vendor relationships.

---

## Scope

This policy applies to all vendors who will:

- Access Contoso systems, applications, or networks
- Process, store, or transmit Contoso data on behalf of Contoso
- Provide software or services that integrate with Contoso infrastructure
- Have physical access to Contoso facilities where data systems are present

It does not apply to vendors providing purely physical goods with no data or system access.

---

## Vendor Security Tiers

Vendors are classified into three security tiers based on the sensitivity of data they will access and the depth of system integration required.

| Tier | Name | Criteria | Examples |
|---|---|---|---|
| Tier 1 | Critical | Access to Restricted data; deep system integration; access to production infrastructure | Core SaaS providers, cloud infrastructure vendors, MSSPs |
| Tier 2 | Standard | Access to Confidential data; limited system integration; no production infrastructure access | CRM tools, HR software vendors, marketing platforms |
| Tier 3 | Low Risk | Access to Internal data only; minimal or no system integration | Training providers, event management tools, office suppliers with portal access |

Tier classification is assigned by the CISO in consultation with the business sponsor.

---

## Pre-Onboarding Assessment Requirements

### Required Documentation by Tier

| Document / Certification | Tier 1 | Tier 2 | Tier 3 |
|---|---|---|---|
| Information Security Policy (current version) | Required | Required | Requested |
| SOC 2 Type II report (within 12 months) | Required | Required | Not required |
| ISO 27001 certification (current) | Required or equivalent | Preferred | Not required |
| Penetration test report (within 12 months) | Required | Required for cloud-hosted services | Not required |
| Business Continuity and Disaster Recovery Plan | Required | Requested | Not required |
| Data Processing Agreement (DPA) | Required | Required if processing personal data | Required if processing personal data |
| Sub-processor list | Required | Required | Not required |
| Right to audit clause acceptance | Required | Preferred | Not required |
| Cybersecurity insurance ($5M minimum coverage) | Required | Required | Not required |
| Completed Contoso Security Questionnaire | Required (full) | Required (standard) | Required (brief) |

### Assessment Process

| Step | Activity | Owner | Timeline |
|---|---|---|---|
| 1 | Business sponsor submits Vendor Onboarding Request via Procurement portal | Business sponsor | Before vendor engagement |
| 2 | Procurement validates commercial and legal requirements | Procurement | Within 3 business days |
| 3 | IT Security receives request; assigns tier and sends questionnaire | IT Security | Within 3 business days |
| 4 | Vendor completes and returns questionnaire | Vendor | Within 10 business days |
| 5 | IT Security reviews questionnaire and documentation | IT Security | Within 7 business days |
| 6 | Risk assessment report produced; findings shared with sponsor | IT Security | Within 3 business days |
| 7 | Remediation plan agreed (if required) | IT Security + Vendor | Within 5 business days of report |
| 8 | CISO approval for Tier 1; IT Security Manager approval for Tier 2/3 | CISO / IT Security Manager | Within 3 business days |
| 9 | Contract signed including security clauses; access provisioned | Legal, IT | As per contract schedule |

Total typical timeline: Tier 1: 30-40 business days. Tier 2: 20-25 business days. Tier 3: 10-15 business days.

---

## Contractual Security Requirements

All vendor contracts must include the following clauses. Legal reviews contracts for compliance before signature.

| Clause | Required For | Description |
|---|---|---|
| Data Processing Agreement (DPA) | All tiers where personal data is processed | Governs lawful basis, purpose limitation, and sub-processor controls |
| Security incident notification | Tier 1, Tier 2 | Vendor must notify Contoso within 24 hours of a confirmed or suspected breach affecting Contoso data |
| Right to audit | Tier 1 | Contoso may conduct or commission a security audit with 30-day notice |
| Data return and deletion | All tiers | On contract termination, vendor must return or securely destroy all Contoso data within 30 days and certify deletion |
| Sub-processor restrictions | Tier 1, Tier 2 | Vendor must notify Contoso 30 days before adding sub-processors; Contoso has right to object |
| Security standard maintenance | All tiers | Vendor must maintain security certifications for the duration of the contract |
| Regulatory compliance | All tiers where applicable | Vendor must comply with GDPR, CCPA, and other applicable data protection laws |

---

## Minimum Technical Security Controls

Vendors must demonstrate the following technical controls are in place, assessed through the questionnaire and evidence review:

| Control | Tier 1 | Tier 2 | Tier 3 |
|---|---|---|---|
| Encryption at rest (AES-256 or equivalent) | Required | Required | Required if storing Contoso data |
| Encryption in transit (TLS 1.2 minimum) | Required | Required | Required |
| Multi-Factor Authentication for admin access | Required | Required | Strongly recommended |
| Role-based access control to Contoso data | Required | Required | Required |
| Vulnerability management program (monthly scanning) | Required | Required | Not required |
| Security awareness training for staff with Contoso data access | Required (annual, documented) | Required (annual) | Recommended |
| Endpoint protection (EDR or equivalent) | Required | Required | Recommended |
| Logging and monitoring of access to Contoso data | Required (90-day retention) | Required (30-day retention) | Recommended |
| Incident response plan covering Contoso data scenarios | Required | Required | Not required |
| Background screening for personnel with access to Restricted data | Required | Not required | Not required |

---

## Ongoing Monitoring Requirements

Vendor approval is not a one-time event. Contoso conducts ongoing monitoring of vendor security posture.

| Activity | Tier 1 | Tier 2 | Tier 3 |
|---|---|---|---|
| Annual security review and questionnaire renewal | Yes | Yes | Yes |
| SOC 2 / ISO 27001 certification renewal verification | Yes - annually | Yes - on renewal | Not applicable |
| Continuous monitoring via third-party risk tools | Yes (automated scoring) | Not required | Not required |
| On-site or virtual audit | Every 2 years or after a security incident | Upon significant security incidents | Not required |
| Review after a security incident (vendor or industry) | Immediate review | Within 30 days | Upon Contoso request |

---

## Vendor Security Incidents

If a vendor experiences a security incident that may affect Contoso data:

1. The vendor must notify the Contoso IT Security team within 24 hours of confirmed or suspected impact
2. The vendor must provide a written incident summary within 72 hours
3. Contoso IT Security will conduct an impact assessment and determine response actions
4. If Contoso data was compromised, the incident enters the Contoso Data Breach Response process (see Security-003)
5. Remediation steps and a vendor post-incident review are required within 30 days

---

## Offboarding

When a vendor relationship ends:

| Step | Action | Timeline |
|---|---|---|
| 1 | Business sponsor initiates offboarding via Procurement portal | At contract end or termination notice |
| 2 | IT revokes all system access and credentials | Within 1 business day of contract end |
| 3 | Vendor provides data deletion certificate | Within 30 days of contract end |
| 4 | IT Security verifies access removal and documents completion | Within 5 business days |
| 5 | Vendor record archived in Third Party Risk registry | On completion |

---

## Related Documents

- IT-001: Data Classification Policy
- IT-002: Acceptable Use Policy
- FIN-001: Procurement Policy
- Legal-002: Data Privacy and GDPR Compliance Policy
- Security-003: Data Breach Response Procedure

---

*Initiate vendor onboarding via the Procurement portal. Security questions: security@contoso.com.*
