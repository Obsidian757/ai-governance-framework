# Virginia AI Education Guidelines — Framework Mapping

## Overview

The "Guidelines for AI Integration Throughout Education in Virginia" (Office of the Secretary of Education, 2024) apply to K-12 local education agencies (LEAs), Virginia Community College System (VCCS) institutions, and four-year institutions covered by the State Council of Higher Education for Virginia (SCHEV). They do not carry the legal force of the EOs or VITA standards — they are state-level guidance — but COV-categorized educational institutions are expected to align their AI policies with these guidelines and to register AI tools through CTP/Planview consistent with EO 30 requirements.

The guidelines rest on a foundational principle: education is ultimately a human endeavor. AI may augment instructional processes, administrative efficiency, and student support — it does not replace teachers, instructors, or the judgment of education professionals.

---

## Scope

| Institution Type | Applicability |
|---|---|
| K-12 Local Education Agencies (LEAs) | Full scope; Superintendents bear primary accountability |
| Virginia Community College System (VCCS) | Full scope; Presidents and Provosts bear primary accountability |
| SCHEV-covered four-year institutions | Full scope for COV-managed systems; public institutions have additional VITA obligations |
| Private colleges and universities | Guidance only; no enforcement mechanism except where federal funding conditions apply |
| Charter schools and lab schools | Follow applicable LEA requirements |

---

## Stakeholder Roles

| Role | Accountability |
|---|---|
| Superintendent / Division Superintendent | AI policy adoption, approval of high-impact AI tools, annual reporting |
| President / Provost (higher ed) | AI governance structure, faculty senate engagement, data stewardship |
| Principal / Dean | School-level implementation, educator training compliance, student disclosure |
| Teacher / Faculty Member | Instructional authority over AI-assisted tasks; competency maintenance; bias monitoring in use |
| Student | Responsible use per institution policy; digital literacy development |
| Division / Institutional Technology Coordinator | Tool procurement, CTP registration, data privacy review, vendor assessment |
| Data Privacy Officer (where designated) | FERPA, COPPA, VCDPA compliance for AI-processed student data |

---

## Guideline Principles and Framework Control Mapping

| Education Guideline | Framework Control | Reference | Implementation Evidence |
|---|---|---|---|
| Education is a human endeavor — AI augments, does not replace, educators | Human-in-the-loop: educator retains instructional authority and final judgment | [human-in-loop-patterns.md](../../../responsible-ai/human-in-loop-patterns.md) | Documented instructional workflow showing human review before AI-generated content affects student assessment or grading |
| Responsible student use and digital literacy | Transparency: students informed of AI involvement in tools they interact with | [transparency-standards.md](../../../responsible-ai/transparency-standards.md) | Student-facing disclosure language in tool UI; AI literacy curriculum documentation |
| Mitigation of bias and discriminatory outcomes | Bias detection: pre-deployment demographic parity testing; ongoing monitoring for differential outcomes | [bias-detection-llm.md](../../../responsible-ai/bias-detection-llm.md) | Bias assessment report pre-deployment; quarterly disaggregated output review by demographic group |
| Student data privacy (FERPA, COPPA, VCDPA) | PII minimization: restrict training and inference data to minimum necessary; data residency controls | [data-residency-llm.md](../../data-residency-llm.md) | DPA with vendor; FERPA records designation; no student PII in model training without consent |
| Educator competency in AI | Role competency: educators who deploy or supervise AI tools demonstrate baseline AI literacy | [roles-genai.md](../../../operating-model/roles-genai.md) | Completed training log; competency attestation; professional development calendar |
| Registration of AI tools via CTP/Planview | Governance intake: all AI tools registered before deployment | [governance-workflow.md](../../../governance-operations/governance-workflow.md) | CTP/Planview confirmation; EO 30 Superintendent/President approval memo |
| Accountability for AI-assisted decisions affecting students | Audit trail: log AI-generated recommendations that inform high-stakes decisions | [audit-trail-requirements.md](../../audit-trail-requirements.md) | Immutable log of AI output used in student decision context; retention per FERPA schedule |
| Equity of access and outcomes | Fairness: AI tools must not create or amplify access disparities across student demographics | [bias-detection-llm.md](../../../responsible-ai/bias-detection-llm.md) | Access equity report; disaggregated usage and outcome data |
| Age-appropriate AI use | Risk tier elevation: AI tools used with minors classified at minimum T2 | [risk-matrix.md](../../../risk-classification/risk-matrix.md) | Risk assessment showing minor-user flag and corresponding governance controls |
| Continuous review and adaptation | Review cadence: AI tools in educational settings reviewed at least annually | [review-cadence.md](../../../operating-model/review-cadence.md) | Annual review documentation; change notification protocol with vendor |

---

## Human-in-the-Loop Requirements for Education Contexts

The framework's [human-in-loop-patterns.md](../../../responsible-ai/human-in-loop-patterns.md) defines three oversight levels. Educational AI deployments map as follows:

| Use Case | Required Oversight Level | Rationale |
|---|---|---|
| AI-assisted grading or scoring of student work | Level 1 — Human reviews every AI output before it affects the student record | High-stakes; direct impact on student standing; FERPA record implication |
| AI tutoring or adaptive learning tools | Level 2 — Human monitors aggregate outputs; individual session review on exception | Lower stakes per interaction; teacher retains curriculum authority |
| AI-generated instructional content used in classroom | Level 2 — Educator reviews AI draft before delivery | Educator instructional authority; bias risk in content framing |
| Administrative AI (scheduling, resource allocation) | Level 2 or Level 3 — Depends on whether outputs affect individual students | If output affects individual student placement, escalate to Level 1 |
| Predictive analytics for at-risk student identification | Level 1 — Counselor reviews every flagged student before intervention | High sensitivity; potential bias in demographic proxies; legal risk |
| AI-assisted admissions screening | Level 1 — Admissions officer reviews every AI-influenced recommendation | HB 2094 high-risk category analogue; equity and legal exposure |

**Non-delegable decisions.** The following may not be primarily determined by an AI system:
- Final grade assignment
- Student discipline determination
- Special education eligibility determination
- Expulsion or suspension recommendation
- IEP goal-setting

---

## Student Data Privacy Controls

### Applicable Legal Framework

| Regulation | Scope | Key Obligation |
|---|---|---|
| FERPA (20 U.S.C. § 1232g) | All LEAs and SCHEV institutions receiving federal funding | Student education records protected; vendor must qualify as school official with legitimate educational interest |
| COPPA (15 U.S.C. § 6501) | AI tools used with children under 13 | Verifiable parental consent before collecting personal information |
| VCDPA (Va. Code § 59.1-575 et seq.) | Controllers processing personal data of Virginia residents | Data minimization; purpose limitation; no sale of student data; opt-out for profiling |
| PPRA (20 U.S.C. § 1232h) | Surveys and data collection in K-12 | Parental notification and consent for certain data collection activities |

### Required EdTech Vendor Contract Provisions

1. Data processing agreement (DPA) designating vendor as school official under FERPA with documented legitimate educational interest
2. No-training clause prohibiting use of student data to train or improve AI models without explicit written institutional consent
3. Data residency commitment — student PII stored in the United States; no PRC-origin processing (EO 26)
4. Retention and deletion schedule aligned with the institution's FERPA records retention policy; deletion verified in writing upon contract termination
5. Breach notification within 72 hours of discovery (Va. Code § 18.2-186.6)
6. Sub-processor disclosure — complete list with institution approval required before adding new sub-processors

---

## Educator Competency Tiers

| Tier | Description | Who Needs It | Evidence |
|---|---|---|---|
| A — Awareness | Understands what AI tools do, their limitations, and the institution's AI policy | All staff in contact with students | Completed AI policy attestation |
| B — User Competency | Can responsibly operate AI tools; recognizes and escalates anomalous or biased outputs | Teachers, counselors, administrators using AI tools | Tool-specific training completion; supervisor attestation |
| C — Coordinator Competency | Can assess AI tools for procurement, conduct bias review, manage CTP registration, advise colleagues | Division/institutional technology coordinators | Training log plus practical assessment; annual recertification |
| D — Governance Lead | Responsible for institutional AI policy, vendor oversight, FERPA compliance, annual reporting | CTO/CIO, Data Privacy Officer, designated AI lead | Formal role designation; participation in COV AI governance working groups |

---

## Vendor Checklist for EdTech AI Sales in Virginia

**Legal and Compliance**
- [ ] Product qualifies as a "school official" under FERPA, or alternative lawful basis documented
- [ ] COPPA compliance documentation available if product accessible to children under 13
- [ ] VCDPA data processing terms included in standard contract or available as addendum
- [ ] No PRC-origin AI components (EO 26) — country of origin for all AI model providers documented
- [ ] No student data used for commercial advertising or model training without institutional consent
- [ ] Sub-processor list current and available for institutional review
- [ ] U.S.-only data residency confirmed, or written exception approved by institution

**Virginia-Specific Gates**
- [ ] Product supports CTP/Planview registration workflow (EA-225 requirement for COV institutions)
- [ ] EO 30 Superintendent/President approval process supported — documentation available
- [ ] Product procurable via eVA or an existing COV cooperative vehicle; eVA vendor registration current
- [ ] SWaM certification held or prime contractor holds SWaM-eligible teaming arrangement (if applicable)

**Bias and Fairness**
- [ ] Pre-release bias assessment conducted covering race, gender, disability status, and English learner status; report available
- [ ] Ongoing bias monitoring commitment documented; customer notification process for material model changes

**Human-in-the-Loop**
- [ ] Product design preserves educator instructional authority — no fully automated grading, discipline, or placement decisions
- [ ] Product provides override mechanism and audit log of AI-generated recommendations
- [ ] AI involvement disclosed to end users (students and parents) in product UI

**Data Privacy and Security**
- [ ] DPA template available with FERPA school-official language
- [ ] 72-hour breach notification SLA committed in contract
- [ ] Alignment with VITA IA standards (SEC 501-09, SEC 525-01) — security assessment available

---

## Cross-References

- [eo-mapping.md](eo-mapping.md) — EO 30 agency-head approval requirements apply to educational institutions
- [vita-ea225-mapping.md](vita-ea225-mapping.md) — CTP/Planview registration for COV-managed educational systems
- [vita-ia-standards.md](vita-ia-standards.md) — IA security standards applicable to school division IT systems
- [vita-policy-standard-mapping.md](vita-policy-standard-mapping.md) — AI Utilization Policy Standard applies to VITA-connected educational institutions
- [../audit-trail-requirements.md](../audit-trail-requirements.md) — Audit trail for student-affecting AI decisions
- [../../../responsible-ai/bias-detection-llm.md](../../../responsible-ai/bias-detection-llm.md) — Bias detection methodology for educational AI tools
- [../../../responsible-ai/human-in-loop-patterns.md](../../../responsible-ai/human-in-loop-patterns.md) — Human oversight levels and non-delegable decision categories

---

*Source: "Guidelines for AI Integration Throughout Education in Virginia," Office of the Secretary of Education, Commonwealth of Virginia, 2024. Mapping maintained as part of the 12th House AI Governance Framework — Virginia compliance module.*
