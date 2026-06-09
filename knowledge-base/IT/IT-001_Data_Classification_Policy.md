# Data Classification Policy

**Document ID:** IT-001  
**Category:** IT and Information Security  
**Version:** 2.4  
**Effective Date:** February 1, 2026  
**Review Date:** February 1, 2027  
**Document Owner:** Chief Information Security Officer  
**Approved By:** Chief Information Officer, Legal and Compliance  
**Status:** Active

---

## Purpose

This policy defines how Contoso Corporation classifies its information assets and the handling requirements associated with each classification level. Correct classification is the foundation of information security - it ensures that sensitive data receives appropriate protection while non-sensitive data is not over-restricted in ways that reduce productivity.

All employees who create, access, store, transmit, or dispose of Contoso information are required to comply with this policy.

---

## Scope

This policy applies to:

- All information created, processed, stored, or transmitted by Contoso employees, contractors, and partners
- All data formats including digital files, databases, physical documents, verbal communications, and visual displays
- All systems and environments including cloud, on-premises, remote work locations, and third-party platforms

---

## Classification Levels

Contoso uses four classification levels. Every piece of information created or received in the course of business must fall into one of these levels.

| Level | Label | Color Code | Definition |
|---|---|---|---|
| Level 1 | Public | Green | Information approved for unrestricted public release. No harm if disclosed externally. |
| Level 2 | Internal | Blue | Information for Contoso internal use only. Disclosure to unauthorized parties could cause minor reputational or operational impact. |
| Level 3 | Confidential | Amber | Sensitive business information. Disclosure to unauthorized parties could cause significant financial, legal, or competitive harm. |
| Level 4 | Restricted | Red | Highest sensitivity. Disclosure could cause severe and irreversible harm including regulatory penalties, major financial loss, or safety risks. |

---

## Examples by Classification Level

### Level 1 - Public

- Published marketing materials, press releases, and website content
- Job postings and recruitment advertisements
- Product brochures and public data sheets
- Annual reports and investor disclosures

### Level 2 - Internal

- Internal process documentation and standard operating procedures
- Employee directory (names and business contact information)
- General meeting notes not involving strategic or commercial topics
- Training materials not containing proprietary methodology
- Approved vendor lists (company names only, no contract terms)

### Level 3 - Confidential

- Customer contracts and contract terms
- Pricing models and discount frameworks
- Business strategy documents and plans not yet publicly announced
- Employee personal data (salary, performance reviews, health information)
- Financial statements prior to external publication
- Acquisition or merger discussions
- Supplier commercial terms and pricing

### Level 4 - Restricted

- Authentication credentials, encryption keys, and secrets
- Personally Identifiable Information (PII) subject to regulatory requirements (GDPR, CCPA, HIPAA)
- Payment Card Industry (PCI) data
- Source code for proprietary products
- Active legal matters and attorney-client privileged communications
- Board-level communications and M&A due diligence materials
- Security vulnerability assessments and penetration test results

---

## Handling Requirements by Classification Level

### Storage

| Requirement | Public | Internal | Confidential | Restricted |
|---|---|---|---|---|
| Cloud storage | Any approved platform | Contoso-managed platforms only | Contoso-managed platforms only | Contoso-managed platforms with encryption at rest |
| Physical storage | Unrestricted | Standard office environment | Locked cabinet or secure room | Locked cabinet in access-controlled room |
| Personal device storage | Permitted | Not permitted | Not permitted | Not permitted |
| Third-party cloud (non-approved) | Permitted | Not permitted | Prohibited | Prohibited |

### Transmission

| Requirement | Public | Internal | Confidential | Restricted |
|---|---|---|---|---|
| Email (internal) | Permitted | Permitted | Permitted with label in subject | Encrypted email only |
| Email (external) | Permitted | Not recommended | Approved recipients only; label required | Prohibited except with CISO approval |
| Messaging platforms (Teams) | Permitted | Permitted | Permitted in approved channels | Prohibited in general channels |
| File sharing (external link) | Permitted | Approved platforms only | Expiring links only; require authentication | Prohibited |
| Physical mail | Permitted | Standard envelope | Sealed envelope; tracked delivery | Courier with signature; sealed tamper-evident packaging |

### Access Controls

| Requirement | Public | Internal | Confidential | Restricted |
|---|---|---|---|---|
| Default access | Anyone | All Contoso employees | Role-based access control (RBAC) | Named individuals only; access log required |
| External access | Permitted | Not without NDA | Not without NDA and CISO review | Not without explicit Legal + CISO approval |
| Access review frequency | N/A | Annual | Quarterly | Monthly |
| Multi-Factor Authentication required | No | No | Yes | Yes; Phishing-Resistant MFA required |

### Retention and Disposal

| Classification | Retention Period | Disposal Method |
|---|---|---|
| Public | Per content type; minimum 1 year | Standard deletion |
| Internal | 3 years from creation or last use | Secure deletion (overwrite or degauss) |
| Confidential | 7 years or per legal / regulatory requirement | Certified secure deletion or physical destruction |
| Restricted | Per legal and regulatory requirement (varies) | CISO-approved destruction with certificate |

---

## Labeling Requirements

All documents, files, and communications containing Confidential or Restricted information must be labeled with the appropriate classification marker.

| Format | Labeling Method |
|---|---|
| Microsoft Office documents | Microsoft Purview sensitivity label applied |
| Emails | Sensitivity label applied via Outlook; classification in subject line for Confidential |
| Physical documents | Printed header and footer on every page |
| Presentations | Classification label on title slide and footer on every slide |
| Source code repositories | README header and repository-level classification tag |
| Database tables | Classification metadata field in schema |

---

## Responsibilities

| Role | Responsibility |
|---|---|
| Data Owner | Assigns initial classification; approves access requests; reviews classification annually |
| Data Custodian (IT) | Implements technical controls aligned to classification level |
| Employee | Applies correct classification labels; handles data per policy; reports suspected misclassification or breach |
| CISO | Sets policy; approves exceptions; oversees classification program |
| Legal and Compliance | Advises on regulatory requirements; approves Restricted data access for external parties |

---

## Exceptions

Requests to deviate from handling requirements must be submitted to the CISO via the Security Risk Exception form. Exceptions are reviewed within 5 business days and are valid for a maximum of 90 days unless renewed. All exceptions are logged and reported quarterly to the Information Security Steering Committee.

---

## Related Documents

- IT-002: Acceptable Use Policy
- IT-003: Vendor Onboarding Security Requirements
- Legal-002: Data Privacy and GDPR Compliance Policy
- HR-001: Employee Code of Conduct

---

*Questions about data classification? Contact the Information Security team at security@contoso.com.*
