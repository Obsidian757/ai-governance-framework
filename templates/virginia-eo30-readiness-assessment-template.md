# Virginia AI Compliance Readiness Assessment — Template

**Engagement type:** Commonwealth of Virginia AI Compliance Readiness Assessment
**Standard alignment:** Virginia Executive Order 30 (2024) · VITA Policy Standard for Utilization of AI by the Commonwealth (Rev 3, June 27 2024) · EA-225 Enterprise Solutions Architecture for AI (v1.2, Nov 16 2023) · Guidelines for AI Integration Throughout Education in Virginia (where applicable)
**Crosswalk reference:** `docs/virginia-compliance-mapping.md`
**Prepared by:** 12th House AI
**Agency / Entity:** \<COV agency, K-12 division, IHE, or vendor>
**Engagement period:** \<Start Date> – \<End Date>
**Report date:** \<YYYY-MM-DD>
**Version:** 1.0
**Classification:** \<Public / Internal / CUI — fill before transmission>

---

## How to use this template

This is the deliverable shape for a 12th House AI Virginia EO-30 / VITA / EA-225 readiness assessment. It is designed for:

- **Executive-branch agencies** subject to Virginia EO-30 (VITA, DVS, VEC, DBHDS, VDOE, and others),
- **K-12 LEAs, VCCS colleges, and SCHEV-covered institutions** evaluating AI under the Virginia AI Education Guidelines,
- **Vendors** preparing for eVA solicitations or AI-scoped Commonwealth cooperative master agreements who need to demonstrate EO-30 / VITA alignment in their response.

Replace every `< >` placeholder. Delete instruction blocks (italicized) before sending the deliverable.

---

## 1. Executive Summary

*One page. Written last. Read first by the agency head or sponsor.*

- **Engagement driver:** \<EO-30 deadline · pending eVA response · audit finding · internal initiative>
- **Scope:** \<which programs / systems / vendor relationships>
- **Maturity (one-line):** \<Ad-hoc · Developing · Defined · Managed · Optimizing>
- **Agency-head approval status (EO-30 §6 / VITA Policy Standard §III):** \<documented / partial / not documented>
- **VITA registration status (Archer + CTP/Planview):** \<not started · in progress · complete>
- **Top three findings:** \<bullet, plain English>
- **Top three recommendations:** \<bullet, with sequencing>

---

## 2. Scope & Methodology

### 2.1 In Scope
- AI systems / use cases: \<count + names>
- Frameworks evaluated: Virginia EO-30, VITA AI Policy Standard, EA-225, AI Education Guidelines (if applicable), ISO/IEC 42001:2023 (where mapped)
- Procurement vehicles in scope: \<eVA · cooperative master · other>

### 2.2 Out of Scope
- \<e.g., model performance audit; agency-wide cybersecurity review>

### 2.3 Methodology
1. **Document review** — agency AI policies, AI procurement records, prior VITA submissions, vendor SSPs
2. **Stakeholder interviews** — Agency Head designee, AITR, ISO, procurement lead, program owners
3. **AI inventory build** — populated via `templates/ai-system-inventory.md`
4. **Control mapping** — mapped to `docs/virginia-compliance-mapping.md`
5. **Gap analysis** — populated via `templates/gap-analysis-template.md`
6. **Risk scoring** — likelihood × impact

### 2.4 Limitations
- \<e.g., findings rely on agency representations; no independent testing>
- \<e.g., VITA Archer / CTP-Planview records were reviewed via screenshots, not direct access>

---

## 3. AI System Inventory (summary)

| # | System / Use Case | Purpose | Vendor or Internal | Data Class (per COV) | Decision Type | EA-225 Classification | Agency-Head Approval (EO-30) | VITA Registration |
|---|-------------------|---------|--------------------|----------------------|---------------|-----------------------|------------------------------|-------------------|
| 1 | \<name> | \<one-line> | \<vendor> | \<Sensitive / Confidential / Restricted / Public> | \<Advisory / Automated / Hybrid> | \<Type per EA-225 v1.2> | ☐ Yes / ☐ No / ☐ N/A | \<Archer ID · CTP ID · None> |
| 2 | | | | | | | | |
| 3 | | | | | | | | |

**Total AI systems identified:** \<n>
**Generative AI systems:** \<n>
**Systems with agency-head approval evidence (EO-30 §6):** \<n>
**Systems registered in VITA Archer:** \<n>
**Systems with EA-225 instrumentation in place:** \<n>

---

## 4. Compliance Gap Analysis — Commonwealth of Virginia

### 4.1 Virginia Executive Order 30 (2024)

| EO-30 Section | Requirement (paraphrased) | Status | Evidence | Gap | Priority |
|---------------|---------------------------|--------|----------|-----|----------|
| §3 — VITA Policy Standard adoption | Adopt and apply | ☐ Met / ☐ Partial / ☐ Not met | | | H/M/L |
| §4 — IT Advisory Council role | Recognize and feed | | | | |
| §5 — Critical decision systems | Identify and govern | | | | |
| §6 — Agency-head approval | Document approval for each AI deployment | | | | |
| §7 — Education AI guidance | Adopt where applicable (K-12 / IHE / SCHEV) | | | | |
| §8 — Generative AI standards | Apply standards | | | | |

### 4.2 VITA Policy Standard for Utilization of AI by COV (Rev 3, June 27 2024)

| Policy Section | Requirement | Status | Gap | Priority |
|----------------|-------------|--------|-----|----------|
| §III — Roles & responsibilities | Agency Head, AITR, ISO, program owner | | | |
| §IV — Acceptable / unacceptable use | Defined and trained | | | |
| §V — Procurement & risk | AI-specific procurement clauses | | | |
| §VI — Logging & registration | Archer + CTP/Planview entries | | | |
| §VII — Generative AI | Specific Gen-AI controls | | | |
| §VIII — Monitoring | Ongoing monitoring evidence | | | |

### 4.3 EA-225 Enterprise Solutions Architecture for AI (v1.2, Nov 16 2023)

| EA-225 Element | Requirement | Status | Gap | Priority |
|----------------|-------------|--------|-----|----------|
| AI system classification | System mapped to EA-225 category | | | |
| Reference architecture conformance | Conforms to v1.2 patterns | | | |
| Instrumentation plan | Logging, metrics, drift detection | | | |
| Data lineage | Sources documented and authorized | | | |
| Successor-standards tracking | Process for v1.3+ adoption | | | |

### 4.4 Guidelines for AI Integration Throughout Education in Virginia *(K-12 / VCCS / SCHEV only)*

| Guideline Area | Requirement | Status | Gap | Priority |
|----------------|-------------|--------|-----|----------|
| Student data protections (FERPA + VA) | | | | |
| Educator AI literacy | | | | |
| Permissible classroom uses | | | | |
| Assessment integrity | | | | |
| Parental notice / consent | | | | |

*Note: The Public Safety Homeland Security AI standards required under EO-30 were not published on schedule by the prior administration; if the engagement touches law-enforcement use cases, flag this as a successor-standards watch item.*

---

## 5. Risk Register (top findings)

| # | Risk | System / Process | Likelihood | Impact | Score | Mitigation Owner | Target Date |
|---|------|------------------|------------|--------|-------|------------------|-------------|
| R-01 | \<plain-English risk statement> | \<system> | L/M/H | L/M/H | \<L×I> | \<role> | \<date> |
| R-02 | | | | | | | |
| R-03 | | | | | | | |

---

## 6. Maturity Assessment

| Capability | Score (0-4) | Notes |
|------------|-------------|-------|
| EO-30 awareness and adoption | | |
| Agency-head approval workflow | | |
| AI inventory completeness | | |
| VITA Archer / CTP-Planview hygiene | | |
| EA-225 instrumentation | | |
| Procurement / vendor AI oversight | | |
| Generative-AI guardrails | | |
| Successor-standards tracking | | |

**Overall maturity rating:** \<Ad-hoc · Developing · Defined · Managed · Optimizing>

---

## 7. Prioritized Recommendations

### 7.1 Quick Wins (≤ 30 days)
1. \<e.g., document agency-head approval for already-deployed systems> — addresses \<EO-30 §6 gap> — effort: S — owner: \<role>

### 7.2 Near-term (30–90 days)
1. \<e.g., register two highest-risk systems in Archer + CTP-Planview>

### 7.3 Strategic (90+ days)
1. \<e.g., stand up quarterly conformance review aligned with VITA successor standards>

### 7.4 Suggested Next Engagement
*Optional. Only if the client has signaled interest.*
- **VITA Approval & Registration Sprint:** Archer + CTP/Planview registration, agency-head approval evidence packet, EA-225 instrumentation plan.
- **Ongoing Quarterly Conformance:** Periodic conformance review and successor-standards tracking.
- Pricing for any next-tier engagement is provided in a follow-on statement of work.

---

## 8. Appendices

- **Appendix A:** Interview list and dates
- **Appendix B:** Documents reviewed (including agency policies, vendor SSPs, prior VITA submissions)
- **Appendix C:** Full AI system inventory
- **Appendix D:** Full risk register
- **Appendix E:** Crosswalk to ISO/IEC 42001:2023 (cross-reference to `docs/virginia-compliance-mapping.md`)
- **Appendix F:** Reference texts (EO-30, VITA Policy Standard Rev 3, EA-225 v1.2, AI Education Guidelines)

---

## Document control

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 0.1 | \<date> | \<initials> | Draft |
| 1.0 | \<date> | \<initials> | Final delivery |

**Prepared by:** Brannon Joseph Solomon Jr., Founder, 12th House AI
**Contact:** info@12thhouseai.com
**Engagement governed by:** \<SOW reference / contract number>
