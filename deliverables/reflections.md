# Reflections & Lessons Learned

**Prepared By:** Taimur Ijlal — GRC Analyst
**Date:** 2026-11-07

---

## 1. Which exclusion did you find hardest to justify?

**Control 7.5 — Protecting against physical and environmental threats** was the hardest. The instinct is to keep it because environmental threats feel universal — fires and floods don't care if you're cloud-native. But the question isn't "do fires exist?" — it's "does CloudNative Analytics have physical infrastructure that a fire could damage?"

The answer is no. AWS's data centres have fire suppression. Employee laptops are replaceable and encrypted. No company data exists only on a physical device.

The difficulty was distinguishing between *the risk existing in the abstract* and *the risk applying to this specific organisation*. A traditional ISO 27001 approach would include this control "just in case." The risk-driven approach asks: what evidence would I need to show an auditor? I'd need evidence of environmental controls over facilities I don't have. That's audit debt with no security benefit.

I kept returning to the scenario where an employee's house floods and destroys their laptop. But that's not an information security event — it's an asset replacement event. The data was encrypted, backed up to the cloud, and recoverable within hours on a new device. Including 7.5 wouldn't change that outcome.

---

## 2. What control inclusion surprised you — thought you could exclude but couldn't?

**Control 7.7 — Clear desk and clear screen.** My initial reaction was to exclude it as a physical control that doesn't apply to a company with no offices. "Clear desk" seems inherently about office environments.

But the underlying risk — visual disclosure of information — absolutely applies to remote workers. An employee's screen showing customer data in a home office where family members, visitors, or video call participants can see it is a real risk. The "clear screen" aspect maps directly to auto screen lock, which is enforced via MDM.

I adapted the control rather than excluding it: "clear desk" becomes "no customer data printed or stored on local desktop," and "clear screen" becomes "MDM-enforced 5-minute auto-lock." The control exists in the SoA but the implementation is tailored to the remote context.

This was a good lesson: **the question isn't "does this control's title match our environment?" — it's "does the risk this control addresses exist in our environment?"** Titles are misleading. The ISO 27001 controls are risk statements dressed as control descriptions.

**Control 5.6 — Contact with special interest groups** was another surprise. I initially flagged it as a candidate for exclusion because "special interest groups" sounds bureaucratic and low-value. But for a cloud-native company, engagement with CSA, OWASP, and AWS security communities is genuinely how we learn about emerging cloud threats. It directly supports our threat intelligence capability (5.7). Excluding it would have weakened our justification for threat awareness.

---

## 3. How would your SoA change if the company opened one physical office?

This is the most practically important question because it tests whether the SoA is designed for maintainability.

If CloudNative Analytics opened a single physical office (say, a small hub in London for optional hybrid working), the following controls would need to be re-evaluated and likely included:

**Definitely re-include:**
- 7.1 (Physical perimeters) — the office needs a controlled boundary
- 7.2 (Physical entry) — access control system (badge, key, or biometric)
- 7.3 (Securing offices) — rooms for confidential calls, secure storage
- 7.4 (Physical monitoring) — CCTV or at minimum visitor logging

**Likely re-include:**
- 7.5 (Environmental threats) — if the office has any infrastructure (even a network switch or meeting room AV equipment)
- 7.6 (Secure areas) — if any sensitive work is done at the office
- 7.8 (Equipment siting) — for any fixed equipment at the office

**Probably stay excluded:**
- 7.11 (Supporting utilities) — if the office is a hot-desking hub with no critical infrastructure, utility failure means "work from home today" rather than a continuity event
- 7.12 (Cabling security) — unless the office has its own network infrastructure beyond standard ISP broadband
- 7.13, 7.14 (Maintenance, disposal) — unless the office has equipment beyond standard office furniture and consumer-grade networking

The key insight: **opening one optional hybrid office would re-introduce approximately 4-7 controls into scope and create significant new evidence requirements.** This is the real cost of a physical presence that most organisations don't account for when making real estate decisions. A GRC-aware organisation would factor the ongoing cost of maintaining physical security controls (estimated: one additional FTE worth of effort annually) into the decision to open an office.

This also shows why the exclusion justifications include explicit re-evaluation triggers — they're designed so that a change in business context automatically flags which controls need reconsideration.

---

## 4. Where did the risk assessment drive a different decision than your instinct?

**Control 8.34 — Protection of information systems during audit testing.** My instinct was to include it because "of course we should protect production during testing." But the risk assessment revealed that our testing approach never touches production — all penetration testing happens in an isolated staging environment in a separate AWS account.

The risk this control addresses (audit testing disrupting or compromising production) is architecturally eliminated by environment separation (8.31). Including 8.34 would mean I need to produce evidence of "production protection during audit testing" when production is never tested. The evidence would be the pentest scope agreement saying "don't test production" — which is already documented under 8.29.

My instinct said "include everything related to testing." The risk assessment said "the specific risk doesn't exist in your architecture." The risk assessment was right.

The opposite happened with **5.7 — Threat intelligence.** My instinct was that this is a mature-organisation control that a startup could defer. But the risk assessment rated cloud misconfiguration (R-003) as Critical and third-party breach (R-005) as High. The only way to proactively manage these risks — rather than reactively responding to incidents — is through threat intelligence. The risk assessment forced me to include it (as "Partial" rather than "Planned," since we have GuardDuty and NCSC feeds even without a formal programme).

---

## 5. What's the cost of over-including controls (audit debt)?

This is the question that most junior GRC analysts never consider, and it's the one that matters most for the credibility of the SoA.

**Audit debt** is the ongoing cost of maintaining evidence for controls that don't serve a security purpose. For each unnecessarily included control, the organisation must:

1. **Produce evidence** — someone must create, collect, or export evidence demonstrating the control is operating. For physical controls, this might be CCTV footage review logs, visitor registers, environmental monitoring reports.

2. **Maintain the evidence** — evidence must be current, dated, and retrievable. A 6-month-old visitor log for an office that doesn't exist is obviously fiction.

3. **Respond to audit findings** — when an auditor asks for evidence and the control is hollow, one of two things happens: either the organisation fabricates evidence (which is fraud and will eventually be caught), or they receive a nonconformity finding (which undermines confidence in the entire ISMS).

4. **Consume audit time** — every included control is a potential audit topic. Including 11 unnecessary physical controls means 11 potential conversations where the auditor asks "how do you implement physical security perimeters?" and the answer is "well, we don't really, but we included it to be safe." This destroys credibility.

For CloudNative Analytics, including all 11 physical controls would create approximately:
- 11 × 2 hours = 22 hours of evidence production per audit cycle
- 11 × 1 hour = 11 hours of auditor time during certification audit
- An unknowable amount of credibility damage when the auditor sees hollow evidence

More importantly, it signals to the auditor that the organisation doesn't understand its own context. An SoA that includes physical security perimeters for a company with no physical premises tells the auditor: "this person listed controls without thinking about them." That impression colours every subsequent interaction during the audit.

**The strongest signal of GRC competence is knowing what to exclude and being able to defend it.** Auditors respect confidence backed by reasoning. They distrust checkbox compliance backed by nothing.

---

## Additional Observations

### On the difference between "Not Applicable" and "Not Implemented"

One of the most important distinctions in the SoA is between excluding a control (Not Applicable) and honestly marking one as not yet implemented (Planned). Several controls in this SoA are marked "Partial" or "Planned" — these are controls that *do* apply but where the organisation hasn't yet achieved full implementation.

An immature SoA marks everything as "Implemented" to look good. A mature SoA is honest about gaps. Auditors can work with honest gaps (they lead to improvement plans). They cannot work with false claims of implementation — that's a major nonconformity.

### On the initial estimate versus final count

I initially projected 15 exclusions but ended with 13. Two controls that seemed excludable on first pass turned out to be applicable when I worked through the risk linkage. This is normal and healthy — the detailed analysis should challenge initial assumptions. If every initial estimate survives the detailed assessment unchanged, the analysis wasn't rigorous enough.

### On maintaining the SoA

This SoA is version 1.0. It should be treated as a living document that changes when:
- The business context changes (new office, new product, outsourcing)
- New risks are identified
- Controls move from "Planned" to "Partial" to "Implemented"
- The risk assessment is updated
- An audit finding challenges an inclusion or exclusion

The version history and re-evaluation triggers in the exclusion justifications are designed to make this maintenance tractable rather than ad-hoc.
