# AI Compliance Discovery Assessment — Template

**Engagement type:** Federal AI Compliance Discovery Assessment (Tier 1 — Discovery)
**Standard alignment:** ISO/IEC 42001:2023 · NIST AI RMF 1.0 · OMB M-25-21 · OMB M-25-22 · EO 14110
**Prepared by:** 12th House AI
**Client:** \<Organization Name>
**Engagement period:** \<Start Date> – \<End Date>
**Report date:** \<YYYY-MM-DD>
**Version:** 1.0
**Classification:** \<Public / Internal / CUI — fill before transmission>

---

## How to use this template

This is the deliverable shape for a 12th House AI Discovery Assessment. It is designed to be completed in 2–3 weeks against a single organization's AI footprint, and produces:

1. An **AI system inventory** (what AI is in use or planned),
2. A **gap analysis** against federal AI compliance requirements,
3. A **risk register** entry per system or per gap,
4. A **prioritized roadmap** the client can take to a Strategic Roadmap engagement (Tier 2) or implement themselves.

Replace every `< >` placeholder. Delete instruction blocks (italicized) before sending the deliverable.

---

## 1. Executive Summary

*One page. Written last. Read first by the executive sponsor.*

- **Why this assessment was commissioned:** \<the trigger — new federal AI requirement, audit finding, contract flow-down, internal initiative>
- **Scope:** \<which business units / systems / data domains>
- **Maturity (one-line):** \<one of: Ad-hoc · Developing · Defined · Managed · Optimizing — see §6>
- **Top three findings:** \<bullet, plain English>
- **Top three recommendations:** \<bullet, with sequencing>
- **Estimated effort to address:** \<rough order-of-magnitude, in hours / weeks / dollars>

---

## 2. Scope & Methodology

### 2.1 In Scope
- Business units: \<…>
- AI systems / use cases: \<count + names>
- Compliance frameworks evaluated: ISO/IEC 42001:2023, NIST AI RMF 1.0, OMB M-25-21, OMB M-25-22, EO 14110, \<other if applicable>
- Time period reviewed: \<dates>

### 2.2 Out of Scope
- \<e.g., security-control testing, code review, model performance audit>
- \<e.g., specific subsidiary or unit explicitly excluded by SOW>

### 2.3 Methodology
1. **Document review** — policies, AI usage logs, vendor contracts, data inventories
2. **Stakeholder interviews** — \<count> interviews across \<roles: CTO, CISO, AI/data leads, procurement, legal>
3. **System walkthroughs** — live demos or screen-shares of each in-scope AI system
4. **Inventory build** — populated via `templates/ai-system-inventory.md`
5. **Control mapping** — mapped to `docs/federal-compliance-mapping.md`
6. **Gap analysis** — populated via `templates/gap-analysis-template.md`
7. **Risk scoring** — likelihood × impact, recorded in client's risk register

### 2.4 Limitations
*Be explicit about what we did NOT verify.*
- \<e.g., we did not test model outputs for bias>
- \<e.g., findings are based on stakeholder representations — not independently audited>
- \<e.g., third-party AI vendor controls were reviewed via documentation only>

---

## 3. AI System Inventory (summary)

*Full inventory in companion workbook. Summary table here.*

| # | System Name | Purpose | Vendor / Build | Data Sensitivity | Decision Type | Status |
|---|-------------|---------|----------------|------------------|---------------|--------|
| 1 | \<name> | \<one-line purpose> | \<vendor or internal> | \<Public/Internal/CUI/PII/PHI> | \<Advisory/Automated/Hybrid> | \<In production / Pilot / Planned> |
| 2 | | | | | | |
| 3 | | | | | | |

**Total AI systems identified:** \<n>
**High-impact systems (per OMB M-25-21 definitions):** \<n>
**Systems lacking documented impact assessment:** \<n>

---

## 4. Compliance Gap Analysis

### 4.1 ISO/IEC 42001:2023 (selected clauses)

| Clause | Requirement (paraphrased) | Status | Evidence | Gap | Priority |
|--------|---------------------------|--------|----------|-----|----------|
| 4.1 | Organizational context | ☐ Met / ☐ Partial / ☐ Not met | | | H/M/L |
| 5.2 | AI policy | | | | |
| 6.1.2 | AI risk assessment | | | | |
| 6.1.4 | AI impact assessment | | | | |
| 7.2 | Competence | | | | |
| 8.2 | AI system impact assessment process | | | | |
| 9.2 | Internal audit | | | | |
| 9.3 | Management review | | | | |

### 4.2 NIST AI RMF (Govern / Map / Measure / Manage)

| Function | Category | Status | Gap | Priority |
|----------|----------|--------|-----|----------|
| GOVERN | GV.1 Policies & procedures | | | |
| GOVERN | GV.3 Roles & responsibilities | | | |
| MAP | MP.1 Context established | | | |
| MEASURE | MS.2 Evaluations | | | |
| MANAGE | MG.4 Continuous monitoring | | | |

### 4.3 OMB M-25-21 / M-25-22 (federal applicability)

*Use only if the client is a federal agency or a contractor with M-25-21/-22 flow-down obligations.*

| Requirement | Applies? | Status | Gap | Priority |
|-------------|----------|--------|-----|----------|
| Chief AI Officer designation (M-25-21) | ☐ Y / ☐ N | | | |
| AI use-case inventory (M-25-21) | | | | |
| Rights-impacting / safety-impacting determination | | | | |
| AI acquisition planning (M-25-22) | | | | |
| Vendor-supplied AI documentation | | | | |

---

## 5. Risk Register (top findings)

| # | Risk | System / Process | Likelihood | Impact | Score | Mitigation Owner | Target Date |
|---|------|------------------|------------|--------|-------|------------------|-------------|
| R-01 | \<plain-English risk statement> | \<system> | L/M/H | L/M/H | \<L×I> | \<role> | \<date> |
| R-02 | | | | | | | |
| R-03 | | | | | | | |

Full risk register delivered separately using the client's existing format, or starting from `docs/risk-register.md`.

---

## 6. Maturity Assessment

Score each capability area 0–4 (Ad-hoc → Optimizing). Plot on a radar chart in the report.

| Capability | Score (0-4) | Notes |
|------------|-------------|-------|
| AI governance & policy | | |
| AI inventory & classification | | |
| AI risk management | | |
| AI impact assessment | | |
| Vendor / third-party AI oversight | | |
| Workforce competence | | |
| Monitoring & incident response | | |
| Management review & continuous improvement | | |

**Overall maturity rating:** \<Ad-hoc · Developing · Defined · Managed · Optimizing>

---

## 7. Prioritized Recommendations

### 7.1 Quick Wins (≤ 30 days)
1. \<recommendation> — addresses \<gap or risk> — effort: \<S/M/L> — owner: \<role>

### 7.2 Near-term (30–90 days)
1. …

### 7.3 Strategic (90+ days)
1. …

### 7.4 Suggested Next Engagement
*Optional — only if the client has signaled interest in continued work. Do not push.*
- **Tier 2 — Strategic Roadmap:** 90-day implementation plan, governance documentation set, AIMS scaffolding aligned to ISO/IEC 42001.
- **Tier 3 — Ultimate Warrior:** Six-month engagement supporting full ISO 42001 implementation toward certification readiness.
- Pricing for any next-tier engagement is provided in a follow-on statement of work.

---

## 8. Appendices

- **Appendix A:** Interview list and dates
- **Appendix B:** Documents reviewed
- **Appendix C:** Full AI system inventory (workbook)
- **Appendix D:** Full risk register
- **Appendix E:** Glossary of terms
- **Appendix F:** References (regulations, standards, agency guidance)

---

## Document control

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 0.1 | \<date> | \<initials> | Draft |
| 1.0 | \<date> | \<initials> | Final delivery |

**Prepared by:** Brannon Joseph Solomon Jr., Founder, 12th House AI
**Contact:** info@12thhouseai.com
**Engagement governed by:** \<SOW reference / contract number>
