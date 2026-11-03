# ISO 27001:2022 Statement of Applicability — CloudNative Analytics Ltd

## Project Overview

This project demonstrates a **risk-driven approach** to building an ISO 27001:2022 Statement of Applicability for a fully remote, cloud-native B2B SaaS company. Rather than blindly including all 93 Annex A controls, this SoA makes deliberate exclusion decisions tied to the organisation's risk assessment, business context, and operational reality.

The core skill demonstrated is **judgment**: knowing when a control applies, when it doesn't, and being able to defend that decision under audit scrutiny.

---

## Scenario

| Field | Detail |
|-------|--------|
| **Organisation** | CloudNative Analytics Ltd |
| **Industry** | B2B SaaS — Data Analytics Platform |
| **Employees** | 85 (fully remote) |
| **Infrastructure** | 100% cloud (AWS eu-west-1), no physical data centres |
| **Customers** | 200+ enterprise clients requiring ISO 27001 certification |
| **Goal** | Achieve ISO 27001:2022 certification within 6 months |

### Key Business Context

- No physical offices — remote-first since founding
- All employees use company-managed laptops with MDM
- Customer data processed exclusively in AWS (eu-west-1)
- No mobile app development
- No in-house cryptographic key generation (AWS KMS)
- API-only product (no end-user-facing application)
- No development outsourcing

### Risk Assessment Summary

| Risk ID | Risk Description | Likelihood | Impact | Risk Level |
|---------|-----------------|------------|--------|------------|
| R-001 | Unauthorised access to customer data | Medium | High | High |
| R-002 | Employee laptop theft/loss | Medium | Medium | Medium |
| R-003 | Cloud misconfiguration | High | High | Critical |
| R-004 | Insider threat | Low | High | Medium |
| R-005 | Third-party breach (AWS) | Low | Critical | High |
| R-006 | Business continuity failure | Low | High | Medium |

---

## Deliverables

| # | Deliverable | File |
|---|-------------|------|
| 1 | **Complete Statement of Applicability** (all 93 controls) | [`deliverables/statement-of-applicability.md`](./deliverables/statement-of-applicability.md) |
| 2 | **Exclusion Justifications** (13 controls with full defence) | [`deliverables/exclusion-justifications.md`](./deliverables/exclusion-justifications.md) |
| 3 | **Alternative Measures Mapping** | [`deliverables/alternative-measures.md`](./deliverables/alternative-measures.md) |
| 4 | **Risk-to-Control Traceability Matrix** | [`deliverables/risk-control-traceability.md`](./deliverables/risk-control-traceability.md) |
| 5 | **Evidence Reference Index** | [`deliverables/evidence-reference-index.md`](./deliverables/evidence-reference-index.md) |
| 6 | **Reflections & Lessons Learned** | [`deliverables/reflections.md`](./deliverables/reflections.md) |
| 7 | **SoA Excel Workbook** (professional format, 6 tabs) | [`deliverables/ISO27001_SoA_CloudNative_Analytics.xlsx`](./deliverables/ISO27001_SoA_CloudNative_Analytics.xlsx) |

### Control Summary

| Theme | Total Controls | Applicable | Excluded | Implemented | Partial | Planned |
|-------|---------------|------------|----------|-------------|---------|---------|
| 5. Organisational | 37 | 37 | 0 | 30 | 5 | 2 |
| 6. People | 8 | 8 | 0 | 6 | 2 | 0 |
| 7. Physical | 14 | 3 | 11 | 3 | 0 | 0 |
| 8. Technological | 34 | 32 | 2 | 25 | 5 | 2 |
| **TOTAL** | **93** | **80** | **13** | **64** | **12** | **4** |

---

## Approach

### What Makes This SoA Different

Most SoA projects mark every control as applicable "to be safe." This project takes the opposite approach — it starts from the risk assessment and business context and works outward:

1. **Risk-first**: Every included control traces back to a specific risk in the register
2. **Honest exclusions**: 13 controls are excluded with documented, defensible justifications
3. **Honest status**: Controls are marked as partially implemented or planned where evidence doesn't yet exist — no aspirational "implemented" labels
4. **Alternative measures**: Where a control is excluded, the SoA shows how the underlying risk is still addressed
5. **Auditor-ready**: Each exclusion includes anticipated auditor questions and prepared responses

### Exclusion Philosophy

ISO 27001:2022 Clause 6.1.3(d) requires organisations to determine which Annex A controls are applicable. The standard explicitly allows exclusion — the requirement is that exclusions are justified and that the justification can demonstrate the risk is either not present or is addressed by alternative means.

Including a control that doesn't apply creates audit debt: the organisation must maintain evidence for a control that serves no security purpose. This wastes resources and undermines credibility when auditors see hollow evidence.

---

## How to Review This Project

1. Start with the **Statement of Applicability** to see the full control-by-control assessment
2. Review the **Exclusion Justifications** to see how each non-applicable control is defended
3. Check the **Risk-to-Control Traceability** to verify every identified risk has coverage
4. Review the **Evidence Reference Index** to see where proof of implementation lives
5. Read the **Reflections** for the reasoning behind the hardest decisions

---

*This project was completed as a portfolio exercise. The organisation and scenario are fictional. All analysis, justifications, and decisions reflect real-world GRC judgment applied to a realistic scenario.*
