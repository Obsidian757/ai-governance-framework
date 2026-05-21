# Governance Frameworks Crosswalk
## How the 12th House AI AIMS maps to every regime our clients live under

**Purpose.** This document is the single index a nonprofit ED, a county or state procurement officer, or a state-agency program manager can read to confirm that the AI Management System (AIMS) documented in this repository speaks to **their** regulatory world — not just the abstract ISO/IEC 42001 framework.

**Framing note.** 12th House AI uses ISO/IEC 42001:2023 as the **implementation framework** for AI Management Systems. We are **not** ISO 42001 certified. We do not claim ISO 42001 certification. We do not represent that any deliverable in this repository is independently audited against ISO/IEC 42001:2023.

---

## 1. Universal frame — NIST AI Risk Management Framework

| NIST AI RMF function | What it asks | Where this AIMS addresses it |
|---|---|---|
| **GOVERN** | Cultivate a culture of AI risk management | [`12th-house-ai-policy.md`](12th-house-ai-policy.md), [`AIMS-operations-manual.md`](AIMS-operations-manual.md), [`ai-governance-statement.md`](ai-governance-statement.md) |
| **MAP** | Categorize AI systems and their context | [`ai-lifecycle-process.md`](ai-lifecycle-process.md), [`../templates/ai-system-inventory.md`](../templates/ai-system-inventory.md), [`../templates/ai-impact-assessment.md`](../templates/ai-impact-assessment.md) |
| **MEASURE** | Assess, analyze, and track AI risks | [`risk-register.md`](risk-register.md), [`incident-monitoring-plan.md`](incident-monitoring-plan.md), [`gap-analysis.md`](gap-analysis.md) |
| **MANAGE** | Allocate resources to identified risks | [`vendor-management-procedure.md`](vendor-management-procedure.md), [`data-governance-procedure.md`](data-governance-procedure.md), [`../templates/management-review-template.md`](../templates/management-review-template.md) |

**Generative AI Profile (NIST AI 600-1).** Our impact-assessment template, vendor-management procedure, and incident-monitoring plan explicitly cover the GenAI-specific risks called out in the GAI Profile: confabulation, harmful bias, dangerous content, data-privacy leakage, IP infringement, environmental impact, and human-AI configuration. See [`../templates/ai-impact-assessment.md`](../templates/ai-impact-assessment.md).

---

## 2. Federal — for clients receiving federal funds or contracting with federal agencies

| Federal regime | Applies to | Where this AIMS addresses it |
|---|---|---|
| **OMB M-24-10** (Advancing Governance, Innovation, and Risk Management for Agency Use of AI) | Federal agencies and, via flow-down, federal grantees and contractors using AI in federally-funded programs | [`federal-compliance-mapping.md`](federal-compliance-mapping.md), [`12th-house-ai-policy.md`](12th-house-ai-policy.md) |
| **OMB M-24-18** (Advancing Responsible Acquisition of AI in Government) | Federal-agency procurement of AI; vendors selling AI to federal agencies | [`vendor-management-procedure.md`](vendor-management-procedure.md), [`federal-compliance-mapping.md`](federal-compliance-mapping.md) |
| **OMB M-25-21 / M-25-22** (successor memoranda, 2025) | Same scope, updated thresholds and timelines | [`federal-compliance-mapping.md`](federal-compliance-mapping.md) |
| **Executive Order 14110** (Biden, 2023; baseline) and **EO 14179** (Trump, 2025) | Federal supply chain, AI developers, federal-funds recipients | [`federal-compliance-mapping.md`](federal-compliance-mapping.md) |

**Note for nonprofit grantees.** If your nonprofit receives federal pass-through funding (CoC funds from HUD, Title IV-E funds via your state child-welfare agency, USDA TEFAP funds, OJJDP funds, 21st CCLC funds), AI you deploy that touches those programs is *very likely* subject to OMB M-24-10 / M-24-18 flow-down through your grant terms. The Discovery Assessment scopes this in.

---

## 3. Commonwealth of Virginia — for state-agency, K-12, higher-ed, and local-government clients

> **Operating outside Virginia?** For Maryland (SB 818), North Carolina (EO 24), Tennessee (STS 200-POL-007), West Virginia, and South Carolina, see [`STATE-AI-POLICIES.md`](STATE-AI-POLICIES.md) — 6-state coverage with primary-source citations.


| Virginia regime | Scope | Where this AIMS addresses it |
|---|---|---|
| **Executive Order 30 (Youngkin, January 18, 2024)** | All Commonwealth executive-branch agencies; K-12 and higher ed via Education Guidelines | [`virginia-compliance-mapping.md`](virginia-compliance-mapping.md), [`../templates/virginia-eo30-readiness-assessment-template.md`](../templates/virginia-eo30-readiness-assessment-template.md) |
| **VITA AI Policy Standard** (Rev 3, June 27, 2024) | Agency *use* of AI — generative and embedded; procurement of AI | [`virginia-compliance-mapping.md`](virginia-compliance-mapping.md) |
| **VITA EA-225** (Enterprise Solutions Architecture for AI, v1.2) | Technical and architectural controls on COV AI systems and suppliers | [`virginia-compliance-mapping.md`](virginia-compliance-mapping.md), [`ai-lifecycle-process.md`](ai-lifecycle-process.md) |
| **AI Education Guidelines** (Office of the Secretary of Education, 2024) | K-12, VCCS, SCHEV-covered institutions | [`virginia-compliance-mapping.md`](virginia-compliance-mapping.md) |

---

## 4. Privacy — Virginia Consumer Data Protection Act (VCDPA)

The VCDPA governs how Virginia consumers' personal data is collected, processed, sold, and used to drive profiling and automated decisions. Most nonprofits and local governments holding constituent PII are touched by it directly or via contractual flow-down from a controller.

| VCDPA requirement | Where this AIMS addresses it |
|---|---|
| Data minimization and purpose limitation | [`data-governance-procedure.md`](data-governance-procedure.md) |
| Consumer rights (access, correction, deletion, portability, opt-out of targeted profiling) | [`data-governance-procedure.md`](data-governance-procedure.md), [`ai-governance-statement.md`](ai-governance-statement.md) |
| Data protection assessments (DPAs) for high-risk processing — including profiling that produces "reasonably foreseeable risk" | [`../templates/ai-impact-assessment.md`](../templates/ai-impact-assessment.md) |
| Contracts with processors specifying purpose, duration, security | [`vendor-management-procedure.md`](vendor-management-procedure.md) |

**Sensitive-data note.** VCDPA's sensitive-data category includes precise geolocation, racial/ethnic origin, religious beliefs, mental/physical health diagnosis, sexual orientation, citizenship/immigration status, genetic/biometric data, and data of a known child. Several of the verticals 12th House AI serves (homelessness, child welfare, DV) routinely process sensitive data and require the heightened controls flagged in our data-governance procedure.

---

## 5. Vertical-specific federal regimes

The AIMS spine above is the same for every client. The vertical regime that *also* applies depends on the client.

### 5.1 Homelessness services (Continuum-of-Care funded organizations)

**Examples:** Continuum-of-Care lead agencies, shelters, rapid-rehousing providers, street-outreach teams.

- **HUD HMIS Data Standards (2024 Manual and Dictionary)** — HMIS data collection, retention, deduplication, project-type rules, AFCARS-style annual reporting on CoC client populations.
- **HUD CoC Program Interim Rule (24 CFR Part 578)** — privacy plans, data-quality plans, HMIS participation requirements.
- **VAWA 2022** — survivor-confidentiality firewall: when HMIS data overlaps with DV-survivor data, the data must be segregated and aggregated, never linked.

**Where this AIMS addresses it:**
- AI Impact Assessment template requires explicit identification of HMIS data flows touching any AI system.
- Data Governance Procedure references HMIS retention requirements (7-year default, with special handling for client deduplication and HUD APR submission).
- Vendor Management Procedure requires confirmation that any AI processor handling HMIS data is covered by a HUD-aware DPA.

### 5.2 Child welfare and child-serving programs

**Examples:** State-licensed foster-care agencies, kinship-care programs, residential treatment.

- **Title IV-E of the Social Security Act** — federal foster-care and adoption-assistance funding; recordkeeping, eligibility documentation, case-plan requirements.
- **AFCARS** (Adoption and Foster Care Analysis and Reporting System) — semi-annual federal reporting on children in foster care and adopted from foster care.
- **CCWIS / SACWIS** rules where the state uses a comprehensive child-welfare information system that your AI integrates with.

**Where this AIMS addresses it:**
- Discovery Assessment template explicitly asks for any AI touchpoint with case-plan generation, risk-score recommendations, or kinship-search; flags the heightened scrutiny required when an AI recommendation could shape a placement decision (human-in-the-loop is non-negotiable).
- Risk Register includes a category for "automated decisions affecting protected populations" with a default-high impact score.

### 5.3 Food security (TEFAP / CSFP / SNAP-Ed partners)

**Examples:** Regional food banks, mobile pantries, school-based food programs.

- **USDA TEFAP recordkeeping** (7 CFR 251) — eligibility documentation, distribution records, retention.
- **USDA civil rights requirements** for federally-funded food programs — non-discrimination, "And Justice for All" poster, complaint procedures.

**Where this AIMS addresses it:**
- AI Impact Assessment template requires civil-rights impact analysis when an AI system informs eligibility screening, intake routing, or partner-agency allocation.
- Data Governance Procedure references USDA retention defaults.

### 5.4 Youth services and education-adjacent programs

**Examples:** Boys & Girls Clubs, after-school programs, 21st Century Community Learning Center grantees.

- **DOJ OJJDP** grant requirements where applicable.
- **VDOE 21st CCLC** monitoring requirements for after-school grantees.
- **FERPA** (20 U.S.C. § 1232g) — education records confidentiality.
- **COPPA** (15 U.S.C. § 6501–6506) — under-13 data collection.

**Where this AIMS addresses it:**
- Vendor Management Procedure requires confirmation that any AI vendor handling student records is FERPA-aware and, where users may be under 13, COPPA-compliant.
- Data Governance Procedure includes the FERPA "directory information" and "education record" definitions and the consent requirements that follow.

### 5.5 Domestic-violence survivor services

**Examples:** DV shelters, sexual-assault services, hotline programs.

- **VAWA 2022** — survivor-confidentiality firewall. Personally identifying information collected by a VAWA-funded program may not be entered into a shared database without survivor consent. HMIS data and DV data must remain segregated.

**Where this AIMS addresses it:**
- AI Impact Assessment template carries a dedicated DV-survivor section: AI that ingests or produces data touching a VAWA-covered program must use aggregated and de-identified data only, and a documented confidentiality firewall must be in place.

---

## 6. ISO/IEC 42001:2023 — the implementation spine

ISO/IEC 42001:2023 is the framework we use to organize all of the above. We treat it as the *connective tissue* between the regimes in §§1–5 — not as a certification we hold.

| ISO 42001 clause area | What it requires | Where this AIMS addresses it |
|---|---|---|
| **Clause 4 — Context of the organization** | Internal/external issues, interested parties, scope of the AIMS | [`12th-house-ai-policy.md`](12th-house-ai-policy.md), [`../templates/stakeholder-register.md`](../templates/stakeholder-register.md) |
| **Clause 5 — Leadership** | Top management commitment, AI policy, roles/responsibilities | [`12th-house-ai-policy.md`](12th-house-ai-policy.md), [`AIMS-operations-manual.md`](AIMS-operations-manual.md) |
| **Clause 6 — Planning** | Risks, opportunities, AI objectives, change planning | [`risk-register.md`](risk-register.md), [`gap-analysis.md`](gap-analysis.md) |
| **Clause 7 — Support** | Resources, competence, awareness, communication, documented information | [`competency-matrix.md`](competency-matrix.md), [`../templates/training-records.md`](../templates/training-records.md), [`../templates/communication-plan.md`](../templates/communication-plan.md) |
| **Clause 8 — Operation** | AI lifecycle, AI impact assessment, third-party AI, data | [`ai-lifecycle-process.md`](ai-lifecycle-process.md), [`../templates/ai-impact-assessment.md`](../templates/ai-impact-assessment.md), [`data-governance-procedure.md`](data-governance-procedure.md), [`vendor-management-procedure.md`](vendor-management-procedure.md) |
| **Clause 9 — Performance evaluation** | Monitoring, internal audit, management review | [`incident-monitoring-plan.md`](incident-monitoring-plan.md), [`../templates/internal-audit-checklist.md`](../templates/internal-audit-checklist.md), [`../templates/management-review-template.md`](../templates/management-review-template.md) |
| **Clause 10 — Improvement** | Nonconformity, corrective action, continual improvement | [`AIMS-operations-manual.md`](AIMS-operations-manual.md) |
| **Annex A — Reference controls** | 38 control objectives across AI policy, internal organization, resources, impact assessment, lifecycle, data, third parties, customers/users | Covered across the documents above; the [`gap-analysis.md`](gap-analysis.md) shows the worksheet |

---

## 7. What this means for a first conversation with us

If you are an evaluator reading this, the bilateral test is simple:

1. **Find your regime** in the table above.
2. **Open the file the row points at.**
3. **Tell us where the language doesn't match your reality.** We will close the gap.

That is the work. The frameworks themselves are public. The integration of the frameworks into a coherent, audit-survivable AIMS — that is what we do.

---

## 8. AI provenance disclosure

This document was drafted with the assistance of large language models, reviewed and edited by a human author who is accountable for its content. Every framework citation in this document is traceable to a public source. No AI system in our workflow makes consequential decisions without a human-in-the-loop checkpoint.

---

*Version 1.0 — May 21, 2026. Maintained by Brannon Joseph Solomon Jr., 12th House AI, LLC.*
