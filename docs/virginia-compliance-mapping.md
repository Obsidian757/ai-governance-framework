# Commonwealth of Virginia AI Compliance Framework
## ISO/IEC 42001:2023 ↔ Virginia Executive Order 30 ↔ VITA AI Standards

**Mapping Guide for Vendors, Contractors, and Commonwealth Executive Branch Agencies**

---

## Executive Summary

This document maps **ISO/IEC 42001:2023** (AI Management Systems) to the **Commonwealth of Virginia's** AI governance framework established under [Executive Order 30 (2024)](https://web.archive.org/web/20251220200739/https://www.governor.virginia.gov/media/governorvirginiagov/governor-of-virginia/pdf/eo/EO-30.pdf). It is the Virginia peer to [`federal-compliance-mapping.md`](./federal-compliance-mapping.md).

Specifically it covers:

- **Virginia Executive Order 30 (Youngkin, January 18, 2024)** — directs the standards below.
- **VITA Policy Standard for the Utilization of Artificial Intelligence by the Commonwealth of Virginia** (Rev 3, June 27, 2024).
- **VITA Enterprise Architecture Standard EA-225 — Enterprise Solutions Architecture for Artificial Intelligence** (v1.2, November 16, 2023).
- **Guidelines for AI Integration Throughout Education in Virginia** (Office of the Secretary of Education, 2024) — applicable where a Commonwealth or local education client is in scope.

**Why this matters.** Virginia has stood up a parallel — and in some places stricter — AI compliance regime alongside the federal stack. Any vendor doing business with a Commonwealth executive branch agency (eVA procurement, Commonwealth cooperative master agreements for AI services, or state agency direct contracts) is touched by EO-30. A 12th House AI client that has implemented ISO 42001-aligned controls has already done the majority of the work; this document shows them exactly which existing controls satisfy which Virginia requirement.

**Key insight.** EO-30 plus VITA's standards together impose specific *operational* obligations — agency-head approval before AI is used, registration in the Commonwealth Technology Portfolio (CTP / Planview) and Archer, logged decision paths, monitored model performance, public disclaimers on AI-generated outputs, and ethical-use commitments — that ISO 42001 satisfies through Clauses 5–10 and Annex A. The mapping below pins each Virginia obligation to a specific ISO 42001 control.

---

## Overview of Virginia AI Requirements

### Executive Order 30 (2024): Artificial Intelligence

**Scope:** All Commonwealth of Virginia executive branch agencies; K-12 schools, community colleges, and universities (via Education Guidelines); executive branch law enforcement (via PSHS standards).

**Applicability to vendors/contractors:** **Direct.** Any AI product or service sold to a Commonwealth agency, used inside an agency's operations, or embedded within a third-party SaaS the agency procures, is in scope of the standards EO-30 directs.

**Five directives:**

1. Enactment of **AI Policy Standards** published by VITA (operationalized in the *Utilization of AI by COV Policy Standard*).
2. Enactment of **AI Information Technology Standards** published by VITA (operationalized in **EA-225**).
3. Enactment of **AI Education Guidelines** for K-12 and post-secondary institutions.
4. Establishment of **AI standards for executive branch law enforcement** and **model standards for local law enforcement** (deadline October 2024 — not published by the Youngkin administration; superseded in part by the Spanberger administration's February 4, 2026 EO and Directive).
5. Establishment of an **AI Task Force**.

---

### VITA Policy Standard for the Utilization of AI by the Commonwealth (Rev 3, June 27, 2024)

**Scope:** Commonwealth executive branch agency *use* of AI — covering existing and new AI, stand-alone and embedded AI, generative AI inside other systems, AI developed by the agency or by third parties on the agency's behalf, the data used to train the AI, and the outputs that support decision making. Also covers an agency's **procurement** of AI applications.

**Operative requirements (paraphrased):**

- **Agency-head approval is required before an AI use case is deployed**, with approval recorded in **Archer** and the **Commonwealth Technology Portfolio (CTP) / Planview**.
- **Ethical-use principles** must be observed (fairness, transparency, accountability, human oversight, minimization of harm).
- **Personal data protections** must apply throughout the AI lifecycle.
- **Public-facing AI outputs require disclaimers** indicating that AI was involved.
- **Compliance with Commonwealth security standards** is mandatory.

---

### VITA EA-225: Enterprise Solutions Architecture — AI (v1.2, November 16, 2023)

**Scope:** Technical and architectural controls on COV AI systems and their suppliers.

**Operative requirements (paraphrased — non-exhaustive):**

- COV AI Systems shall conform to **Commonwealth security standards**.
- COV AI System **decision paths shall be logged for traceability and replay**.
- AI **monitoring shall include metrics and thresholds for model performance and accuracy**.
- Standard covers stand-alone, embedded, and generative AI; both internally developed and third-party.
- Applies to data inputs used to train AI and to outputs used in support of decision making.
- Applies to **procurement** of AI applications.

---

### Guidelines for AI Integration Throughout Education in Virginia (2024)

**Scope:** K-12 public schools, the Virginia Community College System (VCCS), and the State Council of Higher Education for Virginia (SCHEV)–covered institutions.

**Operative themes:** Guiding principles, strategies for success, stakeholder roles and responsibilities. Emphasis on human-centered teaching ("education is ultimately a human endeavor"), responsible student use, mitigation of bias and discriminatory outcomes, and student data privacy.

---

## Comprehensive ISO 42001 ↔ Virginia AI Mapping

### ISO 42001 Clause 4 — Context of the Organization

| ISO 42001 Control | EO-30 | VITA Policy Standard | EA-225 | Compliance Notes |
|---|---|---|---|---|
| 4.1 External/internal issues | Preamble — guardrails across state government | Overview — Commonwealth AI landscape | Sec. Purpose — AI scope statement | ISO documents the Virginia regulatory landscape your AI operates in. |
| 4.2 Stakeholder needs | Directive — public, citizens, agencies | Disclaimer / public-facing output requirement | Stakeholder section — agencies and suppliers | ISO stakeholder register should include VITA, agency head, citizens receiving AI outputs. |
| 4.3 Scope of AIMS | Five-directive scope | Coverage of standalone / embedded / GenAI | Scope: existing + new AI, embedded, GenAI | ISO scope statement should explicitly include AI deployed into or for Commonwealth use. |
| 4.4 AIMS establishment | Directives 1–2 (VITA standards) + 5 (AI Task Force) | Establishes COV-wide AI governance | EA-225 enterprise architecture posture | ISO management system satisfies the "uniform guiding principles" EO-30 demands. |

**Compliance level:** ISO 42001 **fully satisfies** the contextualization required by EO-30 and adds documented rigor.

---

### ISO 42001 Clause 5 — Leadership

| ISO 42001 Control | EO-30 | VITA Policy Standard | EA-225 | Compliance Notes |
|---|---|---|---|---|
| 5.1 Leadership commitment | Governor directive | **Agency-head approval required** for AI use | Agency leadership accountable for AI architecture conformance | **DIRECT MATCH:** ISO leadership commitment = VITA agency-head approval gate. |
| 5.2 AI policy | EO-30 directs Policy Standards | Codifies Policy Standard adoption | EA-225 incorporates COV AI policy | ISO AI policy should explicitly cite EO-30 and incorporate VITA Policy Standard. |
| 5.3 Roles and responsibilities | Names Secretaries, CIO, AG, Sec. of Education | Names approver, registrant, custodian | Names agency, supplier, monitoring owner | ISO RACI / competency matrix should map to VITA-named roles. |

**Compliance level:** ISO 42001 **fully aligns** and provides documented evidence of agency-head approval.

---

### ISO 42001 Clause 6 — Planning

| ISO 42001 Control | EO-30 | VITA Policy Standard | EA-225 | Compliance Notes |
|---|---|---|---|---|
| 6.1 Risks and opportunities | Implied by guardrails | Ethical-use principles imply risk analysis | EA-225 requires risk-aware monitoring | **CRITICAL:** Pair ISO 6.1 with **NIST AI RMF** + Virginia ethical principles. |
| 6.2 AI objectives | EO-30 calls for responsible, ethical, transparent AI | Ethical principles → objectives | Performance/accuracy thresholds | ISO objectives should express EO-30 outcomes (ethical, transparent, accountable). |
| 6.3 Planning for changes | EO-30 anticipates standards evolution | Policy Standard is revision-controlled (Rev 3) | EA-225 versioned (v1.2) | ISO change management satisfies Virginia's revision-tracking expectations. |

**Compliance level:** ISO 42001 + NIST AI RMF = **complete** alignment with Virginia risk and planning expectations.

---

### ISO 42001 Clause 7 — Support

| ISO 42001 Control | EO-30 | VITA Policy Standard | EA-225 | Compliance Notes |
|---|---|---|---|---|
| 7.1 Resources | Directives presume agency resourcing | Agency funds approval workflow | Supplier resourcing requirements | Show budget for VITA registration and monitoring tooling. |
| 7.2 Competence | Education guidelines emphasize trained workforce | Implicit (ethical operators) | Implicit (technical operators) | Competency matrix should include VITA submission process literacy. |
| 7.3 Awareness | Public transparency theme | **Disclaimer requirement** on AI outputs | Documentation requirements | ISO awareness program covers VITA disclaimer obligations. |
| 7.4 Communication | Transparent communication to citizens | Communication to data subjects | Documentation to VITA/supplier | Formal communication plan satisfies Virginia transparency expectations. |
| 7.5 Documented information | EO-30 documents must be available to public | Policy Standard demands documented approvals | **EA-225 requires decision-path logging** | **DIRECT MATCH:** ISO documented information = EA-225 traceability + Policy Standard approval records. |

**Compliance level:** ISO 42001 **exceeds** what Virginia minimally requires.

---

### ISO 42001 Clause 8 — Operation

| ISO 42001 Control | EO-30 | VITA Policy Standard | EA-225 | Compliance Notes |
|---|---|---|---|---|
| 8.1 Operational planning | Five-directive operational scope | Approval before deployment | Lifecycle coverage | ISO lifecycle planning gates VITA approval point. |
| 8.2 AI impact assessment | Implicit in responsible AI directive | **Required before agency-head approval** | Impact analysis as part of architecture review | **DIRECT MATCH:** ISO AI Impact Assessment satisfies VITA pre-approval evaluation. |
| 8.3 Data management | Implicit (personal data protection) | **Personal data protection requirement** | Data inputs in scope | ISO data governance satisfies the Policy Standard's personal-data clause. |
| 8.4 Data quality | Education guidance on data bias | Ethical use → data integrity | Training-data scope | ISO quality criteria satisfy fairness/bias themes. |
| 8.5 AI system development | EO-30 covers AI development | Covers agency-developed and 3rd-party | EA-225 covers internal + third-party AI | ISO lifecycle process is the development control. |
| 8.6 Third-party AI | Directives include procurement | **Covers procurement of AI applications** | **EA-225 explicitly covers procurement** | **CRITICAL:** ISO 8.6 vendor management is how you survive an EO-30 procurement audit. |
| 8.7 Transparency / explainability | Transparent AI is a stated EO-30 goal | **Disclaimer on AI-generated outputs** | Decision-path documentation | **DIRECT MATCH:** ISO transparency = VITA disclaimer obligation. |
| 8.8 Human oversight | Education guidelines: AI augments not replaces | Ethical use → human oversight | Implicit | **DIRECT MATCH:** ISO human-in-loop satisfies Virginia ethical-use requirement. |
| 8.9 Accuracy, robustness, cybersecurity | Implicit | Implicit (ethical, responsible) | **EA-225: conform to COV security standards; metrics + thresholds for performance & accuracy** | **DIRECT MATCH:** ISO security/robustness = EA-225 conformance + monitoring. |
| 8.10 Privacy protection | Implicit (citizen data) | **Personal data protection** | Data scope | ISO privacy controls satisfy Policy Standard. |
| 8.11 Identification / traceability | Implicit | Audit trail of approvals | **EA-225: decision paths logged for traceability and replay** | **DIRECT MATCH:** ISO traceability = EA-225 decision-path logging. |
| 8.12 Business continuity | N/A | N/A | Implied resilience | ISO BC is value-add beyond minimum Virginia requirements. |
| 8.13 Incident detection | Implicit (responsible AI) | Implicit | **Monitoring metrics & thresholds** | ISO incident monitoring satisfies EA-225 monitoring requirement. |
| 8.14 Validation / testing | Implicit | Implicit (responsible AI) | EA-225 architecture review | ISO pre-deployment testing supports VITA approval evidence. |
| 8.15 Capacity, backup, archiving | N/A | Records retention implied | Documentation retention | ISO retention satisfies VITA records expectations. |

**Compliance level:** ISO 42001 **fully satisfies** EO-30 / VITA / EA-225 operational requirements across every named control.

---

### ISO 42001 Clause 9 — Performance Evaluation

| ISO 42001 Control | EO-30 | VITA Policy Standard | EA-225 | Compliance Notes |
|---|---|---|---|---|
| 9.1 Monitoring / measurement | Implicit | Ongoing ethical use | **EA-225: metrics and thresholds for model performance and accuracy** | **DIRECT MATCH:** ISO measurement = EA-225 monitoring. |
| 9.2 Internal audit | Implicit | Implicit | Implicit | ISO audit cadence provides Virginia clients with audit-ready evidence. |
| 9.3 Management review | Implicit | Periodic agency review | Periodic architecture review | ISO management review satisfies VITA review expectations. |

**Compliance level:** ISO 42001 **exceeds** Virginia's monitoring expectations.

---

### ISO 42001 Clause 10 — Improvement

| ISO 42001 Control | EO-30 | VITA Policy Standard | EA-225 | Compliance Notes |
|---|---|---|---|---|
| 10.1 Nonconformity / correction | Implicit | Ethical-use violations require remediation | Performance threshold breach triggers action | ISO corrective action covers Virginia incident response. |
| 10.2 Continual improvement | EO-30 anticipates standards evolution | Policy Standard versioning (Rev 3) | EA-225 versioning (v1.2) | ISO improvement loop tracks Virginia revisions. |

**Compliance level:** ISO 42001 improvement process **aligns** with Virginia's revision cadence.

---

## Special Compliance Areas

### Procurement Path — eVA, Cooperative Master Agreements, Direct Buy

**Virginia requirement.** Any AI procured by a Commonwealth executive branch agency — including through eVA, AI-scoped cooperative master agreements, or direct buy — is in scope of the VITA Policy Standard and EA-225.

| Virginia Procurement Reality | ISO 42001 Solution |
|---|---|
| Agency-head approval gating procurement | ISO 5.1 leadership commitment + ISO 8.2 impact assessment evidence packet |
| Registration in CTP / Planview and Archer | ISO 7.5 documented information + 8.11 traceability |
| Foreign-AI-component prohibitions in some Virginia AI-scoped procurements (under Advancing American AI Act § 7223) | ISO 8.6 third-party AI vendor selection + provenance documentation |
| Disclaimer on AI outputs | ISO 8.7 transparency control |
| Ongoing performance monitoring | ISO 9.1 + EA-225 metrics |

**ISO 42001 benefit.** An ISO 42001-aligned AIMS produces the exact evidence packet a Commonwealth agency or cooperative-procurement lead reviewer expects to see: documented approval, impact assessment, traceability, monitoring, and vendor due diligence. (Independent ISO 42001 certification is optional and is pursued directly by the client with a certification body if desired; it is not required for the AIMS to produce this evidence.)

---

### Education Sector (Virginia)

**Virginia requirement.** Public K-12 districts, the VCCS, and SCHEV-covered institutions must follow the AI Education Guidelines and (for COV-categorized institutions) the VITA Policy Standard and EA-225.

| Education Mandate | ISO 42001 Control |
|---|---|
| AI augments, does not replace, teachers | ISO 8.8 human oversight |
| Student data privacy | ISO 8.10 privacy + 8.3 data management |
| Mitigate discriminatory outcomes / algorithmic bias | ISO 8.2 impact assessment (fairness) + 8.14 validation |
| Educator competency in AI | ISO 7.2 competence |
| Higher-ed AI registration via CTP/Planview | ISO 7.5 + 8.11 |

---

### Honesty / Capability Statement Discipline

**Virginia procurement reality.** Commonwealth cooperative and agency RFPs increasingly require honest representation of certifications, prior performance, and component-supplier provenance. False or unsupported claims (SWaM-active when inactive, CMMC-certified when only RP-credentialed, foreign AI component undisclosed) are disqualifying.

| Virginia Honesty Expectation | ISO 42001 Control |
|---|---|
| Truthful representation of certifications | ISO 7.5 documented information (capability statement under change control) |
| Documented past performance | ISO 7.5 + ISO 9 audit records |
| Supplier provenance (no foreign-AI prohibited component) | ISO 8.6 vendor management |

12th House AI's [`docs/12th-house-ai-policy.md`](./12th-house-ai-policy.md) and [`docs/data-governance-procedure.md`](./data-governance-procedure.md) already implement these controls; this section makes the Virginia hook explicit.

---

## Compliance Summary Table

| Compliance Area | EO-30 | VITA Policy Std | EA-225 | AI Ed Guidelines | ISO 42001 Coverage |
|---|---|---|---|---|---|
| **Agency-head approval / leadership accountability** | ✓ | ✓ | ✓ | N/A | ✅ Clause 5 |
| **AI policy adoption** | ✓ | ✓ | ✓ | ✓ | ✅ Clause 5.2 |
| **AI Impact Assessment before deployment** | ✓ | ✓ | ✓ | N/A | ✅ Clause 8.2 — direct match |
| **Ethical-use principles** | ✓ | ✓ | ✓ | ✓ | ✅ Clauses 6.2, 8.2, 8.8 |
| **Disclaimer on AI-generated outputs** | ✓ | ✓ | ✓ | ✓ | ✅ Clause 8.7 — direct match |
| **Decision-path logging / traceability** | N/A | N/A | ✓ | N/A | ✅ Clause 8.11 — direct match |
| **Model performance / accuracy monitoring** | N/A | N/A | ✓ | N/A | ✅ Clauses 9.1 + 8.13 |
| **Personal-data / student-data privacy** | ✓ | ✓ | ✓ | ✓ | ✅ Clauses 8.3, 8.10 |
| **Vendor / procurement oversight** | ✓ | ✓ | ✓ | N/A | ✅ Clause 8.6 |
| **Public transparency / documentation** | ✓ | ✓ | ✓ | ✓ | ✅ Clauses 7.5, 8.7 |
| **Audit / management review** | ✓ | ✓ | ✓ | N/A | ✅ Clauses 9.2, 9.3 |
| **Human oversight** | ✓ | ✓ | N/A | ✓ | ✅ Clause 8.8 |
| **Continual improvement / revision tracking** | ✓ | ✓ | ✓ | N/A | ✅ Clause 10 |

**Key:** ✓ Virginia requirement present · ✅ ISO 42001 covers · N/A not explicitly addressed.

---

## How ISO 42001 + NIST AI RMF Maps to Virginia

The federal-side recommendation in [`federal-compliance-mapping.md`](./federal-compliance-mapping.md) — *ISO 42001 for governance structure, NIST AI RMF for risk method* — carries over directly to Virginia. EO-30's stated principles (responsible, ethical, transparent AI) align with NIST AI RMF's Govern–Map–Measure–Manage functions, and EA-225's monitoring requirement is naturally satisfied by NIST's "Measure" function. The Virginia regime adds two things federal does not impose as crisply:

1. **A binding gate (agency-head approval recorded in Archer / CTP)** before deployment.
2. **An explicit traceability requirement (EA-225 decision-path logging)** that is stronger than the federal record-keeping baseline.

ISO 42001 Clauses 5.1, 7.5, 8.2, and 8.11 are the four controls that carry the weight of those two Virginia-specific obligations. If a client cannot evidence those four controls cleanly, they cannot defensibly claim EO-30 conformance — regardless of what they have done for federal compliance.

---

## Implementation Checklist for Virginia Engagements

### EO-30 / VITA Policy Standard Conformance
- [ ] AI use case registered in CTP / Planview
- [ ] AI use case logged in Archer
- [ ] Agency-head approval signed and stored as evidence
- [ ] Ethical-use principles documented and reviewed
- [ ] Public disclaimer template applied to all AI-generated outputs
- [ ] Personal data handling documented end-to-end

### EA-225 Technical Conformance
- [ ] System conforms to Commonwealth security standards
- [ ] Decision paths logged for traceability and replay
- [ ] Model performance metrics and thresholds defined and monitored
- [ ] Training data inventoried and provenance documented
- [ ] Output-to-decision linkage documented
- [ ] Third-party / embedded / generative AI components identified and approved

### AI Education Guidelines (where applicable)
- [ ] Teacher / instructor AI competency plan in place
- [ ] Student data privacy controls aligned to AI tooling
- [ ] Bias / discriminatory outcome review completed for each AI tool
- [ ] Human-in-the-loop policy for instructional AI

### Procurement / RFP Discipline
- [ ] Capability statement under change control and truthful as of bid date
- [ ] Foreign AI-component review performed against any prohibition clauses (e.g., Advancing American AI Act §7223 flowdown)
- [ ] Past performance claims documented and verifiable
- [ ] SWaM / CAGE / CMMC status represented accurately

---

## Engagement Path for 12th House AI — Virginia Clients

### Phase 1 — Virginia AI Compliance Readiness Assessment (Weeks 1–4)
- Inventory all AI in use, planned, or embedded in procured software
- Classify each under VITA Policy Standard scope and EA-225 architecture scope
- Gap-analyze against EO-30, VITA Policy Standard, EA-225, and (where applicable) the AI Education Guidelines
- Deliverable: gap report, registration plan, evidence outline

### Phase 2 — Approval & Registration Sprint (Weeks 4–8)
- Prepare AI Impact Assessment per ISO 8.2
- Execute Archer + CTP/Planview registration
- Secure agency-head approval with documented evidence
- Wire ISO 8.11 logging to satisfy EA-225 decision-path requirement

### Phase 3 — Monitoring & Continuous Conformance (Ongoing)
- Stand up monitoring metrics per EA-225 + ISO 9.1
- Quarterly management review tied to ISO 9.3 cadence
- Annual gap reassessment as VITA revises standards or as the Spanberger administration publishes successor EOs/Directives

### Pricing

Pricing is structured per procurement vehicle (direct engagement, eVA solicitation, cooperative master, or sub-to-prime teaming) and is provided per RFP, per teaming agreement, or upon direct request.

Contact: **info@12thhouseai.com**

---

## Companion References

- [`federal-compliance-mapping.md`](./federal-compliance-mapping.md) — peer federal mapping
- [`12th-house-ai-policy.md`](./12th-house-ai-policy.md) — internal AIMS policy
- [`ai-lifecycle-process.md`](./ai-lifecycle-process.md) — operational lifecycle (Clause 8)
- [`data-governance-procedure.md`](./data-governance-procedure.md) — personal-data handling (Clauses 8.3, 8.10)
- [`vendor-management-procedure.md`](./vendor-management-procedure.md) — third-party AI (Clause 8.6)
- [`risk-register.md`](./risk-register.md) — risk register and treatment (Clause 6.1)

---

## Currency Note

EO-30 was signed by Governor Youngkin on January 18, 2024. The Spanberger administration took office in January 2026 and on **February 4, 2026** signed a new Executive Order and Directive establishing principles for Virginia law enforcement AI — which substantially advances EO-30's directive #4 (which had missed its October 2024 deadline). The VITA-published Policy Standard and EA-225 remain operative unless rescinded. This mapping will be updated as successor standards are published.

**Document Version:** 1.0
**Created:** 2026-05-15
**Created by:** 12th House AI
**Regulatory basis:** VA Executive Order 30 (2024); VITA Policy Standard for the Utilization of AI by COV (Rev 3, 2024-06-27); VITA EA-225 Enterprise Solutions Architecture — AI (v1.2, 2023-11-16); Guidelines for AI Integration Throughout Education in Virginia (2024); ISO/IEC 42001:2023.
