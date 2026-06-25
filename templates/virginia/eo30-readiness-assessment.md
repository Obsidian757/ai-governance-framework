# Virginia AI Compliance Readiness Assessment

**Engagement type:** Commonwealth of Virginia AI Compliance Readiness Assessment
**Standard alignment:** Virginia Executive Order 30 (2024) · VITA Policy Standard for Utilization of AI by the Commonwealth (Rev 3, June 27 2024) · EA-225 Enterprise Solutions Architecture for AI (v1.2, Nov 16 2023) · Guidelines for AI Integration Throughout Education in Virginia (where applicable)
**Framework crosswalk:** `framework/compliance/virginia/eo-mapping.md` · `framework/compliance/virginia/vita-ea225-mapping.md` · `framework/compliance/virginia/vita-policy-standard-mapping.md`
**Prepared by:** \<Assessor name / organization>
**Agency / Entity:** \<COV agency, K-12 division, IHE, or vendor>
**Engagement period:** \<Start Date> – \<End Date>
**Report date:** \<YYYY-MM-DD>
**Version:** 1.0
**Classification:** \<Public / Internal / CUI — fill before transmission>

---

## How to use this template

This template shapes the deliverable for a Virginia EO 30 / VITA / EA-225 readiness assessment. It is designed for:

- **Executive-branch agencies** subject to Virginia EO 30 (VITA, DVS, VEC, DBHDS, VDOE, and others)
- **K-12 LEAs, VCCS colleges, and SCHEV-covered institutions** evaluating AI under the Virginia AI Education Guidelines
- **Vendors** preparing for eVA solicitations or AI-scoped Commonwealth cooperative master agreements who need to demonstrate EO 30 / VITA alignment in their response

Replace every `< >` placeholder. Delete instruction blocks (italicized) before delivering.

---

## 1. Executive Summary

*One page. Written last. Read first by the agency head or sponsor.*

- **Engagement driver:** \<EO 30 deadline · pending eVA response · audit finding · internal initiative>
- **Scope:** \<which programs / systems / vendor relationships>
- **Maturity (one-line):** \<Ad-hoc · Developing · Defined · Managed · Optimizing>
- **Agency-head approval status (EO 30 / VITA Policy Standard §III):** \<documented / partial / not documented>
- **VITA registration status (Archer + CTP/Planview):** \<not started · in progress · complete>
- **PRC-origin AI status (EO 46 / VITA procurement scope):** \<clear · flagged · unknown>
- **Top three findings:** \<bullet, plain English>
- **Top three recommendations:** \<bullet, with sequencing>

---

## 2. Scope and Methodology

### 2.1 In Scope

- AI systems / use cases: \<count + names>
- Frameworks evaluated: Virginia EO 30, EO 46, VITA AI Policy Standard (Rev 3), EA-225 (v1.2), AI Education Guidelines (if applicable), NIST AI RMF (as mapping backbone)
- Procurement vehicles in scope: \<eVA · cooperative master · direct buy · other>
- Spanberger administration successor standards: \<watch-only · actively in scope>

### 2.2 Out of Scope

- \<e.g., model performance benchmarking; agency-wide cybersecurity assessment>

### 2.3 Methodology

1. **Document review** — agency AI policies, AI procurement records, prior VITA submissions, vendor SSPs
2. **Stakeholder interviews** — Agency Head designee, AITR, ISO, procurement lead, program owners
3. **AI inventory build** — see Section 3 and `templates/ai-system-inventory.md` (root templates/)
4. **Control mapping** — mapped to `framework/compliance/virginia/` crosswalk files
5. **Gap analysis** — Section 4; scored by likelihood × impact
6. **Risk register** — Section 5

### 2.4 Limitations

- \<e.g., findings rely on agency representations; no independent technical testing of AI systems>
- \<e.g., VITA Archer / CTP-Planview records were reviewed via screenshots, not direct system access>
- \<e.g., EO 46 PRC-origin assessment is based on vendor-provided attestations>

---

## 3. AI System Inventory (Summary)

| # | System / Use Case | Purpose | Vendor or Internal | Data Class (COV) | Decision Type | EA-225 AI Category | Agency-Head Approval (EO 30) | Archer ID | CTP/Planview ID | PRC-Origin Clear (EO 46) |
|---|-------------------|---------|--------------------|------------------|---------------|--------------------|------------------------------|-----------|-----------------|--------------------------|
| 1 | \<name> | \<one-line> | \<vendor / internal> | \<Sensitive / Confidential / Restricted / Public> | \<Advisory / Automated / Hybrid> | \<Stand-alone / Embedded / Generative> | ☐ Yes ☐ No ☐ N/A | \<ID or None> | \<ID or None> | ☐ Yes ☐ No ☐ Unknown |
| 2 | | | | | | | | | | |
| 3 | | | | | | | | | | |

**Total AI systems identified:** \<n>
**Generative AI systems:** \<n>
**Systems with agency-head approval evidence:** \<n of n>
**Systems registered in VITA Archer:** \<n of n>
**Systems registered in CTP/Planview:** \<n of n>
**Systems with confirmed PRC-origin clearance (EO 46):** \<n of n>
**Systems with EA-225 decision-path logging in place:** \<n of n>

---

## 4. Compliance Gap Analysis

### 4.1 Virginia Executive Order 30 (January 18, 2024)

| EO 30 Directive | Requirement | Status | Evidence on Hand | Gap Description | Priority |
|-----------------|-------------|--------|------------------|-----------------|----------|
| Directive 1 — VITA Policy Standard | Adopt and enforce VITA AI Policy Standard across agency | ☐ Met ☐ Partial ☐ Not met | | | H/M/L |
| Directive 2 — EA-225 | Adopt and enforce VITA EA-225 AI IT Standards | ☐ Met ☐ Partial ☐ Not met | | | |
| Directive 3 — Education Guidelines | Apply AI Education Guidelines (K-12/IHE scope) | ☐ Met ☐ Partial ☐ N/A | | | |
| Directive 4 — Law Enforcement AI | Adopt AI standards for executive branch law enforcement (*Spanberger EO/Directive 2/4/2026 advances this*) | ☐ Met ☐ Partial ☐ N/A | | | |
| Directive 5 — AI Task Force | Participate / feed agency inputs to Task Force | ☐ Met ☐ Partial ☐ N/A | | | |
| Agency-head approval | Written approval documented before each AI deployment | ☐ Met ☐ Partial ☐ Not met | | | H/M/L |
| VITA registration | All AI use cases registered in Archer + CTP/Planview | ☐ Met ☐ Partial ☐ Not met | | | |

### 4.2 VITA Policy Standard for Utilization of AI by COV (Rev 3, June 27, 2024)

| Policy Standard Section | Requirement | Status | Gap | Priority |
|-------------------------|-------------|--------|-----|----------|
| Roles and responsibilities | Agency Head, AITR, ISO, Program Owner named and trained | ☐ Met ☐ Partial ☐ Not met | | |
| Acceptable / unacceptable use | Documented policy with training records | | | |
| Procurement and risk | AI-specific procurement language in vendor agreements | | | |
| Logging and registration | Archer + CTP/Planview entries current | | | |
| Generative AI controls | Gen-AI-specific guardrails documented | | | |
| Personal data protection | PII handling documented throughout AI lifecycle | | | |
| Public disclaimer | AI-generated outputs carry required disclosure | | | |
| Monitoring | Ongoing performance monitoring evidence | | | |

### 4.3 EA-225 Enterprise Solutions Architecture for AI (v1.2, November 16, 2023)

| EA-225 Requirement | Status | Evidence | Gap | Priority |
|--------------------|--------|----------|-----|----------|
| Conforms to Commonwealth security standards (ITRM SEC 501-09, SEC 525-01, SEC 528-02, GOV 519-02) | ☐ Met ☐ Partial ☐ Not met | | | H/M/L |
| Decision paths logged for traceability and replay | | | | |
| Monitoring metrics and thresholds defined | | | | |
| Model performance accuracy tracking in place | | | | |
| Training data sources inventoried and authorized | | | | |
| Third-party / embedded / generative AI components documented | | | | |
| AI system registered in CTP/Planview and Archer | | | | |

### 4.4 EO 46 — PRC-Origin AI Ban (February 11, 2025)

| EO 46 Requirement | Status | Evidence | Gap | Priority |
|-------------------|--------|----------|-----|----------|
| DeepSeek AI absent from Commonwealth devices and networks | ☐ Met ☐ Not met ☐ Unknown | | | H/M/L |
| Vendor AI stacks reviewed for PRC-origin model components | | | | |
| Procurement language includes foreign AI provenance requirement | | | | |
| Attestation process established for new AI vendor onboarding | | | | |

### 4.5 Guidelines for AI Integration Throughout Education in Virginia *(K-12 / VCCS / SCHEV only)*

| Guideline Area | Requirement | Status | Gap | Priority |
|----------------|-------------|--------|-----|----------|
| Human primacy in instruction | Human educators retain instructional authority; AI augments | ☐ Met ☐ Partial ☐ N/A | | |
| Student data privacy (FERPA + VCDPA) | AI tools configured to protect student PII | | | |
| Educator AI competency | Training program in place | | | |
| Bias and discriminatory outcome mitigation | Reviewed per tool | | | |
| Parental notice / consent (where applicable) | Process established | | | |
| Permissible classroom use policy | Published and enforced | | | |

---

## 5. Risk Register (Top Findings)

| # | Risk | System / Process | Likelihood | Impact | Score | Recommended Treatment | Owner | Target Date |
|---|------|------------------|------------|--------|-------|-----------------------|-------|-------------|
| R-01 | \<plain-English risk statement> | \<system or process> | L/M/H | L/M/H | | | \<role> | \<date> |
| R-02 | | | | | | | | |
| R-03 | | | | | | | | |
| R-04 | | | | | | | | |
| R-05 | | | | | | | | |

---

## 6. Maturity Assessment

Scale: **0** = Not started · **1** = Ad-hoc · **2** = Developing · **3** = Defined · **4** = Managed · **5** = Optimizing

| Capability Area | Score (0–5) | Rationale |
|-----------------|-------------|-----------|
| EO 30 awareness and adoption | | |
| Agency-head approval workflow | | |
| AI inventory completeness | | |
| VITA Archer / CTP-Planview hygiene | | |
| EA-225 instrumentation (logging, metrics) | | |
| EO 46 PRC-origin provenance controls | | |
| Procurement / vendor AI oversight | | |
| Generative AI guardrails | | |
| Education AI controls (if applicable) | | |
| Successor-standards tracking (Spanberger admin) | | |

**Overall maturity:** \<Ad-hoc · Developing · Defined · Managed · Optimizing>

---

## 7. Prioritized Recommendations

### Quick wins (0–30 days)

1. \<e.g., document agency-head approval for already-deployed systems retroactively — addresses EO 30 agency-head approval gap — effort: S — owner: AITR>

### Near-term (30–90 days)

1. \<e.g., register highest-risk AI systems in Archer and CTP/Planview>
2. \<e.g., implement decision-path logging for systems used in consequential decisions (EA-225 §x)>

### Strategic (90+ days)

1. \<e.g., stand up quarterly conformance review cadence aligned with VITA successor-standards tracking>
2. \<e.g., formalize vendor AI provenance attestation in all future procurement actions>

### Watch list (Spanberger administration)

- VITA may issue revised Policy Standard and EA-225 under new administration — monitor VITA IT governance publications
- Law enforcement AI standards (EO 30 Directive 4, advanced by Spanberger 2/4/2026 EO) — flag if agency scope includes public safety or law enforcement functions

---

## 8. Appendices

- **Appendix A:** Interview log (interviewee, role, date, key findings)
- **Appendix B:** Documents reviewed
- **Appendix C:** Full AI system inventory (expanded from Section 3)
- **Appendix D:** Full risk register
- **Appendix E:** Framework crosswalk — NIST AI RMF functions to Virginia requirements (see `framework/compliance/virginia/eo-mapping.md`)
- **Appendix F:** Primary source references
  - Virginia EO 30 (January 18, 2024)
  - Virginia EO 46 (February 11, 2025)
  - Spanberger AI EO + Directive (February 4, 2026)
  - VITA Policy Standard for Utilization of AI by COV (Rev 3, June 27, 2024)
  - VITA EA-225 Enterprise Solutions Architecture for AI (v1.2, November 16, 2023)
  - VITA ITRM SEC 501-09 (Information Security Standard)
  - VITA ITRM SEC 525-01 (Risk Management Standard)
  - VITA ITRM SEC 528-02 (Encryption Standard)
  - VITA ITRM GOV 519-02 (Privacy Standard)
  - Guidelines for AI Integration Throughout Education in Virginia (2024)

---

## Document Control

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 0.1 | \<date> | \<initials> | Draft |
| 1.0 | \<date> | \<initials> | Final delivery |

**Prepared by:** \<Name, Title, Organization>
**Contact:** \<email>
**Engagement governed by:** \<SOW reference / contract number>

---

*Currency: Virginia AI governance standards are evolving under the Spanberger administration (took office January 2026). Verify against current VITA publications before finalizing deliverables.*
