# Risk Assessment — Benefits Policy Navigator
# Virginia Department of Social Services (VDSS)
# Assessment Date: June 2026 | Framework Version: 1.0

## System Identification

| Field | Value |
|-------|-------|
| System Name | Benefits Policy Navigator |
| Agency | Virginia Department of Social Services (VDSS) |
| System Type | GenAI — RAG-Based Policy Q&A |
| Assessment Date | June 2026 |
| Assessor | [AI Risk Analyst — complete at deployment] |
| Review Authority | VDSS Office of Technology Services + VITA |

---

## Risk Dimension Scoring

### Dimension 1: Decision Consequence

*What decisions does the system influence and how serious is an error?*

| Factor | Score (1–5) | Rationale |
|--------|:-----------:|-----------|
| Who is directly affected? | 3 | VDSS case workers (direct); citizens indirectly via case worker decisions |
| What decisions does the system influence? | 3 | Policy interpretation that informs — but does not make — eligibility determinations |
| Impact of an incorrect output | 3 | Incorrect policy guidance could contribute to a wrong eligibility determination; mitigated by mandatory human review |
| Reversibility of harm | 2 | Benefits decisions can be appealed and corrected; not immediate but not permanent |

**Dimension Score: 2.75 / 5**

---

### Dimension 2: Autonomy Level

*How much does the system act without human involvement?*

| Factor | Score (1–5) | Rationale |
|--------|:-----------:|-----------|
| Human involvement in decision | 1 | Case workers make all eligibility determinations; system is advisory only |
| Speed of consequential action | 1 | Policy queries are asynchronous; no automated downstream actions |
| Ability to override | 1 | Workers can ignore, flag, or override any AI response with no friction |
| Feedback mechanism | 2 | Per-response rating; flagged responses reviewed by policy team |

**Dimension Score: 1.25 / 5**

---

### Dimension 3: Data Sensitivity

*What data does the system process and how sensitive is it?*

| Factor | Score (1–5) | Rationale |
|--------|:-----------:|-----------|
| Data types processed | 2 | Policy documents (public/internal); client PII explicitly blocked from input |
| Regulatory classification | 2 | Internal COV data; not HIPAA-covered, not CUI, not classified |
| Volume | 2 | ~500 staff users; moderate query volume |
| Infrastructure exposure | 1 | All processing on COV-controlled Virginia-region infrastructure |

**Dimension Score: 1.75 / 5**

---

### Dimension 4: Scale and Reach

*How many people are affected directly or indirectly?*

| Factor | Score (1–5) | Rationale |
|--------|:-----------:|-----------|
| Number of direct users | 2 | ~500 VDSS case workers statewide |
| Number of people indirectly affected | 4 | VDSS serves ~800,000 Virginians receiving benefits annually |
| Geographic scope | 3 | Statewide — all VDSS local offices across 120+ locations |
| Concentration of impact | 2 | Distributed use; no single point of citizen impact |

**Dimension Score: 2.75 / 5**

---

### Dimension 5: Model Maturity and Novelty

*How well-understood is this AI approach in this context?*

| Factor | Score (1–5) | Rationale |
|--------|:-----------:|-----------|
| Technology novelty | 3 | GenAI/RAG is established technology but new to VDSS |
| Validation evidence | 2 | RAG well-validated in document Q&A; domain-specific policy validation required |
| Vendor maturity | 2 | Commercial LLM provider with enterprise government track record |
| Internal team capability | 3 | VDSS OTS has limited prior AI deployment experience |

**Dimension Score: 2.5 / 5**

---

## Overall Risk Score and Tier Assignment

| Dimension | Score | Weight | Weighted Score |
|-----------|:-----:|:------:|:--------------:|
| Decision Consequence | 2.75 | 25% | 0.69 |
| Autonomy Level | 1.25 | 25% | 0.31 |
| Data Sensitivity | 1.75 | 20% | 0.35 |
| Scale and Reach | 2.75 | 15% | 0.41 |
| Model Maturity / Novelty | 2.5 | 15% | 0.38 |
| **Composite Score** | | **100%** | **2.14 / 5** |

### **Assigned Tier: T2 (High Risk)**

**Rationale:** Composite score of 2.14 falls in the T2 range (2.0–3.0). The low autonomy score is the strongest mitigant — case workers retain all decision authority and the system cannot take actions on their behalf. The tier is driven upward by the indirect citizen reach: approximately 800,000 Virginians depend on case worker decisions that the system informs. That scale warrants the full T2 governance package despite the low data sensitivity and autonomy scores.

---

## Virginia-Specific Risk Factors

The following factors apply in addition to the base risk dimensions because this system is deployed by a Virginia executive branch agency subject to EO 30, EO 46, and VITA standards.

| Virginia Risk Factor | Assessment | Required Control |
|---------------------|:----------:|-----------------|
| EO 30 applicability | **Applies** — AI system used by a state agency in state operations | Register with VITA before production; complete annual compliance review |
| Prohibited use check (EO 30) | **Clear** — no autonomous citizen-affecting decisions; no biometric data; no law enforcement use | Document in deployment gate checklist |
| PRC-origin technology prohibition (EO 46) | **Pending verification** — must confirm all components are non-PRC origin | Verify at procurement; document in AI-BOM; block deployment if any component fails |
| VITA EA-225 registration | **Required** — system is an AI system on COV infrastructure | CTP/Planview registration before production |
| VITA Policy Standard | **Required** — agency-head approval mandatory | Deputy Commissioner sign-off before deployment |
| VITA IA security standards | **Required** — ITRM SEC 501-09, SEC 525-01, GOV 519-02 | Security assessment and penetration test before production |
| AI ethics training (VITA) | **Required** — all users must complete before access | Training completion tracked; access blocked until ≥90% completion |

---

## Required Controls Checklist — T2

| Control | Required for T2 | Status | Owner |
|---------|:---------------:|--------|-------|
| Risk assessment completed | Yes | **Complete** | AI Risk Analyst |
| Model card completed | Yes | **Complete** | AI Risk Analyst |
| Domain-specific evaluation suite executed | Yes | Not started | VDSS OTS |
| Hallucination rate measured on policy corpus | Yes | Not started | VDSS OTS |
| PII detection testing completed | Yes | Not started | Security team |
| Security review (VITA IA) | Yes | Not started | VITA / VDSS CISO |
| Penetration test completed | Yes | Not started | VITA IA |
| Vendor / DPA review completed | Yes | In progress | Legal / Procurement |
| EO 46 PRC-origin component verification | Yes | Not started | Procurement |
| Human oversight model documented | Yes | **Complete** | AI Risk Analyst |
| Fallback / graceful degradation procedure | Yes | Not started | VDSS OTS |
| Production monitoring plan operational | Yes | In design | VDSS OTS |
| VITA EO 30 registration | Yes | Not started | VDSS OTS |
| VITA CTP / Planview registration | Yes | Not started | VDSS OTS |
| Agency-head approval obtained | Yes | Not started | Deputy Commissioner |
| AI ethics training deployed to all users | Yes | Not started | VDSS OTS / HR |
| Quarterly review calendar entry created | Yes | Not started | AI Risk Analyst |

---

## Deployment Gate Decision

**Current Status: NOT APPROVED FOR PRODUCTION**

Outstanding blockers (must all be resolved before production):

1. Domain-specific evaluation suite not yet executed
2. Hallucination rate on Virginia policy corpus not measured
3. PII detection system not tested end-to-end
4. VITA security review and penetration test not completed
5. EO 46 PRC-origin verification not completed for all components
6. VITA EO 30 and CTP/Planview registration not submitted
7. Agency-head approval not obtained
8. AI ethics training not deployed to user population

**Estimated readiness for production gate review:** 60–90 days pending completion of above items.

---

## Residual Risks (Post-Controls)

| Risk | Likelihood | Impact | Residual Mitigation |
|------|:----------:|:------:|---------------------|
| Hallucinated or incorrect policy citation | Medium | High | RAG grounding + mandatory citation + quarterly audit + worker flagging |
| Knowledge base staleness | Medium | Medium | Monthly corpus refresh + staleness banner when corpus > 30 days old |
| PII leakage into queries | Low | High | Input PII scanner + user training + access blocked for untrained users |
| Case worker over-reliance on AI output | Medium | Medium | Training emphasizes advisory-only role; supervisors monitor for AI-attribution in case notes |
| Vendor model silent update changes behavior | Medium | Medium | Monthly behavioral regression test against fixed evaluation set |
| Corpus error (outdated or incorrect policy document) | Low | High | Policy team owns corpus; version control; worker flag mechanism surfaces errors within 5 days |

---

## Next Review

**Scheduled:** Quarterly — September 2026 (first post-deployment review)
**Mandatory early review triggers:**
- Hallucination rate exceeds 2% in any monthly audit
- Any PII detection alert fires in production
- Any corpus error confirmed by policy team
- Any VITA standard update affecting AI systems
- Any EO or legislative change affecting AI in Virginia state government
