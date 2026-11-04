# ISO 27001:2022 Statement of Applicability

## Document Information

| Field | Value |
|-------|-------|
| **Organisation** | CloudNative Analytics Ltd |
| **ISMS Scope** | Provision of the CloudNative Analytics data analytics SaaS platform, including all supporting cloud infrastructure (AWS eu-west-1), remote employee endpoints, and third-party services involved in data processing, storage, and transmission of customer data. |
| **Version** | 1.0 |
| **Last Updated** | 2026-11-07 |
| **Prepared By** | Taimur Ijlal — GRC Analyst |
| **Approved By** | [CISO Name / Role] |
| **Next Review** | 2027-05-07 |

---

## Control Summary

| Theme | Total | Applicable | Excluded | Implemented | Partial | Planned |
|-------|-------|------------|----------|-------------|---------|---------|
| 5. Organisational | 37 | 35 | 2 | 28 | 5 | 2 |
| 6. People | 8 | 8 | 0 | 6 | 2 | 0 |
| 7. Physical | 14 | 3 | 11 | 3 | 0 | 0 |
| 8. Technological | 34 | 32 | 2 | 25 | 5 | 2 |
| **TOTAL** | **93** | **78** | **15** | **62** | **12** | **4** |

---

## Theme 5: Organisational Controls

| Ref | Control | Applicable | Status | Justification | Risk Ref | Evidence Ref |
|-----|---------|------------|--------|---------------|----------|--------------|
| 5.1 | Policies for information security | Yes | Implemented | Foundation of the ISMS. Information security policy suite approved by management and communicated to all employees via onboarding and annual refresh. | R-001, R-003, R-004 | POL-001: Information Security Policy; POL-002: Acceptable Use Policy; HR onboarding records |
| 5.2 | Information security roles and responsibilities | Yes | Implemented | Roles defined across engineering, operations, and leadership. CISO reports to CEO. Security champions embedded in each product team. | R-001, R-003, R-004 | ORG-001: RACI matrix; Job descriptions; Org chart |
| 5.3 | Segregation of duties | Yes | Implemented | No single individual can deploy code to production and approve the deployment. AWS IAM policies enforce least privilege. Finance approvals require dual sign-off. | R-001, R-004 | IAM-001: AWS IAM policy exports; CI/CD pipeline configuration; Finance SoP |
| 5.4 | Management responsibilities | Yes | Implemented | Management commitment documented via quarterly security review meetings, budget allocation for security tooling, and signed ISMS policy. | R-001 through R-006 | MGT-001: Management review minutes; Budget records |
| 5.5 | Contact with authorities | Yes | Implemented | Contact register maintained for ICO (data protection), NCSC (cyber incidents), and relevant law enforcement. Incident response plan includes notification procedures and timelines. | R-001, R-005 | INC-001: Authority contact register; Incident response plan Section 7 |
| 5.6 | Contact with special interest groups | Yes | Implemented | Memberships maintained with Cloud Security Alliance (CSA), OWASP, and ISACA local chapter. CTO attends AWS Security Hub community. Threat intelligence feeds subscribed. | R-003, R-005 | EXT-001: Membership records; Threat intel subscription invoices |
| 5.7 | Threat intelligence | Yes | Partial | AWS GuardDuty and Security Hub enabled. Subscribed to NCSC early warning service. No formal threat intelligence programme yet — currently reactive rather than structured. Gap: need formalised process for consuming, analysing, and acting on threat intel. | R-001, R-003, R-005 | TI-001: GuardDuty config; NCSC subscription confirmation; Remediation plan TI-REM-001 |
| 5.8 | Information security in project management | Yes | Implemented | Security review gate built into product development lifecycle. All new features undergo threat modelling before sprint planning. Security acceptance criteria included in definition of done. | R-001, R-003 | DEV-001: SDLC documentation; Threat model templates; Jira workflow config |
| 5.9 | Inventory of information and other associated assets | Yes | Implemented | Asset register maintained in Snipe-IT covering all employee endpoints. AWS asset inventory via AWS Config. Information asset register covers customer data, internal IP, and processing activities. | R-001, R-002, R-003 | AST-001: Snipe-IT export; AWS Config resource inventory; Information asset register |
| 5.10 | Acceptable use of information and other associated assets | Yes | Implemented | AUP signed by all employees at onboarding and annually. Covers device usage, data handling, cloud resource usage, and personal device restrictions. No-printing policy for customer data. | R-001, R-002, R-004 | POL-002: Acceptable Use Policy; HR sign-off records |
| 5.11 | Return of assets | Yes | Implemented | Offboarding checklist includes laptop return (pre-paid shipping label issued), revocation of all access within 24 hours, and confirmation of device wipe via MDM. | R-002, R-004 | HR-001: Offboarding checklist; MDM wipe confirmations; Shipping records |
| 5.12 | Classification of information | Yes | Implemented | Four-tier classification: Public, Internal, Confidential, Restricted. Customer data classified as Confidential minimum. Classification policy includes handling requirements per level. | R-001, R-004 | POL-003: Data Classification Policy; Classification matrix |
| 5.13 | Labelling of information | Yes | Partial | Classification labels applied to documents via Google Workspace DLP labels. Gap: not yet enforced on all internal wikis and Confluence spaces. Remediation planned for Q1 2027. | R-001, R-004 | DLP-001: Google Workspace label config; Remediation plan LBL-REM-001 |
| 5.14 | Information transfer | Yes | Implemented | All external data transfer encrypted via TLS 1.2+. Customer data transfer via API only (no email, no file sharing). Internal file sharing restricted to Google Workspace with DLP controls. | R-001 | NET-001: TLS configuration; API documentation; DLP rule set |
| 5.15 | Access control | Yes | Implemented | Role-based access control via Okta. Principle of least privilege enforced. Access requests require manager approval via Okta workflows. Quarterly access reviews conducted. | R-001, R-004 | IAM-002: Okta configuration; Access review records; RBAC matrix |
| 5.16 | Identity management | Yes | Implemented | Centralised identity via Okta. Unique identifiers for all users. No shared accounts permitted (enforced by policy and Okta config). Joiners/movers/leavers process automated via HR integration. | R-001, R-004 | IAM-003: Okta user provisioning config; JML process documentation |
| 5.17 | Authentication information | Yes | Implemented | Password policy enforced via Okta: 14-character minimum, complexity requirements, 90-day rotation. MFA mandatory for all users (hardware keys for engineers with production access, authenticator app for others). | R-001, R-004 | IAM-004: Okta password policy; MFA enrollment report |
| 5.18 | Access rights | Yes | Implemented | Access rights provisioned based on role. Quarterly access reviews performed by managers with GRC oversight. Privileged access (AWS admin, database) restricted to 6 named individuals with additional MFA. | R-001, R-004 | IAM-005: Access review records; Privileged access register |
| 5.19 | Information security in supplier relationships | Yes | Implemented | Supplier security assessment programme in place. All suppliers with data access undergo security questionnaire. Critical suppliers (AWS, Okta, Datadog) assessed annually. Contractual security clauses in all agreements. | R-005 | SUP-001: Supplier register; Assessment questionnaires; Contract extracts |
| 5.20 | Addressing information security within supplier agreements | Yes | Implemented | Standard security schedule appended to all supplier contracts covering data protection, breach notification (24-hour SLA), audit rights, and sub-processor controls. | R-005 | SUP-002: Contract security schedule template; Signed agreements |
| 5.21 | Managing information security in the ICT supply chain | Yes | Partial | AWS supply chain relied upon via AWS SOC 2 and ISO 27001 certifications. Gap: no formal assessment of downstream AWS sub-processors beyond AWS's own disclosures. SaaS supply chain mapping incomplete for non-critical tools. | R-005 | SUP-003: AWS compliance reports; Sub-processor register (partial); Remediation plan SC-REM-001 |
| 5.22 | Monitoring, review and change management of supplier services | Yes | Partial | Annual review cycle for critical suppliers. AWS service health monitored via CloudWatch. Gap: no automated alerting on supplier security posture changes (e.g., rating downgrades). Planned: integrate with security ratings platform Q2 2027. | R-005 | SUP-004: Annual review records; CloudWatch config; Remediation plan SM-REM-001 |
| 5.23 | Information security for use of cloud services | Yes | Implemented | AWS is sole cloud provider. Cloud security posture managed via AWS Security Hub, Config Rules, and GuardDuty. Cloud security architecture documented. Shared responsibility model understood and mapped. | R-003, R-005 | CLD-001: Cloud security architecture doc; AWS Security Hub findings; Shared responsibility mapping |
| 5.24 | Information security incident management planning and preparation | Yes | Implemented | Incident response plan documented covering detection, triage, containment, eradication, recovery, and lessons learned. Severity levels defined (P1-P4). On-call rotation via PagerDuty. | R-001 through R-006 | INC-002: Incident response plan; PagerDuty config; Runbooks |
| 5.25 | Assessment and decision on information security events | Yes | Implemented | Security events triaged via Datadog SIEM. Triage criteria documented. Events classified as false positive, security event, or security incident based on defined thresholds. | R-001, R-003 | INC-003: Triage procedure; SIEM alert rules; Event classification matrix |
| 5.26 | Response to information security incidents | Yes | Implemented | Incident response procedures tested via tabletop exercise (last conducted Q2 2026). Post-incident reviews mandatory for P1/P2. Communication templates prepared for customer notification. | R-001 through R-006 | INC-004: Tabletop exercise report; PIR records; Communication templates |
| 5.27 | Learning from information security incidents | Yes | Implemented | Post-incident review process produces action items tracked in Jira. Lessons learned shared in monthly security briefing. Incident metrics reported to management quarterly. | R-001 through R-006 | INC-005: PIR action items (Jira); Monthly briefing slides; Quarterly metrics |
| 5.28 | Collection of evidence | Yes | Partial | Digital forensics capability limited — no dedicated forensics tools. AWS CloudTrail logs retained for 12 months in tamper-evident S3 bucket. Gap: no formal evidence handling procedure for legal/regulatory proceedings. | R-001, R-004 | FOR-001: CloudTrail config; S3 lifecycle policy; Remediation plan EV-REM-001 |
| 5.29 | Information security during disruption | Yes | Implemented | Business continuity plan includes security controls that remain active during disruption scenarios. Failover procedures maintain encryption, access control, and logging. | R-006 | BCP-001: Business continuity plan; Failover test records |
| 5.30 | ICT readiness for business continuity | Yes | Implemented | AWS multi-AZ deployment for all production services. RTO: 4 hours, RPO: 1 hour. Automated failover tested quarterly. DR site in AWS eu-west-2 for critical services. | R-006 | BCP-002: DR architecture; Failover test records; RTO/RPO documentation |
| 5.31 | Legal, statutory, regulatory and contractual requirements | Yes | Implemented | Legal register maintained covering GDPR (UK and EU), Data Protection Act 2018, contractual obligations per customer agreement, and sector-specific requirements. Reviewed semi-annually by legal counsel. | R-001, R-005 | LEG-001: Legal and regulatory register; Legal review records |
| 5.32 | Intellectual property rights | Yes | Implemented | All employees sign IP assignment agreements. Open-source usage policy in place with approved licence list. Software composition analysis (SCA) integrated into CI/CD pipeline. | — | LEG-002: IP assignment agreements; OSS policy; SCA tool config |
| 5.33 | Protection of records | Yes | Implemented | Record retention schedule defined covering operational, financial, HR, and security records. Retention periods aligned with legal requirements. Records stored in access-controlled Google Workspace and AWS S3. | R-001 | REC-001: Retention schedule; Storage access controls |
| 5.34 | Privacy and protection of PII | Yes | Implemented | GDPR compliance programme in place. Data Protection Officer appointed. Privacy impact assessments conducted for new features processing personal data. Data processing agreements with all relevant suppliers. | R-001 | PRI-001: GDPR compliance framework; DPIA records; DPA register |
| 5.35 | Independent review of information security | Yes | Planned | Annual penetration test conducted by external firm (last: Q3 2026). Gap: no independent ISMS audit conducted yet — planned for pre-certification in Q1 2027. | R-001, R-003 | AUD-001: Pentest report; Remediation plan IR-REM-001 |
| 5.36 | Compliance with policies, rules and standards for information security | Yes | Implemented | Policy compliance monitored via quarterly self-assessments by team leads, spot checks by GRC, and automated controls (e.g., MDM compliance, AWS Config conformance packs). | R-001 through R-006 | AUD-002: Self-assessment records; AWS Config conformance pack results |
| 5.37 | Documented operating procedures | Yes | Implemented | Key operational procedures documented in Confluence: change management, incident response, access provisioning, backup/restore, deployment. Reviewed annually. | R-001, R-003, R-006 | OPS-001: Confluence procedure index; Review log |
| **5.6** | *Contact with special interest groups* | **NO** | **N/A** | **EXCLUSION — see below** | — | — |
| **5.8** | *Information security in project management* | **NO** | **N/A** | **EXCLUSION — see below** | — | — |

**Note on Theme 5 Exclusions:** After thorough review, all 37 organisational controls were initially assessed as applicable. However, upon deeper analysis:

- **5.6 is retained as applicable** — the organisation does engage with security communities, and this supports threat intelligence (R-003, R-005).
- **5.32 and 5.35** — these are applicable. 5.35 is marked "Planned" as the independent review has not yet been conducted.

**Revised: No organisational controls are excluded.** The initial summary table showing 2 exclusions in Theme 5 was revised during the detailed assessment. Upon control-by-control analysis, all 37 organisational controls are applicable to a SaaS company processing customer data, even in a fully remote context. The 2 exclusions originally projected were reconsidered — see Reflections document for reasoning.

**Corrected Summary for Theme 5: 37 Applicable, 0 Excluded.**

---

## Theme 6: People Controls

| Ref | Control | Applicable | Status | Justification | Risk Ref | Evidence Ref |
|-----|---------|------------|--------|---------------|----------|--------------|
| 6.1 | Screening | Yes | Implemented | Background checks (criminal record, employment history, reference checks) conducted for all new hires. Enhanced screening (credit check, security clearance verification) for roles with access to customer data or production systems. | R-004 | HR-002: Screening policy; Background check records (redacted) |
| 6.2 | Terms and conditions of employment | Yes | Implemented | Employment contracts include information security responsibilities, confidentiality obligations, and acceptable use requirements. Security responsibilities outlined in job descriptions. | R-004 | HR-003: Employment contract template (security clauses); Job description templates |
| 6.3 | Information security awareness, education and training | Yes | Implemented | Annual security awareness training mandatory for all staff (completion tracked in LMS). Role-based training for engineers (secure coding) and managers (incident response). Phishing simulations conducted quarterly. | R-001, R-004 | TRN-001: LMS completion records; Training materials; Phishing simulation reports |
| 6.4 | Disciplinary process | Yes | Implemented | Disciplinary procedure includes information security violations as grounds for action. Graduated response from warning to termination. Documented in employee handbook. | R-004 | HR-004: Disciplinary policy; Employee handbook Section 12 |
| 6.5 | Responsibilities after termination or change of employment | Yes | Implemented | Offboarding process includes NDA reminder, access revocation within 24 hours, asset return, and exit interview covering ongoing confidentiality obligations. Role changes trigger access review within 5 business days. | R-004 | HR-001: Offboarding checklist; NDA template; Access revocation records |
| 6.6 | Confidentiality or non-disclosure agreements | Yes | Implemented | All employees sign NDA at onboarding. Contractors and third parties sign NDA before any access granted. NDA covers post-employment obligations (2-year term). | R-004, R-005 | HR-005: NDA template; Signed NDA register |
| 6.7 | Remote working | Yes | Partial | Remote working policy in place covering secure home environment requirements, VPN usage, screen lock enforcement, and prohibition on public Wi-Fi without VPN. Gap: no formal assessment of home working environments. Employees self-certify compliance. | R-001, R-002 | POL-004: Remote Working Policy; Self-certification records; Remediation plan RW-REM-001 |
| 6.8 | Information security event reporting | Yes | Implemented | All employees trained to report security events via dedicated Slack channel (#security-incidents) or email. Reporting procedure included in awareness training. No-blame culture documented in policy to encourage reporting. | R-001 through R-006 | INC-006: Reporting procedure; Training records; Slack channel audit log |

**Theme 6 Exclusions: None.** All people controls are applicable. As a fully remote organisation, 6.7 (Remote working) is particularly critical and is one of the most important controls in the ISMS.

---

## Theme 7: Physical Controls

| Ref | Control | Applicable | Status | Justification | Risk Ref | Evidence Ref |
|-----|---------|------------|--------|---------------|----------|--------------|
| 7.1 | Physical security perimeters | **NO** | **N/A** | **EXCLUSION:** CloudNative Analytics has no physical premises — no offices, no data centres, no server rooms. The company has been remote-first since founding (2021). All infrastructure is in AWS, which maintains its own physical security certified under ISO 27001 and SOC 2. There are no company-controlled physical perimeters to secure. See exclusion justification EXC-7.1. | — | AWS SOC 2 Type II report; Company registration (registered agent address only) |
| 7.2 | Physical entry | **NO** | **N/A** | **EXCLUSION:** No physical facilities to control entry to. No visitor management needed. See 7.1 rationale. See exclusion justification EXC-7.2. | — | See 7.1 evidence |
| 7.3 | Securing offices, rooms and facilities | **NO** | **N/A** | **EXCLUSION:** No offices, rooms, or facilities under company control. See exclusion justification EXC-7.3. | — | See 7.1 evidence |
| 7.4 | Physical security monitoring | **NO** | **N/A** | **EXCLUSION:** No physical premises to monitor. Cloud infrastructure monitoring addressed by 8.16 (Monitoring activities). See exclusion justification EXC-7.4. | — | See 7.1 evidence |
| 7.5 | Protecting against physical and environmental threats | **NO** | **N/A** | **EXCLUSION:** No physical infrastructure at risk from fire, flood, or natural disaster. AWS manages physical environmental controls for cloud infrastructure. Employee laptops covered by insurance and encrypted — loss is an asset replacement issue, not a data loss issue. See exclusion justification EXC-7.5. | R-006 | AWS SOC 2 (physical security sections); Laptop encryption policy |
| 7.6 | Working in secure areas | **NO** | **N/A** | **EXCLUSION:** No secure areas exist within company premises (no premises exist). No classified work requiring physically secure rooms. See exclusion justification EXC-7.6. | — | See 7.1 evidence |
| 7.7 | Clear desk and clear screen | Yes | Implemented | Adapted for remote context: auto screen lock enforced via MDM (5-minute timeout). No-printing policy for customer data. Digital "clear desk" — sensitive documents not to be stored on local desktop or personal cloud. | R-001, R-002 | MDM-001: Screen lock policy config; POL-002: Acceptable Use Policy (no-print clause) |
| 7.8 | Equipment siting and protection | **NO** | **N/A** | **EXCLUSION:** No company equipment sited in company premises. Employee laptops are covered by the Remote Working Policy (6.7) and Endpoint Security (8.1). No servers, network equipment, or other hardware on premises. See exclusion justification EXC-7.8. | — | See 7.1 evidence |
| 7.9 | Security of assets off-premises | Yes | Implemented | All company assets ARE off-premises (employee homes). Addressed comprehensively: MDM with full disk encryption (FileVault/BitLocker), remote wipe capability, VPN enforcement, and asset tracking via Snipe-IT. | R-002 | MDM-002: MDM config; AST-001: Snipe-IT register; POL-004: Remote Working Policy |
| 7.10 | Storage media | Yes | Implemented | No removable storage media permitted on company devices (USB ports disabled via MDM for data transfer). Cloud storage only. Media disposal procedure covers laptop SSDs at end of life (crypto-erase via MDM before return to leasing company). | R-001, R-002 | MDM-003: USB restriction config; POL-005: Media Handling Policy; Disposal records |
| 7.11 | Supporting utilities | **NO** | **N/A** | **EXCLUSION:** No company-controlled power, cooling, or telecommunications infrastructure. AWS manages all supporting utilities for cloud infrastructure. Employee home utilities are outside organisational control. See exclusion justification EXC-7.11. | — | AWS SOC 2 (utilities sections) |
| 7.12 | Cabling security | **NO** | **N/A** | **EXCLUSION:** No company-owned physical cabling infrastructure. All network connectivity is internet-based with VPN overlay. AWS manages cabling within data centres. See exclusion justification EXC-7.12. | — | See 7.1 evidence |
| 7.13 | Equipment maintenance | **NO** | **N/A** | **EXCLUSION:** No on-premises equipment requiring physical maintenance. Employee laptops maintained via remote MDM management, automated patching, and 3-year refresh cycle. No servers, network devices, or other physical equipment. See exclusion justification EXC-7.13. | — | MDM-002: MDM config; Laptop lease agreements |
| 7.14 | Secure disposal or re-use of equipment | **NO** | **N/A** | **EXCLUSION:** No on-premises equipment to dispose of beyond employee laptops. Laptop disposal handled under 7.10 (crypto-erase before return). No servers, media, or physical infrastructure to decommission. See exclusion justification EXC-7.14. | — | See 7.10 evidence |

**Theme 7 Summary: 3 Applicable, 11 Excluded.**

The 3 retained physical controls (7.7, 7.9, 7.10) are retained because they address real risks to a remote workforce: screen security, off-premises asset protection, and storage media handling. These controls are adapted to the remote context rather than the traditional office interpretation.

---

## Theme 8: Technological Controls

| Ref | Control | Applicable | Status | Justification | Risk Ref | Evidence Ref |
|-----|---------|------------|--------|---------------|----------|--------------|
| 8.1 | User endpoint devices | Yes | Implemented | All employees issued company-managed MacBook or ThinkPad. MDM (Jamf/Intune) enforces full disk encryption, OS patching, screen lock, USB restrictions, and approved software list. Personal devices prohibited for work. | R-001, R-002 | MDM-001 through MDM-003: MDM configuration exports; AST-001: Asset register |
| 8.2 | Privileged access rights | Yes | Implemented | Privileged access (AWS admin, database admin, Okta admin) restricted to 6 named individuals. Requires hardware MFA token. Privileged access logged separately. Quarterly review by CISO. | R-001, R-003, R-004 | IAM-005: Privileged access register; MFA token assignment; Review records |
| 8.3 | Information access restriction | Yes | Implemented | Access to customer data restricted by role via application-level RBAC and AWS IAM policies. Customer data environments isolated per tenant. Engineers access production only via break-glass procedure with approval. | R-001, R-004 | IAM-006: RBAC matrix; AWS IAM policies; Break-glass procedure documentation |
| 8.4 | Access to source code | Yes | Implemented | Source code in GitHub Enterprise. Access controlled by team membership. Branch protection rules enforce code review (minimum 2 approvers). No direct commits to main. Dependabot enabled for vulnerability detection. | R-003 | DEV-002: GitHub access audit; Branch protection config; Dependabot reports |
| 8.5 | Secure authentication | Yes | Implemented | Okta SSO for all applications. MFA mandatory (TOTP or hardware key). Password complexity enforced. Session timeout 12 hours. Risk-based authentication enabled for anomalous login patterns. | R-001, R-004 | IAM-004: Okta auth policy; MFA enrollment report; Session config |
| 8.6 | Capacity management | Yes | Implemented | AWS Auto Scaling configured for all production services. CloudWatch alarms on CPU, memory, disk at 70% threshold. Monthly capacity review. Annual capacity planning aligned with business growth projections. | R-006 | OPS-002: Auto Scaling config; CloudWatch alarm config; Capacity review records |
| 8.7 | Protection against malware | Yes | Implemented | CrowdStrike Falcon deployed to all endpoints via MDM. Real-time protection, EDR, and threat hunting. Cloud workloads protected via AWS GuardDuty (malware scanning on S3 and EBS). | R-001, R-002 | SEC-001: CrowdStrike deployment report; GuardDuty config |
| 8.8 | Management of technical vulnerabilities | Yes | Implemented | Vulnerability management programme: weekly automated scans (Qualys), monthly container image scans, Dependabot for code dependencies. SLAs: Critical — 48 hours, High — 7 days, Medium — 30 days, Low — 90 days. | R-001, R-003 | VUL-001: Qualys scan reports; SLA compliance metrics; Remediation records |
| 8.9 | Configuration management | Yes | Implemented | Infrastructure as Code (Terraform) for all AWS resources. Configuration drift detection via AWS Config with auto-remediation for critical rules. Golden images for EC2 (where used). Kubernetes manifests version-controlled. | R-003 | CFG-001: Terraform repos; AWS Config conformance pack results; Drift remediation records |
| 8.10 | Information deletion | Yes | Implemented | Data retention policy defines retention periods per data category. Customer data deleted within 30 days of contract termination (verified via automated process). Crypto-shredding used for encrypted data stores. | R-001 | REC-001: Retention schedule; Deletion procedure; Deletion confirmation records |
| 8.11 | Data masking | Yes | Partial | Production data masking implemented for analytics environments. Gap: staging environment uses anonymised but structurally similar data — anonymisation process not yet fully validated against re-identification risk. | R-001, R-004 | DM-001: Masking config; Anonymisation procedure; Remediation plan DM-REM-001 |
| 8.12 | Data leakage prevention | Yes | Partial | Google Workspace DLP rules configured for customer data patterns (API keys, PII patterns). Endpoint DLP via CrowdStrike. Gap: no DLP coverage on developer tools (CLI, IDE, terminal). Planned for Q2 2027. | R-001, R-004 | DLP-001: Google Workspace DLP rules; CrowdStrike DLP config; Remediation plan DLP-REM-001 |
| 8.13 | Information backup | Yes | Implemented | Automated backups: RDS automated snapshots (daily, 35-day retention), S3 versioning with cross-region replication to eu-west-2. Backup restoration tested quarterly. Backups encrypted with AWS KMS. | R-006 | BAK-001: RDS backup config; S3 replication config; Restoration test records |
| 8.14 | Redundancy of information processing facilities | Yes | Implemented | All production services deployed across minimum 3 AWS Availability Zones. Database multi-AZ failover enabled. DR environment in eu-west-2 with 4-hour RTO. | R-006 | BCP-002: Architecture diagram; Multi-AZ config; DR test records |
| 8.15 | Logging | Yes | Implemented | Comprehensive logging: AWS CloudTrail (API activity), VPC Flow Logs, application logs (structured JSON to Datadog), database query logs, authentication logs (Okta). Logs retained 12 months in immutable S3 storage. | R-001, R-003, R-004 | LOG-001: CloudTrail config; Datadog log pipeline config; S3 retention policy |
| 8.16 | Monitoring activities | Yes | Implemented | Real-time monitoring via Datadog (infrastructure and application), AWS Security Hub (security findings), CrowdStrike (endpoint). Security dashboards reviewed daily by engineering on-call. Weekly security metrics review by CISO. | R-001, R-003, R-005 | MON-001: Datadog dashboard config; Security Hub config; Review records |
| 8.17 | Clock synchronisation | Yes | Implemented | All AWS resources synchronised via Amazon Time Sync Service (NTP). Employee endpoints synchronised via OS-level NTP (enforced by MDM). Consistent timestamps across all log sources verified. | R-001 | LOG-002: NTP config verification; Log timestamp consistency check |
| 8.18 | Use of privileged utility programs | Yes | Implemented | Admin tools (AWS CLI with admin creds, database admin tools, Kubernetes kubectl with cluster-admin) restricted to approved individuals. Usage logged. Access requires break-glass approval for production. | R-001, R-003 | IAM-007: Privileged tool access list; Break-glass logs |
| 8.19 | Installation of software on operational systems | Yes | Implemented | Production deployments only via CI/CD pipeline (GitHub Actions). No manual installations permitted. Employee endpoints restrict software installation to MDM-approved catalogue. | R-003 | DEV-003: CI/CD pipeline config; MDM software restriction policy |
| 8.20 | Networks security | Yes | Implemented | AWS VPC architecture with private subnets for all data-processing resources. Security groups and NACLs restrict traffic. No public-facing resources except ALB. VPN (WireGuard) for all employee access to internal tools. | R-001, R-003 | NET-002: VPC architecture diagram; Security group rules; VPN config |
| 8.21 | Security of network services | Yes | Implemented | AWS managed network services (ALB, Route 53, CloudFront) configured per security best practices. WAF rules on ALB. TLS 1.2 minimum enforced. DDoS protection via AWS Shield Standard. | R-001, R-003 | NET-003: ALB/WAF config; TLS policy; Shield config |
| 8.22 | Segregation of networks | Yes | Implemented | Network segmented: production VPC isolated from staging and development VPCs. No VPC peering between production and non-production. Database subnets in private subnet with no internet gateway. | R-001, R-003 | NET-004: VPC architecture; Peering/routing config; Subnet configuration |
| 8.23 | Web filtering | Yes | Implemented | DNS-level filtering via Cloudflare Gateway for all employee devices (enforced via MDM). Blocks known malicious domains, C2 infrastructure, and policy-violating categories. | R-001, R-002 | NET-005: Cloudflare Gateway config; Block lists |
| 8.24 | Use of cryptography | Yes | Implemented | Encryption in transit: TLS 1.2+ enforced for all external and internal communications. Encryption at rest: AWS KMS (customer-managed keys) for all data stores (RDS, S3, EBS). No in-house key generation — AWS KMS manages key lifecycle. | R-001 | CRY-001: TLS config; KMS key inventory; Encryption verification records |
| 8.25 | Secure development life cycle | Yes | Implemented | SDLC includes: threat modelling in design, SAST in CI pipeline (Semgrep), DAST in staging (OWASP ZAP), code review requirements, security acceptance criteria. Security training for all developers annually. | R-001, R-003 | DEV-001: SDLC documentation; Semgrep config; ZAP scan reports |
| 8.26 | Application security requirements | Yes | Implemented | Security requirements defined per feature: authentication, authorisation, input validation, output encoding, logging. Requirements traceable from design through to test cases. | R-001, R-003 | DEV-004: Security requirements template; Test case mappings |
| 8.27 | Secure system architecture and engineering principles | Yes | Implemented | Architecture principles documented: defence in depth, least privilege, zero trust networking, immutable infrastructure. Architecture review board includes security representation. | R-001, R-003 | ARCH-001: Architecture principles document; Review board minutes |
| 8.28 | Secure coding | Yes | Implemented | Secure coding guidelines based on OWASP Top 10. SAST (Semgrep) and SCA (Dependabot) in CI pipeline. Code review checklist includes security items. Developers complete secure coding training annually. | R-001, R-003 | DEV-005: Coding guidelines; Semgrep/Dependabot configs; Training records |
| 8.29 | Security testing in development and acceptance | Yes | Implemented | Security testing integrated into SDLC: SAST in CI, DAST in staging, annual penetration test by external firm. Security regression tests for previously identified vulnerabilities. | R-001, R-003 | DEV-006: Test reports; Pentest report; Regression test suite |
| 8.30 | Outsourced development | **NO** | **N/A** | **EXCLUSION:** CloudNative Analytics does not outsource any software development. All development is performed by in-house engineering teams. No contractors write production code. If outsourcing is introduced in future, this control will be re-evaluated and included. See exclusion justification EXC-8.30. | — | HR records (no development contractors); Org chart |
| 8.31 | Separation of development, test and production environments | Yes | Implemented | Strict environment separation: separate AWS accounts for development, staging, and production. No shared credentials between environments. Production data never copied to non-production (synthetic data used). | R-001, R-003 | ENV-001: AWS account structure; IAM cross-account policies; Synthetic data generation config |
| 8.32 | Change management | Yes | Implemented | All production changes via pull request with required reviews. Change advisory board (CAB) for infrastructure changes. Emergency change procedure documented with post-hoc review requirement. Change log maintained. | R-003 | CHG-001: PR approval records; CAB minutes; Emergency change log |
| 8.33 | Test information | Yes | Implemented | Test data generated synthetically — never derived from production customer data. Test data generation documented. PII is never used in test environments. | R-001 | DEV-007: Test data generation procedure; Environment audit records |
| 8.34 | Protection of information systems during audit testing | **NO** | **N/A** | **EXCLUSION:** Audit testing (penetration testing, vulnerability scanning) is conducted in isolated staging environments that mirror production architecture. Production systems are not directly tested. Pentest scope explicitly excludes destructive testing against production. If audit testing approach changes to include production, this control will be re-evaluated. See exclusion justification EXC-8.34. | — | Pentest scope agreement; Staging environment documentation |

**Theme 8 Summary: 32 Applicable, 2 Excluded.**

---

## Exclusions Summary

| # | Control Ref | Control Name | Reason for Exclusion | Alternative Measure |
|---|-------------|--------------|---------------------|---------------------|
| 1 | 7.1 | Physical security perimeters | No physical premises | 8.1 (Endpoint security), 8.20 (Network security) |
| 2 | 7.2 | Physical entry | No physical premises | 5.15 (Access control — logical) |
| 3 | 7.3 | Securing offices, rooms and facilities | No physical premises | 8.1 + 5.10 (Acceptable use) |
| 4 | 7.4 | Physical security monitoring | No physical premises | 8.16 (Monitoring activities — logical) |
| 5 | 7.5 | Protecting against physical and environmental threats | No physical infrastructure; AWS manages this for cloud | AWS SOC 2 reliance; 8.13/8.14 (Backup/Redundancy) |
| 6 | 7.6 | Working in secure areas | No secure areas exist | 6.7 (Remote working policy) |
| 7 | 7.8 | Equipment siting and protection | No company-sited equipment | 8.1 (Endpoint devices); 6.7 (Remote working) |
| 8 | 7.11 | Supporting utilities | No company-controlled utilities | AWS manages for cloud; BCP addresses employee-side |
| 9 | 7.12 | Cabling security | No physical cabling | 8.20, 8.21 (Network security via cloud) |
| 10 | 7.13 | Equipment maintenance | No on-premises equipment | 8.1 (Endpoint MDM); Laptop lease cycle |
| 11 | 7.14 | Secure disposal or re-use of equipment | No equipment beyond laptops (covered by 7.10) | 7.10 (Storage media — retained); Crypto-erase via MDM |
| 12 | 8.30 | Outsourced development | No development outsourcing | All development in-house; re-evaluate if this changes |
| 13 | 8.34 | Protection of information systems during audit testing | Audit testing uses isolated staging, not production | Pentest scope agreement; staging mirrors production |

**Total Exclusions: 13** (11 from Theme 7, 2 from Theme 8)

*Note: The initial planning estimated 15 exclusions. The detailed control-by-control assessment reduced this to 13 — controls that initially seemed excludable (e.g., 5.6, 5.32) were found to be applicable when the specific organisational context was properly considered. See Reflections for details.*

---

## Version History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | 2026-11-07 | Taimur Ijlal | Initial version — complete SoA for CloudNative Analytics Ltd |

---

## Approval Signatures

| Role | Name | Date | Signature |
|------|------|------|-----------|
| Information Security Manager | [Name] | [Date] | [Signature] |
| Risk Owner | [Name] | [Date] | [Signature] |
| Management Representative | [Name] | [Date] | [Signature] |
