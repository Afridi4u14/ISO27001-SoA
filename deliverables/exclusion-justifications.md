# Exclusion Justification Register

**Organisation:** CloudNative Analytics Ltd
**Prepared By:** Taimur Ijlal — GRC Analyst
**Date:** 2026-11-07
**Total Exclusions:** 13

This document provides detailed justification for each control excluded from the Statement of Applicability, including business context, risk assessment linkage, alternative measures, anticipated auditor challenges, and conditions under which the exclusion should be re-evaluated.

---

## EXC-7.1: Physical Security Perimeters (Control 7.1)

### Exclusion Statement
This control is NOT APPLICABLE to CloudNative Analytics Ltd.

### Business Context
CloudNative Analytics has operated as a fully remote organisation since its founding in 2021. The company:
- Has no leased or owned office space
- Has no data centres or co-location facilities
- Is registered via a registered agent address (not an operational facility)
- Has no plans to acquire physical premises within the current strategic planning horizon (3 years)

### Risk Assessment Linkage
The underlying risk this control addresses is **unauthorised physical access to information processing facilities**. In CloudNative Analytics' context:
- All information processing occurs in AWS eu-west-1, where physical security is managed by AWS under their ISO 27001 and SOC 2 certifications
- The only company-owned physical assets are employee laptops, which are addressed by control 8.1 (User endpoint devices)
- No company data is stored in any physical location outside of AWS and encrypted endpoints

### Alternative Controls

| Physical Risk | Alternative Control | How It Addresses the Risk |
|---------------|--------------------| --------------------------|
| Unauthorised access to servers | 8.20 (Network security) + AWS physical controls | VPC isolation, security groups, and AWS's certified physical security programme |
| Unauthorised access to data | 8.3 (Information access restriction) | Logical access controls via Okta RBAC and AWS IAM |
| Theft of equipment | 8.1 (User endpoint devices) | Full disk encryption, MDM remote wipe, VPN-only access |

### Evidence of Non-Applicability
- Companies House registration showing registered agent address only (no operational premises)
- AWS billing records showing 100% cloud infrastructure spend
- HR policy confirming remote-first status (no office attendance expected or possible)
- Asset register showing zero on-premises servers, network equipment, or storage devices

### Anticipated Auditor Questions

**Q: "What about employees' home offices? Aren't those processing facilities?"**
A: Employees' homes are not company-controlled facilities. We cannot and do not control the physical security of private residences. The security of data in home environments is addressed through our endpoint security programme (8.1 — full disk encryption, MDM, remote wipe) and our Remote Working Policy (6.7). We treat the employee endpoint as the security boundary, not the physical location.

**Q: "What if you hire a co-working space for a team event?"**
A: Temporary meeting space is not an information processing facility. Our policies prohibit processing customer data outside of company endpoints and AWS. A co-working space would be used for discussion only — no data processing, no paper documents, no whiteboards with sensitive information. This is covered by our Acceptable Use Policy (5.10).

**Q: "How do you verify AWS's physical security?"**
A: We rely on AWS's independently audited certifications: ISO 27001 (certificate verified annually), SOC 2 Type II report (reviewed annually by our team — Section IV covers physical security), and SOC 3 public report. AWS physical security controls are a key element of our supplier assessment under control 5.19.

### Conditions for Re-evaluation
This exclusion must be re-evaluated if:
- The company opens any physical office, co-working membership, or hotdesking arrangement
- The company begins processing data outside of AWS (e.g., edge computing, on-premises appliances)
- The company acquires physical infrastructure (servers, network equipment, storage)
- Regulatory requirements mandate physical premises

---

## EXC-7.2: Physical Entry (Control 7.2)

### Exclusion Statement
This control is NOT APPLICABLE to CloudNative Analytics Ltd.

### Business Context
This control requires mechanisms to authorise and control physical entry to company premises. Since CloudNative Analytics has no physical premises (see EXC-7.1), there are no entry points to control. There is no visitor management requirement, no access card system, and no reception area.

### Risk Assessment Linkage
The risk of unauthorised physical entry is not present — there are no company facilities to enter. Logical access control (the digital equivalent) is comprehensively addressed by controls 5.15, 5.16, 5.17, and 5.18.

### Alternative Controls
- 5.15 (Access control): Logical access to all systems controlled via Okta RBAC
- 5.16 (Identity management): All identities centrally managed, no shared accounts
- 5.17 (Authentication information): MFA enforced for all access

### Anticipated Auditor Questions

**Q: "If this control is excluded, how do you control who accesses your information?"**
A: Access control is entirely logical. We control *who can access our systems*, not *who can enter a building*. This is addressed by our access control programme (5.15–5.18) which provides more granular control than physical entry ever could — we can enforce per-resource, per-role, time-based access with full audit trails, which physical badge systems cannot match.

### Conditions for Re-evaluation
Same conditions as EXC-7.1.

---

## EXC-7.3: Securing Offices, Rooms and Facilities (Control 7.3)

### Exclusion Statement
This control is NOT APPLICABLE to CloudNative Analytics Ltd.

### Business Context
No offices, rooms, or facilities exist under company control. See EXC-7.1 for full context.

### Risk Assessment Linkage
The risk of unauthorised access to information within offices is addressed through:
- Digital information security (all data in cloud or on encrypted endpoints)
- No-printing policy for customer data (eliminates paper document risk)
- Screen lock enforcement via MDM (prevents visual disclosure)

### Alternative Controls
- 8.1 (User endpoint devices): Encrypted laptops with MDM
- 5.10 (Acceptable use): No-printing policy, digital-only data handling
- 7.7 (Clear desk/screen — retained): Auto screen lock enforced via MDM

### Anticipated Auditor Questions

**Q: "How do you secure sensitive information if there's no secure room?"**
A: Our sensitive information exists in two places: AWS (secured by AWS's physical and logical controls, verified through their SOC 2) and on encrypted employee endpoints (secured by 8.1 and our MDM programme). We have deliberately eliminated the need for physical secure storage by maintaining a no-printing policy and storing all documents digitally. This is actually a stronger security posture than a locked filing cabinet in an office.

### Conditions for Re-evaluation
Same conditions as EXC-7.1.

---

## EXC-7.4: Physical Security Monitoring (Control 7.4)

### Exclusion Statement
This control is NOT APPLICABLE to CloudNative Analytics Ltd.

### Business Context
No company premises exist to monitor. CCTV, motion detection, and guard services are not applicable.

### Alternative Controls
- 8.16 (Monitoring activities): Comprehensive digital monitoring via Datadog, Security Hub, and CrowdStrike provides the logical equivalent — and with far greater coverage and granularity than physical cameras
- 8.15 (Logging): All system access logged with immutable audit trails

### Anticipated Auditor Questions

**Q: "How do you detect unauthorised access without physical monitoring?"**
A: We monitor all access digitally. Every API call is logged (CloudTrail), every authentication attempt is logged (Okta), every endpoint action is monitored (CrowdStrike EDR), and all infrastructure events are captured (Datadog). Digital monitoring provides richer data than CCTV — we know exactly *what* was accessed, not just that someone entered a room.

### Conditions for Re-evaluation
Same conditions as EXC-7.1.

---

## EXC-7.5: Protecting Against Physical and Environmental Threats (Control 7.5)

### Exclusion Statement
This control is NOT APPLICABLE to CloudNative Analytics Ltd.

### Business Context
CloudNative Analytics has no physical infrastructure vulnerable to fire, flood, earthquake, or other environmental threats. AWS manages all environmental controls (fire suppression, cooling, flood protection) for our cloud infrastructure under their SOC 2 programme.

### Risk Assessment Linkage
Risk R-006 (Business continuity failure) is the relevant risk. This is addressed through:
- AWS multi-AZ architecture (resilient to single-facility failure)
- DR environment in separate AWS region (eu-west-2)
- Employee laptop loss is an asset replacement issue — no data loss due to encryption and cloud-only data storage

### Alternative Controls
- AWS SOC 2 physical security controls (verified annually)
- 8.13 (Information backup): Automated backups with cross-region replication
- 8.14 (Redundancy): Multi-AZ deployment, DR site in separate region
- 5.30 (ICT readiness for BC): DR tested quarterly

### Anticipated Auditor Questions

**Q: "What if AWS's eu-west-1 region has a complete failure?"**
A: Our DR plan includes failover to eu-west-2 with a 4-hour RTO. Critical data is replicated cross-region in near real-time (RPO: 1 hour). We test this failover quarterly. A complete regional failure at AWS would affect thousands of customers globally and would be an unprecedented event — but even in that scenario, our data and services can be restored from eu-west-2.

**Q: "What about employee laptops being damaged in a flood or fire?"**
A: Laptop loss is a hardware replacement issue, not a data security issue. All data is in AWS or synced to cloud storage. Laptop drives are encrypted — physical destruction actually secures the data. We can provision a replacement laptop with full access within 24 hours via overnight shipping and MDM auto-enrolment.

### Conditions for Re-evaluation
Same conditions as EXC-7.1, plus: if the company begins processing data on edge devices or IoT hardware that require environmental protection.

---

## EXC-7.6: Working in Secure Areas (Control 7.6)

### Exclusion Statement
This control is NOT APPLICABLE to CloudNative Analytics Ltd.

### Business Context
No secure areas exist within company premises because no company premises exist. There is no classified work requiring physically controlled environments (SCIFs, server rooms, vaults). All "secure" processing happens in AWS, where AWS manages the physical security of the data centre environment.

### Alternative Controls
- 6.7 (Remote working): Defines security requirements for home working environments
- 8.1 (User endpoint devices): Secures the processing device regardless of physical location
- 8.3 (Information access restriction): Logical access controls provide the equivalent of "secure area" restrictions

### Conditions for Re-evaluation
If the company begins handling data with physical security requirements (e.g., government classified data, defence contracts), this control would need to be included with corresponding physical infrastructure.

---

## EXC-7.8: Equipment Siting and Protection (Control 7.8)

### Exclusion Statement
This control is NOT APPLICABLE to CloudNative Analytics Ltd.

### Business Context
No company equipment is sited in company-controlled facilities. The only company equipment is employee laptops, which are at employees' home locations. The siting and protection of these devices is addressed through the endpoint security programme (8.1) and the Remote Working Policy (6.7), which includes guidance on secure device storage at home.

### Alternative Controls
- 8.1 (User endpoint devices): MDM, encryption, remote wipe
- 6.7 (Remote working): Secure home environment guidance
- 7.9 (Security of assets off-premises — retained): Specifically covers off-premises assets

### Conditions for Re-evaluation
Same conditions as EXC-7.1.

---

## EXC-7.11: Supporting Utilities (Control 7.11)

### Exclusion Statement
This control is NOT APPLICABLE to CloudNative Analytics Ltd.

### Business Context
CloudNative Analytics has no company-controlled power supplies, air conditioning, telecommunications, or water supplies. AWS manages all supporting utilities for cloud infrastructure (covered under their SOC 2). Employee home utilities are entirely outside organisational control.

### Alternative Controls
- AWS manages and certifies utility resilience for cloud infrastructure
- 5.30 (ICT readiness for BC): Addresses the risk of employee-side utility failure through the ability to work from any location with internet access (not tied to specific premises)

### Anticipated Auditor Questions

**Q: "What happens if an employee loses power or internet?"**
A: Individual employee utility failures do not affect service availability — the product runs in AWS independent of any employee's home infrastructure. Employees can relocate to any internet-connected location. No single employee's connectivity is a single point of failure. For critical on-call roles, mobile hotspots are provided as backup.

### Conditions for Re-evaluation
Same conditions as EXC-7.1.

---

## EXC-7.12: Cabling Security (Control 7.12)

### Exclusion Statement
This control is NOT APPLICABLE to CloudNative Analytics Ltd.

### Business Context
No company-owned network cabling, patch panels, distribution boards, or telecommunications infrastructure exists. All network connectivity is internet-based (employee home broadband) with VPN overlay (WireGuard). AWS manages all data centre cabling.

### Alternative Controls
- 8.20 (Network security): VPN encryption protects data in transit over untrusted networks
- 8.24 (Cryptography): TLS 1.2+ for all communications ensures eavesdropping on physical cables cannot expose data
- 8.21 (Security of network services): AWS-managed network services with dedicated security controls

### Conditions for Re-evaluation
Same conditions as EXC-7.1.

---

## EXC-7.13: Equipment Maintenance (Control 7.13)

### Exclusion Statement
This control is NOT APPLICABLE to CloudNative Analytics Ltd.

### Business Context
No on-premises servers, network equipment, or infrastructure requires physical maintenance. Employee laptops are maintained remotely via MDM (software updates, patching, configuration management) and replaced on a 3-year lease cycle. Laptops requiring physical repair are returned to the manufacturer under warranty — data is secured via full disk encryption, and the MDM performs a remote wipe before the device is handed to a repair service.

### Alternative Controls
- 8.1 (User endpoint devices): MDM handles remote "maintenance" (patching, updates)
- 7.10 (Storage media — retained): Covers data security during equipment servicing via crypto-erase

### Conditions for Re-evaluation
Same conditions as EXC-7.1.

---

## EXC-7.14: Secure Disposal or Re-use of Equipment (Control 7.14)

### Exclusion Statement
This control is NOT APPLICABLE as a standalone control. The risk of data exposure through equipment disposal is addressed under retained control 7.10 (Storage media).

### Business Context
The only company equipment requiring disposal is employee laptops. The disposal process is:
1. MDM initiates crypto-erase (verified remotely)
2. Device returned to leasing company via tracked courier
3. Leasing company provides certificate of destruction or refurbishment (with certified data wipe)

This is fully covered under control 7.10 (Storage media), which is retained and implemented. Creating a separate control for equipment disposal would duplicate the storage media disposal process without adding security value.

### Alternative Controls
- 7.10 (Storage media — retained and implemented): Covers crypto-erase and disposal verification
- Asset register (5.9): Tracks device lifecycle from provisioning to disposal

### Conditions for Re-evaluation
If the company acquires physical infrastructure beyond employee endpoints (servers, network equipment, specialised hardware), this control should be included separately from 7.10.

---

## EXC-8.30: Outsourced Development (Control 8.30)

### Exclusion Statement
This control is NOT APPLICABLE to CloudNative Analytics Ltd.

### Business Context
CloudNative Analytics does not outsource any software development. All product development is performed by in-house engineering teams (currently 45 engineers across 6 teams). No contractors, consultants, or third-party development firms write production code. Open-source libraries are used but governed by the SCA programme (Dependabot) under control 8.28.

### Risk Assessment Linkage
The risk of insecure third-party code is addressed by:
- Hiring controls (6.1, 6.2): All developers are screened employees
- Secure development lifecycle (8.25): Applies to all in-house development
- Code review requirements (8.28): All code reviewed before merge
- SCA (8.28): Open-source dependencies scanned for vulnerabilities

### Anticipated Auditor Questions

**Q: "What about freelancers or contractors who write code?"**
A: We have no development contractors. Our HR records and GitHub access logs confirm that all code contributors are full-time employees. If we were to engage development contractors in the future, this control would immediately become applicable and we would implement supplier security requirements, code review processes, and contractual security obligations before any external code entered our repositories.

**Q: "What about open-source software — isn't that outsourced development?"**
A: Open-source dependencies are managed through our software composition analysis programme (Dependabot under 8.28). We track all dependencies, scan for known vulnerabilities, and apply updates per our vulnerability management SLAs (8.8). We do not consider open-source usage as "outsourced development" under this control, but the risk is addressed through our existing controls.

### Conditions for Re-evaluation
This exclusion must be re-evaluated immediately if:
- Any development contractor or consultancy is engaged
- Offshore development is considered
- A "code-for-hire" arrangement is entered into
- An acquisition brings in externally developed code

---

## EXC-8.34: Protection of Information Systems During Audit Testing (Control 8.34)

### Exclusion Statement
This control is NOT APPLICABLE in its traditional form to CloudNative Analytics Ltd.

### Business Context
All audit testing (penetration testing, vulnerability scanning) is conducted against our staging environment, which mirrors production architecture but contains no real customer data (synthetic data only). The pentest scope agreement explicitly:
- Excludes destructive testing against any environment
- Restricts testing to staging environment URLs and IP ranges
- Prohibits social engineering of employees without prior HR approval
- Requires advance notification (minimum 5 business days)

Because testing does not touch production systems, the risk of audit testing disrupting or compromising production information systems does not exist in our current testing model.

### Risk Assessment Linkage
The risk this control addresses — audit testing causing harm to production systems — is eliminated by architectural separation. Production and staging run in separate AWS accounts with no cross-account access, no shared credentials, and no network connectivity between them.

### Alternative Controls
- 8.31 (Separation of environments): Strict environment isolation ensures testing cannot affect production
- Pentest scope agreement: Contractual control limiting testing to non-production
- 8.29 (Security testing): Defines testing approach and boundaries

### Anticipated Auditor Questions

**Q: "What if you need to test something that only exists in production?"**
A: Our staging environment mirrors production architecture. If a production-only issue needs investigation, we do so through our monitoring and logging tools (8.15, 8.16) rather than through audit testing. If we ever determine that production penetration testing is necessary, we would include this control, define production testing safeguards, and update the SoA accordingly.

**Q: "Don't your vulnerability scanners hit production?"**
A: Our automated vulnerability scanning (Qualys) runs against staging infrastructure. AWS-native security scanning (Security Hub, Inspector) runs in all environments including production but is non-intrusive — it reads configuration and metadata rather than actively probing systems.

### Conditions for Re-evaluation
This exclusion must be re-evaluated if:
- The decision is made to conduct penetration testing against production systems
- A customer or regulatory requirement mandates production-environment security testing
- The staging environment no longer adequately mirrors production architecture
