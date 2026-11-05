# Evidence Reference Index

**Organisation:** CloudNative Analytics Ltd
**Prepared By:** Taimur Ijlal — GRC Analyst
**Date:** 2026-11-07

This index catalogues all evidence referenced in the Statement of Applicability. Each evidence item is assigned a unique reference code, a description of what it contains, where it is stored, who is responsible for maintaining it, and how often it is updated. The purpose is to ensure that during an audit, any referenced evidence can be located and produced promptly.

---

## Evidence Naming Convention

Format: `[CATEGORY]-[NUMBER]`

| Category Code | Domain |
|---------------|--------|
| POL | Policies |
| ORG | Organisational / Governance |
| IAM | Identity and Access Management |
| HR | Human Resources |
| TRN | Training |
| AST | Asset Management |
| SUP | Supplier Management |
| INC | Incident Management |
| BCP | Business Continuity |
| DEV | Development / SDLC |
| SEC | Security Operations |
| NET | Network Security |
| MDM | Mobile Device Management / Endpoints |
| LOG | Logging and Monitoring |
| MON | Monitoring |
| CLD | Cloud Security |
| DLP | Data Loss Prevention |
| VUL | Vulnerability Management |
| CFG | Configuration Management |
| BAK | Backup |
| FOR | Forensics |
| CRY | Cryptography |
| DM | Data Masking |
| REC | Records Management |
| LEG | Legal |
| PRI | Privacy |
| AUD | Audit |
| OPS | Operations |
| ENV | Environment Separation |
| ARCH | Architecture |
| CHG | Change Management |
| EXT | External Engagement |
| MGT | Management |
| TI | Threat Intelligence |

---

## Full Evidence Register

| Evidence Ref | Description | Storage Location | Owner | Update Frequency | Controls Supported |
|-------------|-------------|-----------------|-------|-----------------|-------------------|
| POL-001 | Information Security Policy (approved, version-controlled) | Google Drive / Policies folder | CISO | Annual review | 5.1 |
| POL-002 | Acceptable Use Policy (signed by all employees) | Google Drive / Policies folder | CISO | Annual review | 5.10, 7.7 |
| POL-003 | Data Classification Policy | Google Drive / Policies folder | CISO | Annual review | 5.12 |
| POL-004 | Remote Working Policy | Google Drive / Policies folder | CISO + HR | Annual review | 6.7, 7.9 |
| POL-005 | Media Handling Policy | Google Drive / Policies folder | CISO | Annual review | 7.10 |
| ORG-001 | RACI matrix for information security responsibilities | Confluence / Security space | CISO | Quarterly | 5.2 |
| MGT-001 | Management review meeting minutes | Google Drive / Management folder | CISO | Quarterly | 5.4 |
| IAM-001 | AWS IAM policy exports | AWS Config / S3 archive | Platform Engineering Lead | Real-time (Config) | 5.3 |
| IAM-002 | Okta configuration and RBAC setup | Okta admin console | IT Manager | On change | 5.15 |
| IAM-003 | Okta user provisioning configuration and JML process | Confluence / IT space | IT Manager | On change | 5.16 |
| IAM-004 | Okta password policy and MFA enrollment report | Okta admin console | IT Manager | Monthly report | 5.17, 8.5 |
| IAM-005 | Privileged access register and quarterly review records | Google Sheet (restricted) | CISO | Quarterly | 5.18, 8.2 |
| IAM-006 | Application RBAC matrix and break-glass procedure | Confluence / Security space | Engineering Manager | On change | 8.3 |
| IAM-007 | Privileged utility tool access list and break-glass logs | Confluence + CloudTrail | CISO | On change | 8.18 |
| HR-001 | Offboarding checklist, MDM wipe confirmations, shipping records | BambooHR / Offboarding folder | HR Manager | Per event | 5.11, 6.5 |
| HR-002 | Screening policy and background check records (redacted) | BambooHR / Compliance folder | HR Manager | Per hire | 6.1 |
| HR-003 | Employment contract template (security clauses highlighted) | Google Drive / HR folder | HR Manager + Legal | Annual review | 6.2 |
| HR-004 | Disciplinary policy (information security section) | Google Drive / HR folder | HR Manager | Annual review | 6.4 |
| HR-005 | NDA template and signed NDA register | Google Drive / Legal folder | Legal | Per engagement | 6.6 |
| TRN-001 | LMS completion records, training materials, phishing simulation reports | KnowBe4 / LMS platform | Security Awareness Lead | Annual + quarterly phishing | 6.3 |
| AST-001 | Snipe-IT asset register export | Snipe-IT | IT Manager | Real-time | 5.9, 7.9 |
| SUP-001 | Supplier register, security assessment questionnaires, contract extracts | Google Drive / Procurement | Procurement + GRC | Annual | 5.19 |
| SUP-002 | Contract security schedule template and signed agreements | Google Drive / Legal folder | Legal | Per contract | 5.20 |
| SUP-003 | AWS compliance reports (SOC 2, ISO 27001), sub-processor register | Google Drive / Suppliers folder | GRC Analyst | Annual | 5.21 |
| SUP-004 | Annual supplier review records, CloudWatch config | Google Drive / Suppliers folder | GRC Analyst | Annual | 5.22 |
| CLD-001 | Cloud security architecture document, Security Hub findings, shared responsibility mapping | Confluence / Architecture space | Platform Engineering Lead | Quarterly | 5.23 |
| INC-001 | Authority contact register, incident response plan Section 7 | Confluence / Security space | CISO | Annual review | 5.5 |
| INC-002 | Incident response plan, PagerDuty config, runbooks | Confluence / Security space | CISO | Annual review + post-incident | 5.24 |
| INC-003 | Triage procedure, SIEM alert rules, event classification matrix | Confluence / Security space | Security Operations Lead | Quarterly | 5.25 |
| INC-004 | Tabletop exercise report, PIR records, communication templates | Google Drive / Incidents folder | CISO | Semi-annual exercise | 5.26 |
| INC-005 | PIR action items (Jira), monthly briefing slides, quarterly metrics | Jira + Google Slides | CISO | Per incident + quarterly | 5.27 |
| INC-006 | Security event reporting procedure, Slack channel audit log | Confluence / Security space | Security Operations Lead | Annual review | 6.8 |
| FOR-001 | CloudTrail config, S3 lifecycle policy for evidence preservation | AWS console / Terraform config | Platform Engineering Lead | Annual review | 5.28 |
| BCP-001 | Business continuity plan, failover test records | Google Drive / BCP folder | CISO | Annual review + quarterly test | 5.29 |
| BCP-002 | DR architecture diagram, multi-AZ config, DR and failover test records | Confluence / Architecture space | Platform Engineering Lead | Quarterly test | 5.30, 8.14 |
| LEG-001 | Legal and regulatory register, legal review records | Google Drive / Legal folder | Legal Counsel | Semi-annual | 5.31 |
| LEG-002 | IP assignment agreements, OSS policy, SCA tool config | Google Drive / Legal folder | Legal + Engineering | Annual review | 5.32 |
| REC-001 | Record retention schedule, storage access controls | Confluence / Governance space | GRC Analyst | Annual review | 5.33, 8.10 |
| PRI-001 | GDPR compliance framework, DPIA records, DPA register | Google Drive / Privacy folder | DPO | Per processing change | 5.34 |
| AUD-001 | Pentest report, independent review remediation plan | Google Drive / Audit folder | CISO | Annual | 5.35 |
| AUD-002 | Self-assessment records, AWS Config conformance pack results | Google Drive / Compliance folder | GRC Analyst | Quarterly | 5.36 |
| OPS-001 | Confluence procedure index, procedure review log | Confluence / Operations space | Engineering Manager | Annual review | 5.37 |
| OPS-002 | Auto Scaling config, CloudWatch alarm config, capacity review records | AWS console / Terraform | Platform Engineering Lead | Monthly review | 8.6 |
| EXT-001 | CSA/OWASP/ISACA membership records, threat intel subscription invoices | Google Drive / External folder | CISO | Annual | 5.6 |
| TI-001 | GuardDuty config, NCSC subscription confirmation | AWS console + email | Security Operations Lead | Real-time | 5.7 |
| DEV-001 | SDLC documentation, threat model templates, Jira workflow config | Confluence / Engineering space | Engineering Manager | Annual review | 5.8, 8.25 |
| DEV-002 | GitHub access audit, branch protection config, Dependabot reports | GitHub Enterprise | Engineering Manager | Monthly audit | 8.4 |
| DEV-003 | CI/CD pipeline config (GitHub Actions) | GitHub Enterprise | Engineering Manager | On change | 8.19 |
| DEV-004 | Security requirements template, test case mappings | Confluence / Engineering space | Engineering Manager | Per release | 8.26 |
| DEV-005 | Secure coding guidelines, Semgrep/Dependabot configs, training records | Confluence + GitHub | Engineering Manager | Annual review | 8.28 |
| DEV-006 | Security test reports, pentest report, regression test suite | Google Drive / Audit folder | CISO + Engineering Manager | Per release + annual | 8.29 |
| DEV-007 | Test data generation procedure, environment audit records | Confluence / Engineering space | Engineering Manager | Annual review | 8.33 |
| ENV-001 | AWS account structure, IAM cross-account policies, synthetic data config | AWS console / Terraform | Platform Engineering Lead | On change | 8.31 |
| ARCH-001 | Architecture principles document, review board minutes | Confluence / Architecture space | CTO | Quarterly | 8.27 |
| CHG-001 | PR approval records, CAB minutes, emergency change log | GitHub + Google Drive | Engineering Manager | Per change | 8.32 |
| MDM-001 | MDM screen lock policy configuration | Jamf / Intune admin console | IT Manager | On change | 7.7, 8.1 |
| MDM-002 | Full MDM configuration (encryption, patching, app control) | Jamf / Intune admin console | IT Manager | On change | 7.9, 8.1 |
| MDM-003 | USB restriction configuration | Jamf / Intune admin console | IT Manager | On change | 7.10 |
| SEC-001 | CrowdStrike Falcon deployment report and GuardDuty config | CrowdStrike console + AWS | Security Operations Lead | Real-time | 8.7 |
| VUL-001 | Qualys scan reports, SLA compliance metrics, remediation records | Qualys console + Jira | Security Operations Lead | Weekly scan | 8.8 |
| CFG-001 | Terraform repos, AWS Config conformance pack results, drift remediation records | GitHub + AWS Config | Platform Engineering Lead | Real-time detection | 8.9 |
| DM-001 | Data masking config, anonymisation procedure | Confluence / Data space | Data Engineering Lead | On change | 8.11 |
| DLP-001 | Google Workspace DLP rules, CrowdStrike DLP config | Google admin + CrowdStrike console | Security Operations Lead | Quarterly review | 5.13, 8.12 |
| NET-001 | TLS configuration, API documentation, DLP rule set | Terraform + Confluence | Platform Engineering Lead | On change | 5.14 |
| NET-002 | VPC architecture diagram, security group rules, VPN config | Terraform + Confluence | Platform Engineering Lead | On change | 8.20 |
| NET-003 | ALB/WAF config, TLS policy, Shield config | Terraform / AWS console | Platform Engineering Lead | On change | 8.21 |
| NET-004 | VPC architecture, peering/routing config, subnet configuration | Terraform | Platform Engineering Lead | On change | 8.22 |
| NET-005 | Cloudflare Gateway config, block lists | Cloudflare dashboard | IT Manager | Monthly review | 8.23 |
| LOG-001 | CloudTrail config, Datadog log pipeline config, S3 retention policy | AWS console + Datadog | Platform Engineering Lead | On change | 8.15 |
| LOG-002 | NTP config verification, log timestamp consistency check | Terraform + monitoring | Platform Engineering Lead | Quarterly check | 8.17 |
| MON-001 | Datadog dashboard config, Security Hub config, review records | Datadog + AWS console | Security Operations Lead | Daily review | 8.16 |
| CRY-001 | TLS config, KMS key inventory, encryption verification records | Terraform + AWS console | Platform Engineering Lead | Annual review | 8.24 |
| BAK-001 | RDS backup config, S3 replication config, restoration test records | AWS console / Terraform | Platform Engineering Lead | Quarterly test | 8.13 |

---

## Evidence Collection Notes for Auditors

1. **Automated evidence** (AWS Config, Okta, CrowdStrike, Datadog) can be exported on demand during audit
2. **Policy documents** are version-controlled in Google Drive with edit history
3. **Meeting minutes and review records** are stored in Google Drive with restricted access
4. **Technical configurations** are stored as code in Terraform repositories (GitHub Enterprise) with full commit history
5. **Evidence is never fabricated or backdated** — if evidence does not exist for a control, the SoA reflects this as "Partial" or "Planned" status

---

## Evidence Gaps (Acknowledged)

| Evidence Ref | Gap Description | Remediation Plan | Target Date |
|-------------|----------------|-----------------|-------------|
| DLP-REM-001 | No DLP evidence for developer tools | Extend DLP programme | Q2 2027 |
| DM-REM-001 | Anonymisation validation incomplete | Engage privacy engineer for validation | Q1 2027 |
| EV-REM-001 | No formal evidence handling procedure | Draft digital forensics SoP | Q1 2027 |
| IR-REM-001 | No independent ISMS audit yet | Schedule pre-certification audit | Q1 2027 |
| LBL-REM-001 | Information labelling incomplete on internal wikis | Extend DLP labels to Confluence | Q1 2027 |
| RW-REM-001 | Remote working environment self-certification only | Evaluate remote environment assessment options | Q2 2027 |
| SC-REM-001 | SaaS supply chain mapping incomplete | Complete non-critical tool inventory | Q1 2027 |
| SM-REM-001 | No automated supplier posture monitoring | Integrate security ratings platform | Q2 2027 |
| TI-REM-001 | No formal threat intelligence programme | Establish structured process | Q1 2027 |
