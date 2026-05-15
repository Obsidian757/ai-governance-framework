# 12th House AI — Public AIMS Package

**ISO/IEC 42001:2023 AI Management System — full documentation set**
**Federal &amp; Commonwealth of Virginia AI compliance — control mappings**

12th House AI is a founder-led federal &amp; Commonwealth of Virginia AI compliance consulting practice based in Hampton Roads, Virginia. This repository is our **publicly published AI Management System (AIMS) package** — the same documentation we use to certify our own practice, and the same documentation we recommend to clients.

We publish it in the open because most consulting firms talk about their methodology. We show ours.

---

## What you get in this repository

| Area | Contents |
|---|---|
| **AIMS core** | AI Policy · Operations Manual · AI Lifecycle Process · Risk Register · Data Governance Procedure · Vendor Management Procedure · Incident Monitoring Plan · Competency Matrix · Gap Analysis |
| **Crosswalks** | ISO 42001 ↔ Federal (OMB M-25-21, M-25-22, NIST AI RMF, EO 14110) · ISO 42001 ↔ Commonwealth of Virginia (EO-30, VITA Policy Standard, EA-225, AI Education Guidelines) |
| **Templates** | AI Impact Assessment · AI System Inventory · Internal Audit Checklist · Management Review · Training Records · Stakeholder Register · Communication Plan |
| **Marketing** | One-page capability statement |
| **Client Management** | Engagement scaffolding (client folder template, status template, weekly summary) |
| **Evidence** | AI Risk Register (xlsx) · Metrics Tracking (xlsx) · Signature page · Pre-signature verification |

---

## Status (as of May 15, 2026)

- **AIMS documentation:** Complete
- **ISO/IEC 42001:2023 organizational certification:** **In progress.** We will publish a date here once Stage 2 is scheduled and confirmed.
- **Federal &amp; Virginia control mappings:** Published.
- **Client engagement history under 12th House AI:** None yet — practice launching with this AIMS as proof-of-work.

We are explicit about stage. We do not exaggerate scale we don't have.

---

## Repository structure

```
iso-42001-certification/
├── docs/                    # Core AIMS documentation (13 files)
├── templates/               # Reusable templates (5 files)
├── marketing/               # Capability statement (1 file)
├── client-management/       # Engagement scaffolding (templates only — no live clients yet)
├── evidence/                # Audit evidence
├── README.md                # This file
└── tools-guide.md           # Internal: how to use templates in engagements
```

---

## Core documentation — `/docs/`

| File | What it is |
|---|---|
| [`iso-42001-explained-simple.md`](docs/iso-42001-explained-simple.md) | Plain-English ISO 42001 explanation |
| [`12th-house-ai-policy.md`](docs/12th-house-ai-policy.md) | AIMS Policy (auditor-facing) |
| [`AIMS-operations-manual.md`](docs/AIMS-operations-manual.md) | Internal AIMS Operations Manual |
| [`ai-governance-statement.md`](docs/ai-governance-statement.md) | Public-facing AI Governance Statement |
| [`ai-lifecycle-process.md`](docs/ai-lifecycle-process.md) | AI system lifecycle management |
| [`data-governance-procedure.md`](docs/data-governance-procedure.md) | Data handling for AI systems |
| [`vendor-management-procedure.md`](docs/vendor-management-procedure.md) | Third-party AI vendor oversight |
| [`incident-monitoring-plan.md`](docs/incident-monitoring-plan.md) | Detection systems and triggers |
| [`risk-register.md`](docs/risk-register.md) | Risk register guidance |
| [`gap-analysis.md`](docs/gap-analysis.md) | Current state vs. ISO 42001 requirements |
| [`competency-matrix.md`](docs/competency-matrix.md) | Personnel qualifications (ISO 42001 §7.2) |
| [`federal-compliance-mapping.md`](docs/federal-compliance-mapping.md) | ISO ↔ OMB ↔ NIST AI RMF ↔ EO 14110 |
| [`virginia-compliance-mapping.md`](docs/virginia-compliance-mapping.md) | ISO ↔ Virginia EO-30 ↔ VITA Policy Standard ↔ EA-225 ↔ AI Education Guidelines |

---

## Templates — `/templates/`

### Engagement-deliverable templates (assessment work)

| File | Use |
|---|---|
| [`discovery-assessment-template.md`](templates/discovery-assessment-template.md) | Federal AI Compliance Discovery Assessment — the shape of the Tier-1 ($7,500) deliverable |
| [`virginia-eo30-readiness-assessment-template.md`](templates/virginia-eo30-readiness-assessment-template.md) | Commonwealth of Virginia EO-30 / VITA Policy Standard / EA-225 readiness assessment deliverable |
| [`gap-analysis-template.md`](templates/gap-analysis-template.md) | Reusable per-engagement ISO/IEC 42001 gap analysis worksheet (Clauses 4–10 + Annex A) |

### AIMS-operations templates (used inside an engagement or our own AIMS)

| File | Use |
|---|---|
| [`ai-impact-assessment.md`](templates/ai-impact-assessment.md) | Pre-deployment AI impact assessment, per system |
| [`ai-system-inventory.md`](templates/ai-system-inventory.md) | AI inventory — works as both client-discovery instrument and standing inventory |
| [`internal-audit-checklist.md`](templates/internal-audit-checklist.md) | ISO 42001 internal audit (Clause 9.2) |
| [`management-review-template.md`](templates/management-review-template.md) | AIMS management review meetings (Clause 9.3) |
| [`training-records.md`](templates/training-records.md) | Competency / training log (Clause 7.2) |
| [`communication-plan.md`](templates/communication-plan.md) | Internal & external AI communications (Clause 7.4) |
| [`stakeholder-register.md`](templates/stakeholder-register.md) | Interested-parties register (Clause 4.2) |

---

## Services overview

| Tier | Investment | Scope |
|---|---|---|
| **Discovery Assessment** | $7,500 | AI inventory · gap analysis · risk assessment · executive briefing |
| **Strategic Roadmap** | $25,000 | 90-day implementation plan plus governance documentation |
| **Ultimate Warrior** | $75,000 | Six-month engagement supporting full ISO 42001 implementation toward certification readiness |

We also offer Commonwealth of Virginia EO-30 / VITA / EA-225 engagements:

| Tier | Investment | Scope |
|---|---|---|
| **Virginia AI Compliance Readiness Assessment** | $7,500–$15,000 | Inventory, classification under VITA Policy Standard and EA-225, gap report |
| **VITA Approval &amp; Registration Sprint** | $15,000–$35,000 | Archer + CTP/Planview registration, agency-head approval evidence packet, EA-225 instrumentation plan |
| **Ongoing Quarterly Conformance** | $2,500 / quarter | Conformance review, successor-standards tracking |

Full one-pager: [`marketing/capability-statement.md`](marketing/capability-statement.md)

---

## Companion artifacts

- [`federal-ai-policy-rag`](https://github.com/Obsidian757/federal-ai-policy-rag) — Streamlit RAG over the federal and Virginia AI policy library, with a jurisdiction selector so you can scope questions to Federal, Commonwealth of Virginia, or both.
- [`12thhouseai.com`](https://12thhouseai.com) — public practice website.

---

## Credential posture

| Credential | Status |
|---|---|
| DoD Secret Clearance — founder | Active |
| NIST AI Risk Management Framework — practitioner experience | Active |
| ISO/IEC 42001:2023 (organizational) | In progress — date posted when Stage 2 is confirmed |
| ISO/IEC 42001 Lead Implementer (PECB) | Under consideration, Q2 2026 |

**Not** held and **not currently pursuing:**
- CMMC Registered Practitioner (RP) or any CMMC certification
- CISM / CISSP / PMP

We will update this README as credentials evolve.

---

## What this AIMS package is *not*

- **Not a portfolio of past client engagements.** 12th House AI is a new practice launching alongside this AIMS package. Client work will be reflected here as it is delivered, not before.
- **Not a Big-4 alternative.** We are deliberately small, founder-led, and SMB-rate-focused.
- **Not a CMMC offering.** We do not provide CMMC RP services.

---

## Contact

**Brannon Joseph Solomon Jr.** — Founder
📧 info@12thhouseai.com
🌐 [12thhouseai.com](https://12thhouseai.com)
📍 Hampton Roads, Virginia

---

*Documentation in this repository is published under the terms of the LICENSE file. Engagements with clients are governed by separate agreements.*
