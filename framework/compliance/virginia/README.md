# Virginia AI Governance — Compliance Directory

## Overview

Virginia operates one of the more layered state AI governance regimes in the US. Unlike the EU AI Act — which imposes binding obligations organized by risk tier — Virginia's regime is built primarily through executive authority: back-to-back governors have used EOs to set direction before the General Assembly acted, and VITA has layered technical policy standards beneath the EOs. Practitioners must track both layers simultaneously: the executive instruments define *what* agencies must do, while VITA standards define *how* they must do it within Commonwealth technology infrastructure.

Two administrations have now shaped this landscape. Governor Youngkin's EO 30 (January 2024) created the foundational governance scaffold — agency-head approval requirements, a public-facing Inventory of AI Tools, and alignment with NIST AI RMF. His EO 26 (February 2025) added a supply-chain dimension by prohibiting PRC-origin AI platforms (naming DeepSeek) on COV systems. Governor Spanberger took office in January 2026 and issued her own AI EO and an accompanying Directive focused on law enforcement AI use; further administrative guidance is expected as her team reviews existing VITA standards.

On the legislative side, HB 2094 (the High-Risk AI Act, session 2025) passed both chambers but was vetoed on March 24, 2025. Its provisions — modeled loosely on Colorado SB 23-205 and the EU AI Act's high-risk categories — signal where the General Assembly is headed. Vendors and agencies that read HB 2094 carefully are better positioned for the legislation that will eventually pass.

VITA standards operate largely independent of which administration is in office. EA-225 (Enterprise Solutions Architecture for AI) and the AI Utilization Policy Standard (Revision 3, June 2024) translate EO intent into procurement and technical controls. The IA standards (SEC 501-09, SEC 525-01, SEC 528-02, GOV 519-02) govern the security perimeter around any AI system handling COV data.

For vendors selling into Virginia agencies, the practical gatekeeping sequence is: (1) confirm the use case clears EO 30 agency-head approval, (2) verify the tool appears or is registerable in the Archer/CTP inventory, (3) satisfy VITA EA-225 architecture alignment, (4) confirm IA security standards compliance, and (5) procure through the appropriate vehicle (eVA, SWaM-eligible cooperative, or applicable master agreement).

---

## Instruments Covered

| Instrument | Type | Effective | Status |
|---|---|---|---|
| EO 30 (Youngkin) | Executive Order | Jan 18, 2024 | Active |
| EO 26 (Youngkin) | Executive Order | Feb 11, 2025 | Active |
| Spanberger AI EO | Executive Order | Feb 4, 2026 | Active |
| Spanberger AI Directive | Executive Directive | Feb 4, 2026 | Active |
| HB 2094 | Legislation (vetoed) | — | Vetoed Mar 24, 2025 |
| VITA AI Utilization Policy Standard Rev 3 | Policy Standard | Jun 27, 2024 | Active |
| VITA EA-225 v1.2 | Architecture Standard | Nov 16, 2023 | Active; revision expected |
| VITA ITRM SEC 501-09 | IA Standard | Current | Active |
| VITA ITRM SEC 525-01 | IA Standard | Current | Active |
| VITA ITRM SEC 528-02 | IA Standard | Current | Active |
| VITA ITRM GOV 519-02 | IA Governance | Current | Active |
| VA AI Education Guidelines | State Guidelines | 2024 | Active |

---

## Navigation

| File | Covers | Primary Audience |
|---|---|---|
| [eo-mapping.md](eo-mapping.md) | EO 30, EO 26, Spanberger EO/Directive — control requirements, agency-head approval gates, prohibited platforms, law enforcement AI constraints | Agency AI leads, vendors pursuing state contracts |
| [vita-ea225-mapping.md](vita-ea225-mapping.md) | EA-225 Enterprise Solutions Architecture for AI — architecture patterns, CTP/Planview registration, decision-path logging, performance monitoring | Enterprise architects, IT procurement officers, AI platform vendors |
| [vita-policy-standard-mapping.md](vita-policy-standard-mapping.md) | VITA AI Utilization Policy Standard Rev 3 — use-case approval workflow, inventory requirements, responsible-use controls | Agency technology officers, program managers, vendors |
| [vita-ia-standards.md](vita-ia-standards.md) | ITRM SEC 501-09, SEC 525-01, SEC 528-02, GOV 519-02 — security controls, risk assessment, encryption, privacy requirements for AI systems on COV infrastructure | CISOs, security engineers, FedRAMP/StateRAMP practitioners |
| [education-guidelines-mapping.md](education-guidelines-mapping.md) | Virginia AI Education Guidelines (2024) — K-12 LEA and higher-education requirements, student data privacy, educator competency, EdTech procurement | School division technology coordinators, higher-ed CIOs, EdTech vendors |

---

## Templates

| Template | Location |
|---|---|
| Virginia EO 30 Readiness Assessment | [templates/virginia/eo30-readiness-assessment.md](../../../../templates/virginia/eo30-readiness-assessment.md) |
| VITA AI System Registration Guide | [templates/virginia/vita-ai-system-registration.md](../../../../templates/virginia/vita-ai-system-registration.md) |

---

## Relationship to the Framework

The framework uses NIST AI RMF 1.0 (Govern / Map / Measure / Manage) as its universal organizational structure. Virginia's instruments do not replace that structure — they add jurisdiction-specific operational gates that must be satisfied at defined points in the lifecycle.

Key integration points:

**Govern function.** EO 30 requires agency-head approval before deploying any AI tool. This gate sits within the governance workflow at the use-case intake stage. Map EO 30 agency-head approval onto the [governance workflow](../../governance-operations/governance-workflow.md) intake checkpoint and the [control register](../../governance-operations/control-register.md) as a mandatory pre-deployment control.

**Map function.** Virginia's risk classification logic — present in HB 2094's definitions (even vetoed, they signal future legislative intent) and in EO 30's tiered treatment — maps directly onto the framework's T1–T4 risk tiers in [risk-matrix.md](../../risk-classification/risk-matrix.md). Law enforcement AI under the Spanberger Directive carries additional constraints that push affected use cases to T1.

**Measure function.** VITA EA-225 requires architecture conformance review via CTP/Planview before procurement. Map this to the framework's [deployment-gates.md](../../llm-lifecycle/deployment-gates.md).

**Manage function.** Audit trail requirements under EO 30 and VITA policy standards require that AI decision paths be logged and that humans retain meaningful override authority. Map to [audit-trail-requirements.md](../audit-trail-requirements.md) and [human-in-loop-patterns.md](../../responsible-ai/human-in-loop-patterns.md).

Public disclaimer requirements (VITA Policy Standard) align with the framework's [transparency-standards.md](../../responsible-ai/transparency-standards.md). Any Commonwealth-facing AI interaction must disclose AI involvement.

---

## Procurement Paths

Virginia agency procurement routes relevant to AI vendors:

- **eVA** — mandatory Commonwealth electronic procurement portal for agency purchases. All AI software and service contracts must be entered or referenced in eVA.
- **SWaM certification** — Small, Women-owned, and Minority-owned Business program. AI vendors with SWaM certification receive evaluation preference. Registration through DSBSD.
- **Cooperative master agreements** — VITA statewide contracts and NASPO ValuePoint allow agencies to purchase AI tools without a full competitive procurement. Confirm EA-225 alignment separately — a NASPO vehicle does not automatically satisfy VITA architecture standards.
- **Micro-purchases** — under $10,000 have simplified procedures but still require EO 30 agency-head approval if the tool uses AI.

---

## Watch Items — Spanberger Administration (January 2026+)

1. **VITA standards revision cycle.** EA-225 (v1.2, Nov 2023) and the AI Utilization Policy Standard (Rev 3, Jun 2024) were both issued under the prior administration. A revision is likely in the 2026–2027 cycle. Set a review trigger for any VITA ITRM publication.
2. **Law enforcement AI Directive implementation guidance.** Agency-level implementation plans are expected to follow the February 2026 Directive. Vendors serving public safety agencies should monitor.
3. **HB 2094 reintroduction.** Likely to return in 2026 or 2027 with modifications. Vendors whose tools qualify as "high-risk" under HB 2094's definitions should begin gap analysis against [eu-ai-act-mapping.md](../eu-ai-act-mapping.md), which covers substantially similar requirements.
4. **VCDPA enforcement posture.** The Attorney General's enforcement posture under the new administration may increase scrutiny of AI-driven profiling and automated decision-making affecting Virginia residents.

---

*This directory is maintained as part of the 12th House AI Governance Framework. Cross-reference with [nist-ai-rmf-mapping.md](../nist-ai-rmf-mapping.md) for the universal control structure and [multi-jurisdictional-guide.md](../multi-jurisdictional-guide.md) for Virginia's relationship to federal and other state regimes.*
