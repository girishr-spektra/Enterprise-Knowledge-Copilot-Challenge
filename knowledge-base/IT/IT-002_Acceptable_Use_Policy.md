# Acceptable Use Policy

**Document ID:** IT-002  
**Category:** IT and Information Security  
**Version:** 3.1  
**Effective Date:** April 1, 2025  
**Review Date:** April 1, 2026  
**Document Owner:** Chief Information Security Officer  
**Approved By:** Chief Information Officer  
**Status:** Active

---

## Purpose

This Acceptable Use Policy (AUP) defines how Contoso Corporation's technology resources, systems, and data may be used by employees, contractors, and any party granted access. It protects Contoso's assets, ensures legal compliance, and maintains a productive and secure technology environment.

All users of Contoso systems are required to comply with this policy as a condition of access.

---

## Scope

This policy covers all technology resources owned, operated, or managed by Contoso, including:

- Computing devices: laptops, desktops, tablets, mobile phones (company-issued and BYOD enrolled in MDM)
- Network infrastructure: Contoso office networks, VPN, and Wi-Fi
- Cloud platforms and SaaS applications: Microsoft 365, Azure, Salesforce, and all other approved tools
- Communication tools: email (Outlook), messaging (Teams), video conferencing (Teams), and collaboration platforms (SharePoint, OneDrive)
- Development systems: code repositories, CI/CD pipelines, Azure DevOps, GitHub Enterprise
- Data assets: all information created, stored, processed, or transmitted using Contoso systems

---

## Permitted Uses

### General Use

| Activity | Permitted | Notes |
|---|---|---|
| Business communications (email, Teams) | Yes | Primary intended use |
| Document creation and collaboration | Yes | Use approved M365 tools |
| Internet browsing for business purposes | Yes | Via approved browser |
| Accessing approved SaaS applications | Yes | See the Approved Software list in IT portal |
| Personal use - incidental and reasonable | Yes | Must not interfere with work; subject to monitoring |
| Remote access via VPN | Yes | Required for internal system access outside office |
| Use of AI tools (approved) | Yes | See Approved AI Tools list in IT portal; data handling rules apply |

### Bring Your Own Device (BYOD)

Personal devices may access Contoso email and Teams under the following conditions:

| Requirement | Details |
|---|---|
| MDM enrollment | Device must be enrolled in Contoso MDM (Intune) before accessing any Contoso data |
| OS version | Must be within 2 major versions of the current OS release |
| Screen lock | 5-minute auto-lock with PIN or biometric required |
| Remote wipe consent | Employee consents to remote wipe of company data partition in the MDM enrollment agreement |
| Contoso data isolation | Contoso data must remain in managed apps; personal apps cannot access Contoso data |

---

## Prohibited Uses

The following activities are prohibited on all Contoso systems and resources:

### Security-Related Prohibitions

| Prohibited Activity | Consequence Level |
|---|---|
| Installing unauthorized software or applications | Level 3 - Serious |
| Disabling, bypassing, or tampering with security controls (antivirus, EDR, firewall) | Level 4 - Gross Misconduct |
| Sharing login credentials with any other person, including colleagues | Level 3 - Serious |
| Accessing systems or data beyond authorized scope | Level 3 - Serious |
| Connecting unauthorized devices to the Contoso network | Level 2 - Moderate |
| Using personal cloud storage (Google Drive, Dropbox) to store company data | Level 3 - Serious |
| Transmitting Restricted data via unencrypted channels | Level 4 - Gross Misconduct |
| Attempting to probe, scan, or exploit any network or system | Level 4 - Gross Misconduct |
| Using unapproved AI tools to process Confidential or Restricted data | Level 3 - Serious |

### Behavioral Prohibitions

| Prohibited Activity | Consequence Level |
|---|---|
| Sending or forwarding harassing, threatening, or offensive content | Level 3 or 4 depending on severity |
| Using company email for personal business ventures | Level 2 - Moderate |
| Bulk commercial email distribution (spam) using Contoso infrastructure | Level 4 - Gross Misconduct |
| Accessing, downloading, or distributing inappropriate or illegal content | Level 4 - Gross Misconduct |
| Pirating software or using unlicensed software on company systems | Level 3 - Serious |
| Misrepresenting identity or impersonating another employee | Level 4 - Gross Misconduct |
| Mining cryptocurrency using company resources | Level 3 - Serious |

### AI Tool Usage Prohibitions

| Prohibited Activity | Reason |
|---|---|
| Entering customer PII into any AI tool not approved and configured for PII handling | Data privacy violation |
| Entering source code or proprietary algorithms into non-approved AI tools | IP protection |
| Using AI-generated content without human review for customer-facing communications | Quality and accuracy risk |
| Using personal AI subscriptions to process Confidential or Restricted company data | Data leakage risk |

Approved AI tools are listed in the IT portal. Tools not on the approved list must go through the IT vendor review process before use.

---

## Internet and Network Usage

### Permitted Website Categories

| Category | Permitted | Notes |
|---|---|---|
| Business productivity and collaboration | Yes | |
| News and general information | Yes | Reasonable personal use |
| Professional development and learning | Yes | |
| Social media - personal | Limited | During break times; not to interfere with work |
| Streaming video - personal | During break times only | High bandwidth; not during peak hours |

### Blocked Categories

The following categories are blocked by the Contoso web filter at the network level:

- Adult content and pornography
- Gambling
- Malware distribution sites and known phishing domains
- Hacking tools and exploit sites
- Proxy bypass tools and anonymizers
- Unauthorized file sharing and torrent sites

If a legitimate business site is incorrectly blocked, submit an unblock request to IT via the portal.

---

## Email and Communication Standards

- Company email is the property of Contoso and may be monitored in accordance with applicable law
- Employees should have no expectation of privacy when using Contoso communication systems
- Auto-forwarding of company email to external personal accounts is prohibited
- Bulk internal communication (distribution lists) requires manager approval for groups over 100 recipients

---

## Monitoring and Audit

Contoso reserves the right to monitor system activity, network traffic, and device usage on all company-owned or company-managed systems. Monitoring activities include but are not limited to:

| Activity | Purpose |
|---|---|
| Network traffic analysis | Detecting malware, data exfiltration, policy violations |
| Endpoint activity logging | Investigating security incidents |
| Email and Teams message metadata | Compliance audits; not content by default |
| Web browsing logs | Policy compliance; productivity |
| DLP policy enforcement | Preventing data loss on Confidential and Restricted content |

Monitoring is conducted in accordance with local employment law and privacy regulations. Employees are informed of monitoring through this policy and the employment agreement.

---

## Reporting

Employees who suspect a policy violation, security incident, or inappropriate use of company systems must report it immediately to:

| Channel | Contact | Use For |
|---|---|---|
| IT Security Incident portal | it-security@contoso.com | Security incidents, suspected malware, data breach |
| IT Help Desk | Internal portal or x4357 | General IT issues, unauthorized software requests |
| Ethics Hotline | 1-800-CON-ETHI | Anonymous reports of serious violations |

---

## Consequences of Violation

Violations of this policy are subject to the disciplinary framework in HR-001. Consequence levels referenced in the prohibited use tables correspond to:

- **Level 2 - Moderate:** Written warning; possible revocation of specific system access
- **Level 3 - Serious:** Final written warning; suspension; revocation of access; escalation to Legal
- **Level 4 - Gross Misconduct:** Immediate suspension pending investigation; termination; potential criminal referral

---

## Related Documents

- IT-001: Data Classification Policy
- IT-003: Vendor Onboarding Security Requirements
- HR-001: Employee Code of Conduct
- HR-002v2: Remote Work Policy

---

*Questions about permitted or prohibited activities? Contact it-security@contoso.com before acting.*
