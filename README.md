# 12th House AI — Public AIMS Package

**ISO/IEC 42001-aligned AI Management System (AIMS) — full documentation set**
**Federal, Commonwealth of Virginia, and nonprofit-sector AI governance — control mappings**

12th House AI is a founder-led, veteran-owned AI governance and workflow-automation consultancy based in Hampton Roads, Virginia. We serve **nonprofits, state and local government, and SMBs**, with federal work under teaming arrangements. This repository is our **publicly published AI Management System (AIMS) package** — the documentation framework we use for our own practice and the same framework we implement for clients.

We publish it in the open because most consulting firms talk about their methodology. We show ours.

---

## Evaluator's Quick Read (30-second version)

**If you are a nonprofit executive director, city or county procurement officer, or state-agency program manager evaluating whether 12th House AI speaks your governance language — start here.**

| You operate under… | We map to it explicitly |
|---|---|
| **NIST AI RMF 1.0 + Generative AI Profile** | [`docs/federal-compliance-mapping.md`](docs/federal-compliance-mapping.md), [`docs/GOVERNANCE-FRAMEWORKS.md`](docs/GOVERNANCE-FRAMEWORKS.md) |
| **Virginia Executive Order 30 (2024) / VITA AI Policy Standard / VITA EA-225** | [`docs/virginia-compliance-mapping.md`](docs/virginia-compliance-mapping.md), [`templates/virginia-eo30-readiness-assessment-template.md`](templates/virginia-eo30-readiness-assessment-template.md) |
| **Maryland SB 818 / NC EO 24 / TN STS 200-POL-007 / WV / SC** (mid-Atlantic + Southeast state AI regimes) | [`docs/STATE-AI-POLICIES.md`](docs/STATE-AI-POLICIES.md) — 6-state coverage with primary-source citations |
| **OMB M-24-10 / M-24-18 (federal-funds recipients)** | [`docs/GOVERNANCE-FRAMEWORKS.md`](docs/GOVERNANCE-FRAMEWORKS.md) |
| **Virginia Consumer Data Protection Act (VCDPA)** | [`docs/data-governance-procedure.md`](docs/data-governance-procedure.md), [`docs/GOVERNANCE-FRAMEWORKS.md`](docs/GOVERNANCE-FRAMEWORKS.md) |
| **HUD HMIS Data Standards 2024** (homelessness orgs) | [`docs/GOVERNANCE-FRAMEWORKS.md`](docs/GOVERNANCE-FRAMEWORKS.md) §Vertical-Specific |
| **Title IV-E + AFCARS** (child welfare) | [`docs/GOVERNANCE-FRAMEWORKS.md`](docs/GOVERNANCE-FRAMEWORKS.md) §Vertical-Specific |
| **USDA TEFAP recordkeeping + civil rights** (food banks) | [`docs/GOVERNANCE-FRAMEWORKS.md`](docs/GOVERNANCE-FRAMEWORKS.md) §Vertical-Specific |
| **DOJ OJJDP / VDOE 21st CCLC / FERPA / COPPA** (youth services) | [`docs/GOVERNANCE-FRAMEWORKS.md`](docs/GOVERNANCE-FRAMEWORKS.md) §Vertical-Specific |
| **VAWA 2022** (DV survivor data segregation) | [`docs/GOVERNANCE-FRAMEWORKS.md`](docs/GOVERNANCE-FRAMEWORKS.md) §Vertical-Specific |

The ISO/IEC 42001 framework underneath is the *spine*. The vertical-specific obligations above are how that spine attaches to **your** regulatory reality.

**Important framing notes:**

- We use ISO/IEC 42001:2023 as the **implementation framework** for AI Management Systems. We are **not** ISO 42001 certified, and we are **not** pursuing organizational ISO 42001 certification. Wherever you see "ISO 42001" in this repository, read it as "ISO 42001-aligned."
- We are **veteran-owned**. We are **not** SDVOSB, VOSB, 8(a), HUBZone, CMMC-certified, or FedRAMP-authorized.
- Virginia SWaM application **#845183 in process**. Not yet active.
- Every AI workflow we recommend keeps **a human in the loop** on consequential decisions. We do not deploy autonomous decision-making AI.

---

## What you get in this repository

| Area | Contents |
|---|---|
| **AIMS core** | AI Policy · Operations Manual · AI Lifecycle Process · Risk Register · Data Governance Procedure · Vendor Management Procedure · Incident Monitoring Plan · Competency Matrix · Gap Analysis |
| **Governance frameworks crosswalk** | [`docs/GOVERNANCE-FRAMEWORKS.md`](docs/GOVERNANCE-FRAMEWORKS.md) — single index mapping the AIMS to NIST AI RMF, VA EO 30, VITA EA-225, OMB M-24-10/M-24-18, VCDPA, and vertical-specific federal regimes |
| **State AI policies crosswalk** | [`docs/STATE-AI-POLICIES.md`](docs/STATE-AI-POLICIES.md) — 6-state coverage (VA / MD / NC / TN / WV / SC) with primary-source citations; honest read on which states have binding teeth |
| **Federal crosswalk** | ISO 42001 ↔ NIST AI RMF ↔ OMB ↔ EO 14110/14179 ([`docs/federal-compliance-mapping.md`](docs/federal-compliance-mapping.md)) |
| **Commonwealth of Virginia crosswalk** | ISO 42001 ↔ EO-30 ↔ VITA Policy Standard ↔ EA-225 ↔ AI Education Guidelines ([`docs/virginia-compliance-mapping.md`](docs/virginia-compliance-mapping.md)) |
| **Templates** | AI Impact Assessment · AI System Inventory · Internal Audit Checklist · Management Review · Training Records · Stakeholder Register · Communication Plan · VA EO-30 Readiness Assessment · Discovery Assessment · Gap Analysis |
| **Marketing** | One-page capability statement |
| **Client Management** | Engagement scaffolding (client folder template, status template, weekly summary) |
| **Evidence** | AI Risk Register (xlsx) · Metrics Tracking (xlsx) · Signature page · Pre-signature verification |

---

## Status (as of May 21, 2026)

- **AIMS documentation:** Complete and published as the framework we implement against.
- **ISO/IEC 42001:2023 framework application:** In use as the implementation spine. **No certification claim.** We are not certified and are not pursuing certification.
- **Federal / Virginia / vertical-specific control mappings:** Published.
- **Client engagement history under 12th House AI:** Active outreach to first cohort (nonprofit + SMB). Engagements will be reflected here as they are delivered, not before.

We are explicit about stage. We do not exaggerate scale we don't have.

---

## Repository structure

```
iso-42001-aligned-aims/
├── docs/                    # Core AIMS documentation + framework crosswalks
├── templates/               # Reusable templates
├── marketing/               # Capability statement
├── client-management/       # Engagement scaffolding (templates only — no live clients yet)
├── evidence/                # Audit-trail artifacts
├── README.md                # This file
└── tools-guide.md           # Internal: how to use templates in engagements
```

---

## Core documentation — `/docs/`

| File | What it is |
|---|---|
| [`GOVERNANCE-FRAMEWORKS.md`](docs/GOVERNANCE-FRAMEWORKS.md) | **Start here.** Single-page index mapping the AIMS to every governance framework we align to. |
| [`iso-42001-explained-simple.md`](docs/iso-42001-explained-simple.md) | Plain-English ISO 42001 explanation |
| [`12th-house-ai-policy.md`](docs/12th-house-ai-policy.md) | AIMS Policy (auditor-facing) |
| [`AIMS-operations-manual.md`](docs/AIMS-operations-manual.md) | Internal AIMS Operations Manual |
| [`ai-governance-statement.md`](docs/ai-governance-statement.md) | Public-facing AI Governance Statement |
| [`ai-lifecycle-process.md`](docs/ai-lifecycle-process.md) | AI system lifecycle management |
| [`data-governance-procedure.md`](docs/data-governance-procedure.md) | Data handling for AI systems (VCDPA-aligned) |
| [`vendor-management-procedure.md`](docs/vendor-management-procedure.md) | Third-party AI vendor oversight |
| [`incident-monitoring-plan.md`](docs/incident-monitoring-plan.md) | Detection systems and triggers |
| [`risk-register.md`](docs/risk-register.md) | Risk register guidance |
| [`gap-analysis.md`](docs/gap-analysis.md) | Current-state vs. ISO 42001-aligned AIMS requirements |
| [`competency-matrix.md`](docs/competency-matrix.md) | Personnel qualifications (ISO 42001 §7.2) |
| [`federal-compliance-mapping.md`](docs/federal-compliance-mapping.md) | ISO 42001 ↔ NIST AI RMF ↔ OMB ↔ Executive Orders |
| [`virginia-compliance-mapping.md`](docs/virginia-compliance-mapping.md) | ISO 42001 ↔ Virginia EO-30 ↔ VITA Policy Standard ↔ EA-225 ↔ AI Education Guidelines |

---

## Templates — `/templates/`

### Engagement-deliverable templates

| File | Use |
|---|---|
| [`discovery-assessment-template.md`](templates/discovery-assessment-template.md) | AI Compliance Discovery Assessment — the shape of the Tier-1 deliverable |
| [`virginia-eo30-readiness-assessment-template.md`](templates/virginia-eo30-readiness-assessment-template.md) | Commonwealth of Virginia EO-30 / VITA Policy Standard / EA-225 readiness assessment |
| [`gap-analysis-template.md`](templates/gap-analysis-template.md) | Reusable per-engagement ISO 42001-aligned gap analysis worksheet (Clauses 4–10 + Annex A) |

### AIMS-operations templates

| File | Use |
|---|---|
| [`ai-impact-assessment.md`](templates/ai-impact-assessment.md) | Pre-deployment AI impact assessment, per system |
| [`ai-system-inventory.md`](templates/ai-system-inventory.md) | AI inventory — works as client-discovery instrument and standing inventory |
| [`internal-audit-checklist.md`](templates/internal-audit-checklist.md) | ISO 42001-aligned internal audit (Clause 9.2) |
| [`management-review-template.md`](templates/management-review-template.md) | AIMS management review meetings (Clause 9.3) |
| [`training-records.md`](templates/training-records.md) | Competency / training log (Clause 7.2) |
| [`communication-plan.md`](templates/communication-plan.md) | Internal & external AI communications (Clause 7.4) |
| [`stakeholder-register.md`](templates/stakeholder-register.md) | Interested-parties register (Clause 4.2) |

---

## Engagement scopes

We work as a **prime** on direct nonprofit and SMB engagements and as a **subcontractor** under partner primes (notably on Commonwealth of Virginia eVA and cooperative procurements). Pricing is provided per RFP, per teaming agreement, or upon direct request — not as a public retail rate card.

### Nonprofit & state/local government (primary lane in 2026)

| Tier | Scope |
|---|---|
| **Compliance Readiness Assessment** | AI inventory · gap analysis against the regimes that apply to the client (e.g., HUD HMIS, Title IV-E, USDA TEFAP, FERPA/COPPA, VCDPA) · risk register · executive briefing |
| **Governance Documentation Pack** | Policy + AI Impact Assessment + Data Governance + Vendor Management documents calibrated to the client's regulatory stack |
| **Implementation Support** | Three- to six-month engagement supporting AIMS rollout and evidence collection |

### Commonwealth of Virginia (EO-30 / VITA / EA-225)

| Tier | Scope |
|---|---|
| **Virginia AI Compliance Readiness Assessment** | Inventory, classification under VITA Policy Standard and EA-225, gap report |
| **VITA Approval & Registration Sprint** | Archer + CTP/Planview registration, agency-head approval evidence packet, EA-225 instrumentation plan |
| **Ongoing Quarterly Conformance** | Conformance review, successor-standards tracking |

### Federal (via teaming)

We engage federal opportunities through teaming with credentialed primes. Direct federal prime work is deferred until our small-business credentials catch up to where we want them.

Deliverable shapes are published as templates under [`templates/`](templates/). Full one-pager: [`marketing/capability-statement.md`](marketing/capability-statement.md).

---

## Companion artifacts

- [`federal-ai-policy-rag`](https://github.com/Obsidian757/federal-ai-policy-rag) — Streamlit RAG over the federal and Virginia AI policy library, with a jurisdiction selector.
- [`12thhouseai.com`](https://12thhouseai.com) — public practice website.

---

## Credential posture

| Credential | Status |
|---|---|
| DoD Secret Clearance — founder | Active |
| NIST AI Risk Management Framework — practitioner experience | Active |
| Veteran-owned (founder, U.S. Navy) | Confirmed |
| Virginia SWaM (#845183) | Application in process — not yet active |
| ISO/IEC 42001:2023 (organizational certification) | **Not held; not pursuing.** Framework used as the AIMS implementation spine. |
| ISO/IEC 42001 Lead Implementer (PECB) | Under consideration |

**Explicitly NOT held and NOT pursuing:**
- SDVOSB / VOSB certification (eligibility under review; certification not granted)
- 8(a), HUBZone, WOSB
- CMMC Registered Practitioner or any CMMC certification
- FedRAMP authorization
- ISO 42001 organizational certification

We will update this README as credentials evolve.

---

## What this AIMS package is *not*

- **Not a portfolio of past client engagements.** 12th House AI is a new practice. Client work will be reflected here as it is delivered, not before.
- **Not a Big-4 alternative.** We are deliberately small, founder-led, and rate-aligned to nonprofit and SMB budgets.
- **Not a CMMC offering.** We do not provide CMMC RP services.
- **Not an autonomous-AI vendor.** Every AI workflow we recommend includes a human in the loop on consequential decisions.

---

## AI provenance disclosure

Some content in this repository was drafted with the assistance of large language models under human review and editorial control. The author is responsible for every word published here. No AI system in our workflow operates without a human-in-the-loop checkpoint.

---

## Contact

**Brannon Joseph Solomon Jr.** — Founder
Email: info@12thhouseai.com
Web: [12thhouseai.com](https://12thhouseai.com)
Location: Hampton Roads, Virginia

---

*Documentation in this repository is published under the terms of the LICENSE file. Engagements with clients are governed by separate agreements.*
