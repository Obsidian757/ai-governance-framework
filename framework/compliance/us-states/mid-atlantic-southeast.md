# State AI Procurement Policies — Mid-Atlantic and Southeast

*Reference maintained as part of the 12th House AI Governance Framework. Citations dated; state AI policy is moving quickly through 2026. This document is a consultative reference, not a formal compliance opinion.*

---

## Evaluator's Quick Read

If you run procurement for a state agency, a county, a city, or a nonprofit funded through state pass-through dollars in the mid-Atlantic or Southeast, this document maps your state's AI governance regime to the same framework your peers cite: **NIST AI RMF 1.0**. Six states are covered (VA, MD, NC, WV, TN, SC), with primary-source citations and an honest read on which states have binding procurement teeth versus aspirational strategy.

---

## Universal Frame: NIST AI RMF 1.0

Every active state AI policy in the mid-Atlantic / Southeast region cites **NIST AI RMF 1.0** as the governing methodology. Virginia's VITA standards, Maryland's Responsible AI Policy, North Carolina's NCDIT framework, and Tennessee's STS 200-POL-007 all reference NIST AI RMF by name. The four NIST AI RMF functions — **GOVERN, MAP, MEASURE, MANAGE** — are the vocabulary state officials use in vendor reviews and capability statement evaluations.

ISO/IEC 42001 and CMMC are not named in any state AI policy reviewed for this document. The framework uses ISO 42001 as the AIMS implementation scaffolding and NIST AI RMF as the universal vocabulary — not as a certification claim.

---

## Cross-State Critical Facts

- **PRC-origin AI is explicitly banned or administratively prohibited in three of the six states.** Virginia (EO 46, Feb 2025) bans DeepSeek on Commonwealth devices and networks. Tennessee (Gov. Lee, March 6, 2025) bans DeepSeek and Manus on the state network. North Carolina (NCDIT, early 2025) banned DeepSeek administratively. Maryland and South Carolina enforce through procurement review rather than statutory ban.
- **Human-in-the-loop is required for consequential decisions in every active state regime.** No exceptions across VA, MD, NC, TN. Any vendor describing AI as "autonomous" in a benefits, eligibility, or rights-affecting context will be screened out.
- **Maryland is the strictest codified regime.** SB 818 (2024) codifies risk tiers and mandates contractor compliance flow-down on every contract.
- **Tennessee is the most operationally rigorous.** STS AI Review Committee gate plus the Standards Products List for LLM/NLP/LAM tools means vendors clear a real procurement gauntlet before contract.
- **Virginia has strong governance but vetoed statutory teeth.** HB 2094 (High-Risk AI Developer and Deployer Act) passed the legislature in February 2025 and was vetoed March 24, 2025. VITA AI IT Standards plus EO 30 and EO 46 are the operative instruments. The Spanberger administration (took office January 2026) issued a new EO on February 4, 2026 advancing law enforcement AI governance.
- **North Carolina has a new EO 24** (Gov. Stein, September 2, 2025), built on the NCDIT Responsible Use framework (August 2024).
- **West Virginia and South Carolina are task-force / strategy only.** Neither has binding procurement rules yet.

---

## State-by-State Reference

### Virginia

**Primary instruments:**
- **Executive Order 30 (Jan 18, 2024)** — Comprehensive state AI standards. Five directives: VITA Policy Standard, EA-225, Education Guidelines, law enforcement standards, AI Task Force.
- **Executive Order 46 (Feb 11, 2025)** — Bans DeepSeek AI on Commonwealth devices and networks.
- **Spanberger AI EO + Directive (Feb 4, 2026)** — Advances law enforcement AI standards under new administration.
- **VITA EA-225 / VITA AI Policy Standard Rev 3** — Enterprise AI architecture standard and governance policy. All Commonwealth agencies and suppliers must follow. NIST AI RMF is the explicit reference methodology.
- **HB 2094** — Passed February 2025, vetoed March 24, 2025. Not in force. Signals future legislative direction.

**Binding procurement teeth:** Yes — EO 30, VITA Policy Standard, and EA-225 apply to all COV agency procurement. eVA procurement portal is mandatory.

**Framework integration:**
- GOVERN: VITA-aligned AI use policy template and inventory cadence; agency-head approval gate
- MAP: Use-case intake and risk screening aligned to VITA risk-based approach
- MEASURE: Bias / privacy / security testing artifacts tied to EO 30 directives
- MANAGE: Incident response, human-in-the-loop documentation, decision-path logging per EA-225

**See also:** `framework/compliance/virginia/` — dedicated Virginia compliance module.

---

### Maryland

**Primary instruments:**
- **Executive Order 01.01.2024.02 (Jan 8, 2024)** — Gov. Wes Moore's directive on responsible and productive use of AI in Maryland state government.
- **SB 818 — Artificial Intelligence Governance Act of 2024** (signed May 2024) — Codifies inventory and assessment duties. Agencies must require contractors to comply with the State's Responsible AI Policy as a contract term. This is the flow-down.
- **Maryland Responsible AI Policy (DoIT)** — Operational implementation, updated 2025. Risk tiers (high-risk = AI affecting safety, civil liberties, equal opportunity, essential services, or privacy) map directly to NIST AI RMF. Vendors must disclose intended use, data sources, training-data provenance, performance metrics, and known limitations at procurement intake. Bias testing required for high-risk uses.

**Binding procurement teeth:** Yes — SB 818 mandates contractor flow-down.

**Framework integration:**
- GOVERN: Written Responsible AI policy template mirroring DoIT structure; contractor flow-down language
- MAP: High-risk classification screening mirroring SB 818 categories
- MEASURE: Bias-testing protocol and training-data provenance log
- MANAGE: Continuous-monitoring cadence aligned to Maryland conditional-approval pattern (PoC → monitored production)

**Risk tier mapping to framework tiers:**

| Maryland Responsible AI High-Risk Category | Framework Tier |
|---|---|
| AI affecting safety of individuals | T1 (Critical) |
| AI affecting civil liberties or equal opportunity | T1 or T2 (High), depending on automation level |
| AI affecting access to essential government services | T2 (High) |
| AI affecting individual privacy | T2 (High) or T3 (Medium), depending on data sensitivity |
| Administrative / operational AI | T3 (Medium) or T4 (Low) |

---

### North Carolina

**Primary instruments:**
- **Executive Order 24 (Sept 2, 2025)** — "Advancing Trustworthy Artificial Intelligence That Benefits All North Carolinians," signed by Gov. Josh Stein. Named principles: fairness, accountability, transparency, security, privacy, civil liberties protection.
- **NCDIT Responsible Use of Artificial Intelligence Framework (August 2024)** — Still operative as governance baseline. AI Oversight Teams in each agency review vendor AI before deployment. Higher scrutiny for AI affecting benefits / eligibility decisions.
- **PRC-origin AI ban (administrative)** — NCDIT banned DeepSeek on state devices, early 2025.
- **Public records exposure** — NCDIT treats data sent to public generative AI tools as "released to the public" and subject to public records law.

**Binding procurement teeth:** Partial — EO 24 and NCDIT framework are operative but codification is lighter than MD or TN. AI Oversight Teams provide practical procurement gatekeeping.

**Framework integration:**
- GOVERN: Agency-level AI use policy plus NCDIT public-records risk advisory in vendor SOPs
- MAP: Use-case intake with benefits / eligibility scrutiny flag; EO 24 named principles cross-check
- MEASURE: Fairness, accountability, transparency, security, privacy, civil-liberties test battery
- MANAGE: Human-in-the-loop documentation for consequential decisions; PRC-origin provenance attestation

---

### Tennessee

**Primary instruments:**
- **STS 200-POL-007 Enterprise AI Policy** (Strategic Technology Solutions, TN Dept. of Finance & Admin.) plus the Enterprise Generative AI Policy.
- **TN AI Advisory Council Action Plan (Nov 17, 2025)** — Statutorily-required annual report; first published Nov 24, 2025.
- **STS AI Review Committee** — All AI procurements and vendor partnerships must clear this committee before contract.
- **Standards Products List** — Vendor LLM/NLP/LAM tools must appear on the list or pass the Standard Product List Exception Process.
- **PRC-origin AI ban** — Gov. Lee banned DeepSeek and Manus on the state network, March 6, 2025.
- **ELVIS Act (effective July 1, 2024)** — Likeness / voice / image protection against generative AI; creates liability exposure for vendors deploying voice/image models in TN.
- **Tennessee Information Protection Act (effective 2025)** — Privacy duties overlay.

**Binding procurement teeth:** Strong — STS AI Review Committee gate + Standards Products List creates a real procurement gauntlet.

**Framework integration:**
- GOVERN: Written AI policy satisfying STS Review Committee intake; Standards Products List exception narrative template
- MAP: Use-case screen with safety / security / accountability pillar mapping (Action Plan language)
- MEASURE: Vendor disclosure pack (model behavior, data flows, limitations) tuned to STS review format
- MANAGE: Citizen-facing AI labeling per Generative AI Policy; human-in-the-loop on consequential decisions; ELVIS Act voice/image safeguards

---

### West Virginia

**Primary instruments:**
- **HB 5690 (2024)** — Created the WV AI Task Force, housed within Office of Technology.
- **HB 3187 (2025)** — Amended WV Code § 5A-6-9; signed by Gov. Patrick Morrisey April 25, 2025, effective July 9, 2025. Moved Task Force into Governor's Office; added economic-opportunity mandate; requires annual reports.

**Binding procurement teeth:** None — no binding state-level procurement rules as of June 2026. Vendors should expect informal due diligence from the Office of Technology.

**Framework integration:** Default to NIST AI RMF baseline plus Task Force aspirational alignment (data privacy, individual rights, model inventory). Position for forthcoming binding rules given the Task Force's annual reporting cadence.

---

### South Carolina

**Primary instruments:**
- **South Carolina State Agencies Artificial Intelligence Strategy** (Department of Administration, 2024). No formal AI executive order as of this writing.
- **Center of Excellence + AI Advisory Group** — First COE meeting February 2025. SC Division of Information Security (DIS) building AI risk management strategy.
- **SC Supreme Court Interim Policy on Generative AI (March 25, 2025)** — Judicial branch only.
- **"Protect, Promote, Pursue" three-pillar strategy** — Calls for statewide acceptable-use policy, AI procurement standards, and sensitive-data protection. Largely aspirational.

**Binding procurement teeth:** None — strategy-level posture only. Expect Center of Excellence ad hoc evaluation rather than a published intake form.

**Framework integration:** NIST AI RMF baseline with strategy-pillar alignment ("Protect, Promote, Pursue") in capability statements.

---

## Cross-State Compliance Matrix

| Requirement | VA | MD | NC | TN | WV | SC |
|---|---|---|---|---|---|---|
| Binding procurement rules | Yes | Yes | Partial | Yes | No | No |
| Executive order on AI | Yes (EO 30 + EO 46 + Spanberger) | Yes | Yes (EO 24) | Policy-level | No | No |
| PRC-origin AI ban (explicit) | Yes (EO 46) | Informal | Informal | Yes | No | No |
| Human-in-the-loop required | Yes | Yes | Yes | Yes | Expected | Expected |
| Vendor flow-down obligations | Yes (VITA std) | Yes (SB 818) | Partial | Yes (STS) | No | No |
| Bias testing required | Implied | Yes (high-risk) | Yes (EO 24) | Yes | No | No |
| Inventory / audit trail required | Yes (Archer/CTP) | Yes | Partial | Yes | No | No |
| Dedicated AI procurement committee | No (eVA/VITA) | No | NCDIT review | Yes (STS committee) | No | No |

---

## Why ISO 42001 Still Matters (Even Though States Don't Name It)

State AI policies tell you **what** to govern: model lineage, risk tiers, bias testing, human-in-the-loop on consequential decisions, vendor disclosures, foreign-AI provenance, inventory cadence. They do not tell you **how** to operationalize those duties as an organization. ISO 42001 provides the AI management system (AIMS) scaffolding — policies, roles, controls, audit trails, continuous-improvement cycles — that turns NIST AI RMF function descriptions into running operational artifacts.

This framework uses ISO 42001 as the AIMS implementation backbone. We are not pursuing organizational ISO 42001 certification and do not make certified claims. The framework gives clients a coherent way to demonstrate to state procurement officers that NIST AI RMF GOVERN / MAP / MEASURE / MANAGE are operational artifacts with named owners, review cadence, and evidence trails — not aspirational language in a capability statement.

---

*Currency note: State AI regimes are evolving rapidly through 2026. Citations reflect published policy as of the dates noted. New EOs, statutes, and agency rules are expected — particularly in Virginia (Spanberger administration), North Carolina (EO 24 implementation), and Maryland (ongoing SB 818 enforcement guidance). Run a primary-source check before relying on this document in a live bid.*
