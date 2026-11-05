# Risk-to-Control Traceability Matrix

**Organisation:** CloudNative Analytics Ltd
**Prepared By:** Taimur Ijlal — GRC Analyst
**Date:** 2026-11-07

This document maps every identified risk from the risk assessment to the specific Annex A controls that address it. The purpose is twofold: to demonstrate that no identified risk is left unaddressed, and to show which controls are doing the heaviest lifting so that implementation priority can be justified.

---

## R-001: Unauthorised Access to Customer Data

**Risk Level:** High (Medium Likelihood × High Impact)

| Control Ref | Control Name | How It Addresses This Risk | Status |
|-------------|-------------|---------------------------|--------|
| 5.1 | Policies for information security | Establishes organisational expectations for data protection | Implemented |
| 5.2 | Information security roles and responsibilities | Defines who is accountable for data access decisions | Implemented |
| 5.3 | Segregation of duties | Prevents any single person from having unchecked access to data | Implemented |
| 5.12 | Classification of information | Ensures customer data is identified and handled per its sensitivity | Implemented |
| 5.14 | Information transfer | Ensures data is encrypted in transit and only transferred via approved channels | Implemented |
| 5.15 | Access control | RBAC ensures only authorised roles can access customer data | Implemented |
| 5.16 | Identity management | Unique identities prevent shared access and enable accountability | Implemented |
| 5.17 | Authentication information | MFA and strong passwords prevent credential-based attacks | Implemented |
| 5.18 | Access rights | Quarterly reviews ensure access remains appropriate | Implemented |
| 5.34 | Privacy and protection of PII | GDPR compliance programme protects personal data specifically | Implemented |
| 6.1 | Screening | Background checks reduce insider threat risk | Implemented |
| 6.3 | Information security awareness | Training reduces human error and social engineering risk | Implemented |
| 8.1 | User endpoint devices | Encrypted endpoints prevent data exposure via device theft | Implemented |
| 8.3 | Information access restriction | Application-level controls restrict access to specific data sets | Implemented |
| 8.5 | Secure authentication | SSO with MFA provides strong authentication | Implemented |
| 8.12 | Data leakage prevention | DLP rules detect and prevent unauthorised data exfiltration | Partial |
| 8.15 | Logging | Audit trail of all data access for detection and investigation | Implemented |
| 8.20 | Networks security | VPC isolation and security groups restrict network-level access | Implemented |
| 8.24 | Use of cryptography | Encryption at rest and in transit protects data confidentiality | Implemented |

**Coverage Assessment:** This risk has the deepest control coverage (19 controls). The partially implemented DLP (8.12) is the most significant gap — it means data exfiltration via developer tools is not currently detected. This is on the remediation roadmap for Q2 2027.

---

## R-002: Employee Laptop Theft/Loss

**Risk Level:** Medium (Medium Likelihood × Medium Impact)

| Control Ref | Control Name | How It Addresses This Risk | Status |
|-------------|-------------|---------------------------|--------|
| 5.9 | Inventory of information and other associated assets | Asset register enables tracking of all devices | Implemented |
| 5.10 | Acceptable use of information and other associated assets | Defines acceptable device usage and storage | Implemented |
| 5.11 | Return of assets | Ensures devices are returned when employees leave | Implemented |
| 6.7 | Remote working | Guidance on secure device storage at home | Partial |
| 7.7 | Clear desk and clear screen | Screen lock prevents visual exposure if device accessed by others | Implemented |
| 7.9 | Security of assets off-premises | MDM, encryption, and remote wipe for all off-premises devices | Implemented |
| 7.10 | Storage media | USB restrictions prevent data leaving the device to removable media | Implemented |
| 8.1 | User endpoint devices | Full disk encryption means a stolen laptop yields no data | Implemented |
| 8.7 | Protection against malware | CrowdStrike EDR provides visibility even if device is compromised | Implemented |
| 8.23 | Web filtering | DNS filtering reduces risk of drive-by malware that could precede theft | Implemented |

**Coverage Assessment:** Strong coverage. The critical mitigation is full disk encryption (8.1) — a stolen laptop is a hardware loss, not a data loss. The partial implementation of remote working environment assessment (6.7) is a minor gap — we rely on employee self-certification rather than inspection.

---

## R-003: Cloud Misconfiguration

**Risk Level:** Critical (High Likelihood × High Impact)

| Control Ref | Control Name | How It Addresses This Risk | Status |
|-------------|-------------|---------------------------|--------|
| 5.7 | Threat intelligence | Awareness of common cloud attack patterns | Partial |
| 5.8 | Information security in project management | Security review gate prevents insecure deployments | Implemented |
| 5.23 | Information security for use of cloud services | Cloud security architecture and shared responsibility mapping | Implemented |
| 8.2 | Privileged access rights | Restricts who can modify cloud configuration | Implemented |
| 8.4 | Access to source code | Branch protection prevents unauthorised IaC changes | Implemented |
| 8.8 | Management of technical vulnerabilities | Scanning detects misconfigurations | Implemented |
| 8.9 | Configuration management | IaC (Terraform) and AWS Config drift detection | Implemented |
| 8.15 | Logging | CloudTrail logs all configuration changes | Implemented |
| 8.16 | Monitoring activities | Security Hub provides continuous misconfiguration detection | Implemented |
| 8.19 | Installation of software on operational systems | CI/CD-only deployments prevent ad-hoc changes | Implemented |
| 8.20 | Networks security | VPC architecture reduces blast radius of misconfigurations | Implemented |
| 8.22 | Segregation of networks | Environment separation limits impact | Implemented |
| 8.25 | Secure development life cycle | Threat modelling catches design-level misconfiguration risks | Implemented |
| 8.27 | Secure system architecture and engineering principles | Architecture principles prevent insecure-by-design configurations | Implemented |
| 8.31 | Separation of development, test and production environments | Separate AWS accounts prevent staging misconfigurations from affecting production | Implemented |
| 8.32 | Change management | CAB review for infrastructure changes | Implemented |

**Coverage Assessment:** This is the highest-rated risk (Critical) and has proportionately strong coverage (16 controls). The primary defence is the combination of IaC (8.9) and continuous monitoring (8.16) — misconfigurations are either prevented by Terraform or detected by Security Hub within minutes. The gap in formal threat intelligence (5.7) means we may miss emerging cloud attack vectors.

---

## R-004: Insider Threat

**Risk Level:** Medium (Low Likelihood × High Impact)

| Control Ref | Control Name | How It Addresses This Risk | Status |
|-------------|-------------|---------------------------|--------|
| 5.1 | Policies for information security | Sets expectations and consequences | Implemented |
| 5.3 | Segregation of duties | Prevents single-actor abuse | Implemented |
| 5.12 | Classification of information | Limits who sees what based on classification | Implemented |
| 5.13 | Labelling of information | Makes classification visible | Partial |
| 5.15 | Access control | Least privilege limits what an insider can access | Implemented |
| 5.18 | Access rights | Quarterly reviews catch privilege accumulation | Implemented |
| 5.28 | Collection of evidence | Enables investigation after detection | Partial |
| 6.1 | Screening | Pre-employment checks reduce risk | Implemented |
| 6.2 | Terms and conditions of employment | Contractual security obligations | Implemented |
| 6.4 | Disciplinary process | Deterrent effect and consequences for violations | Implemented |
| 6.5 | Responsibilities after termination | Ongoing obligations and prompt access revocation | Implemented |
| 6.6 | Confidentiality or non-disclosure agreements | Legal deterrent and post-employment protection | Implemented |
| 8.2 | Privileged access rights | Limits who has admin access | Implemented |
| 8.3 | Information access restriction | Application-level controls limit data access by role | Implemented |
| 8.11 | Data masking | Reduces exposure in non-production environments | Partial |
| 8.12 | Data leakage prevention | Detects data exfiltration attempts | Partial |
| 8.15 | Logging | Audit trail for investigation | Implemented |

**Coverage Assessment:** Insider threat relies on a combination of prevention (access controls), deterrence (policies, NDAs, disciplinary process), and detection (logging, DLP). The key gap is DLP coverage (8.12) — a determined insider using developer tools could currently exfiltrate data without triggering DLP alerts. This is the same gap identified under R-001 and is prioritised for remediation.

---

## R-005: Third-Party Breach (AWS)

**Risk Level:** High (Low Likelihood × Critical Impact)

| Control Ref | Control Name | How It Addresses This Risk | Status |
|-------------|-------------|---------------------------|--------|
| 5.5 | Contact with authorities | Notification procedures for breach response | Implemented |
| 5.6 | Contact with special interest groups | Industry groups for shared threat intelligence | Implemented |
| 5.7 | Threat intelligence | Awareness of threats targeting cloud providers | Partial |
| 5.19 | Information security in supplier relationships | Supplier security assessment programme | Implemented |
| 5.20 | Addressing information security within supplier agreements | Contractual breach notification obligations | Implemented |
| 5.21 | Managing information security in the ICT supply chain | AWS sub-processor oversight | Partial |
| 5.22 | Monitoring, review and change management of supplier services | Annual supplier review cycle | Partial |
| 5.23 | Information security for use of cloud services | Cloud security architecture and shared responsibility | Implemented |
| 8.13 | Information backup | Cross-region backup enables recovery if AWS region compromised | Implemented |
| 8.14 | Redundancy of information processing facilities | Multi-AZ and DR site in eu-west-2 | Implemented |
| 8.16 | Monitoring activities | Security Hub detects anomalies in AWS environment | Implemented |
| 8.24 | Use of cryptography | Encryption with customer-managed keys means AWS breach doesn't automatically expose data | Implemented |

**Coverage Assessment:** The key insight is that customer-managed KMS keys (8.24) provide a critical layer — even if AWS infrastructure is breached, data encrypted with our keys cannot be decrypted without compromising our key management. The gaps in supply chain monitoring (5.21, 5.22) are being addressed through planned integration with a security ratings platform. The partially implemented threat intelligence (5.7) limits our ability to proactively detect AWS-specific threats.

---

## R-006: Business Continuity Failure

**Risk Level:** Medium (Low Likelihood × High Impact)

| Control Ref | Control Name | How It Addresses This Risk | Status |
|-------------|-------------|---------------------------|--------|
| 5.24 | Information security incident management planning and preparation | Incident response plan includes continuity scenarios | Implemented |
| 5.26 | Response to information security incidents | Tested response procedures | Implemented |
| 5.29 | Information security during disruption | Security controls maintained during disruption | Implemented |
| 5.30 | ICT readiness for business continuity | DR architecture, RTO/RPO defined and tested | Implemented |
| 8.6 | Capacity management | Auto Scaling prevents capacity-related outages | Implemented |
| 8.13 | Information backup | Automated backups with cross-region replication | Implemented |
| 8.14 | Redundancy of information processing facilities | Multi-AZ and multi-region architecture | Implemented |

**Coverage Assessment:** Business continuity is well-covered. The multi-AZ architecture (8.14) is the primary defence, with cross-region DR (8.14 + 8.13) as the secondary defence. The quarterly DR testing provides confidence that failover works. No significant gaps identified.

---

## Coverage Gap Analysis

### Controls Addressing Multiple Risks (Highest Value)

| Control | Risks Addressed | Count |
|---------|----------------|-------|
| 8.15 (Logging) | R-001, R-003, R-004 | 3 |
| 5.15 (Access control) | R-001, R-004 | 2 |
| 8.1 (User endpoint devices) | R-001, R-002 | 2 |
| 8.16 (Monitoring activities) | R-001, R-003, R-005 | 3 |
| 5.3 (Segregation of duties) | R-001, R-004 | 2 |
| 8.12 (Data leakage prevention) | R-001, R-004 | 2 |

### Identified Gaps Requiring Remediation

| Gap | Affected Risks | Remediation | Target Date |
|-----|---------------|-------------|-------------|
| DLP coverage on developer tools (8.12) | R-001, R-004 | Extend DLP to CLI/IDE/terminal | Q2 2027 |
| Formal threat intelligence programme (5.7) | R-001, R-003, R-005 | Establish structured threat intel consumption process | Q1 2027 |
| Supply chain monitoring automation (5.22) | R-005 | Integrate security ratings platform | Q2 2027 |
| Evidence handling procedure (5.28) | R-001, R-004 | Develop formal digital forensics procedure | Q1 2027 |
| Information labelling completion (5.13) | R-001, R-004 | Extend DLP labels to all internal platforms | Q1 2027 |

### Risks with No Coverage Gaps

- **R-002 (Laptop theft/loss):** Fully addressed. Full disk encryption is the critical mitigation.
- **R-006 (Business continuity failure):** Fully addressed. Multi-AZ and DR architecture tested quarterly.
