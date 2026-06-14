# Virginia AI Executive Orders — Framework Mapping

## Overview

This document maps Virginia's AI-related Executive Orders and related legislative instruments to the controls in this governance framework. It is intended for practitioners deploying AI systems within, or selling AI services to, Virginia Commonwealth of Virginia (COV) executive branch agencies and localities.

The mapping follows two axes: (1) specific framework controls by directory, and (2) NIST AI RMF functions (GOVERN / MAP / MEASURE / MANAGE), which Virginia VITA EA-225 and state procurement officers increasingly use as a shared vocabulary for AI governance requirements.

---

## Virginia AI Regulatory Instruments — Status Table

| Instrument | Type | Signed | Status | Scope |
|---|---|---|---|---|
| Executive Order 30 (Youngkin) | Executive Order | January 18, 2024 | **Active** | All COV executive branch agencies + procurement vendors |
| Executive Order 26 (Youngkin) | Executive Order | February 11, 2025 | **Active** — supersedes informal guidance | All COV devices, networks, and vendor solutions |
| VITA Policy Standard (EA-225) | IT Standard | Issued under EO 30, Directive 2 | **Active** — revision expected 2026 | COV agencies and technology vendors |
| VITA AI Policy Standard | Policy Standard | Issued under EO 30, Directive 1 | **Active** — revision expected 2026 | COV agencies and technology vendors |
| EO + Directive (Spanberger, Feb 4 2026) | Executive Order + Directive | February 4, 2026 | **Active** — successor to EO 30 Directive 4 | Law enforcement AI; broader COV AI posture updates in progress |
| HB 2094 (2025 Session) | Legislation | Vetoed March 24, 2025 | **Not in force** | Would have covered "high-risk AI" deployers statewide |

---

## EO 30 — Youngkin AI Safeguards Order (January 18, 2024)

### Background

Executive Order 30, signed January 18, 2024, directed five actions to establish safeguards for AI use across the Commonwealth's executive branch. It applies directly to COV agencies and extends procurement obligations to vendors providing AI-enabled solutions through state contracts, including eVA, cooperative master agreements, and direct buys subject to COV IT standards.

### EO 30 — Directive 1: VITA AI Policy Standards

Directive 1 required VITA to develop and publish AI policy standards addressing agency use of AI tools, ethical principles, and employee conduct.

| EO 30 Requirement | Framework Control | NIST AI RMF | Reference |
|---|---|---|---|
| Ethical use principles for AI — prohibit use that discriminates, manipulates, or violates civil liberties | Responsible AI standards; bias detection protocols | GOVERN (GV.1, GV.4) | [responsible-ai/bias-detection-llm.md](../../responsible-ai/bias-detection-llm.md), [responsible-ai/transparency-standards.md](../../responsible-ai/transparency-standards.md) |
| Agency-head approval required before deploying AI in decision-support roles | Deployment gates; T1/T2 risk tier controls requiring executive sign-off | GOVERN (GV.2); MANAGE (MG.2) | [llm-lifecycle/deployment-gates.md](../../llm-lifecycle/deployment-gates.md), [risk-classification/risk-matrix.md](../../risk-classification/risk-matrix.md) |
| Mandatory public disclaimer on AI-generated outputs delivered to citizens | Output transparency requirements; hallucination policy disclosures | GOVERN (GV.1); MAP (MP.5) | [responsible-ai/transparency-standards.md](../../responsible-ai/transparency-standards.md), [responsible-ai/hallucination-policy.md](../../responsible-ai/hallucination-policy.md) |
| Personal data protection — restrict AI systems from ingesting PII beyond operational necessity | Data minimization controls in LLM deployment; RAG governance data scoping | MAP (MP.4); MEASURE (MS.3) | [llm-lifecycle/rag-governance.md](../../llm-lifecycle/rag-governance.md), [compliance/data-residency-llm.md](../data-residency-llm.md) |
| AI use must align with COV Enterprise Architecture policies | EA-225 alignment built into model selection and lifecycle gates | GOVERN (GV.5) | [llm-lifecycle/model-selection.md](../../llm-lifecycle/model-selection.md) |

### EO 30 — Directive 2: VITA AI IT Standards (EA-225)

Directive 2 required VITA to publish technology standards under the Commonwealth's Enterprise Architecture. VITA EA-225 is the operational output: it specifies registration, documentation, and lifecycle requirements for AI systems deployed by COV agencies.

| EO 30 / EA-225 Requirement | Framework Control | NIST AI RMF | Reference |
|---|---|---|---|
| Register all AI deployments in Archer GRC and CTP/Planview portfolio tool before go-live | System inventory and pre-deployment governance registration; control-register integration | GOVERN (GV.5); MAP (MP.2) | [governance-operations/control-register.md](../../governance-operations/control-register.md), [operating-model/grc-integration.md](../../operating-model/grc-integration.md) |
| Risk assessment required for each AI system prior to deployment | Risk classification assessment using framework risk matrix; T1–T4 tier determination | MAP (MP.1, MP.2, MP.4) | [risk-classification/risk-matrix.md](../../risk-classification/risk-matrix.md), [risk-classification/genai-risk-matrix.md](../../risk-classification/genai-risk-matrix.md) |
| Ongoing monitoring obligations — agencies must monitor AI systems post-deployment | LLM production monitoring; drift detection; escalation thresholds | MEASURE (MS.3, MS.4) | [llm-lifecycle/monitoring.md](../../llm-lifecycle/monitoring.md), [model-lifecycle/monitoring.md](../../model-lifecycle/monitoring.md) |
| Documentation of AI system purpose, data inputs, outputs, and human oversight level | Model card / system card documentation; impact assessment template | MAP (MP.1, MP.3) | [compliance/audit-trail-requirements.md](../audit-trail-requirements.md) |
| Human oversight commensurate with risk tier | Human-in-the-loop patterns matched to risk classification; HITL controls for T1/T2 systems | MANAGE (MG.2) | [responsible-ai/human-in-loop-patterns.md](../../responsible-ai/human-in-loop-patterns.md), [risk-classification/risk-matrix.md](../../risk-classification/risk-matrix.md) |
| Incident reporting to VITA for AI-related failures or adverse outcomes | Incident forensics and escalation path protocols; board-level notification thresholds | MANAGE (MG.3, MG.4) | [operating-model/incident-forensics.md](../../operating-model/incident-forensics.md), [operating-model/escalation-paths.md](../../operating-model/escalation-paths.md) |
| Third-party AI vendor assessment — agencies must assess vendor AI governance before procurement | Third-party model risk framework; supply chain security requirements | MAP (MP.4); MANAGE (MG.2) | [compliance/third-party-model-risk.md](../third-party-model-risk.md), [ai-security/supply-chain-security.md](../../ai-security/supply-chain-security.md) |

### EO 30 — Directive 3: AI Education Guidelines

Directive 3 required VITA and the Department of Human Resource Management (DHRM) to develop AI education and training guidelines for COV employees.

| EO 30 Requirement | Framework Control | NIST AI RMF | Reference |
|---|---|---|---|
| AI literacy training for agency staff prior to AI tool deployment | Governance training as a deployment gate condition; workforce AI literacy KPI | GOVERN (GV.3) | [operating-model/governance-metrics.md](../../operating-model/governance-metrics.md), [llm-lifecycle/deployment-gates.md](../../llm-lifecycle/deployment-gates.md) |
| Role-based guidance for AI users vs. AI system administrators | RACI matrices differentiate user roles, admin roles, and oversight roles | GOVERN (GV.2) | [operating-model/roles-responsibilities.md](../../operating-model/roles-responsibilities.md), [operating-model/roles-genai.md](../../operating-model/roles-genai.md) |
| Documentation of responsible use guidelines accessible to all staff | Responsible AI checklist and transparency standards published to user-facing documentation | GOVERN (GV.1) | [compliance/responsible-ai-checklist.md](../responsible-ai-checklist.md) |

### EO 30 — Directive 4: Law Enforcement AI Standards (October 2024 Deadline — Not Met)

Directive 4 required the Secretary of Public Safety and Homeland Security to establish AI standards for law enforcement use of AI by October 2024. The Youngkin administration did not meet this deadline. This obligation was carried forward and addressed by the Spanberger administration in February 2026 (see Section 4 below).

| EO 30 Requirement | Framework Control | NIST AI RMF | Reference |
|---|---|---|---|
| Risk classification for law enforcement AI use cases (facial recognition, predictive policing, surveillance) | Agentic AI risk matrix; T1 classification for consequential law enforcement decisions | MAP (MP.2, MP.4, MP.5) | [risk-classification/agentic-ai-risk.md](../../risk-classification/agentic-ai-risk.md), [risk-classification/risk-matrix.md](../../risk-classification/risk-matrix.md) |
| Bias and fairness testing for law enforcement AI models | Bias detection LLM protocols; red-teaming for adversarial fairness | MEASURE (MS.1, MS.2) | [responsible-ai/bias-detection-llm.md](../../responsible-ai/bias-detection-llm.md), [ai-security/red-teaming-protocol.md](../../ai-security/red-teaming-protocol.md) |
| Mandatory human review before any adverse action derived from AI output | Human-in-the-loop patterns for T1 systems; human override as hard requirement | MANAGE (MG.2) | [responsible-ai/human-in-loop-patterns.md](../../responsible-ai/human-in-loop-patterns.md) |
| Audit trail for all law enforcement AI decisions | Audit trail requirements; prompt audit trail for LLM-based systems | MANAGE (MG.4) | [compliance/audit-trail-requirements.md](../audit-trail-requirements.md), [compliance/prompt-audit-trail.md](../prompt-audit-trail.md) |

### EO 30 — Directive 5: AI Task Force

Directive 5 established the Virginia AI Task Force to advise the Governor on AI policy. The Task Force coordinates across agencies and engages private-sector and academic stakeholders.

| EO 30 Requirement | Framework Control | NIST AI RMF | Reference |
|---|---|---|---|
| Cross-agency AI policy coordination | Operating model AI CoE design; governance workflow for cross-functional decisions | GOVERN (GV.5, GV.6) | [operating-model/ai-coe-design.md](../../operating-model/ai-coe-design.md), [governance-operations/governance-workflow.md](../../governance-operations/governance-workflow.md) |
| Stakeholder engagement on AI risk and benefit | Board reporting; escalation paths for stakeholder-facing risk communications | GOVERN (GV.6) | [operating-model/board-reporting.md](../../operating-model/board-reporting.md) |
| Regulatory change monitoring — tracking emerging AI legislation and standards | Regulatory change monitoring and horizon scanning | GOVERN (GV.1) | [compliance/regulatory-change-monitoring.md](../regulatory-change-monitoring.md) |

---

## EO 26 — Youngkin DeepSeek / PRC-Origin AI Ban (February 11, 2025)

### Background

Executive Order 26, signed February 11, 2025, prohibited the use of DeepSeek AI on all Commonwealth-managed devices, networks, and information systems. The underlying rationale — PRC-origin AI presenting data exfiltration and supply chain risk — was reinforced when Attorney General Miyares joined a 21-state coalition supporting a federal legislative ban on PRC-origin AI.

EO 26 has direct procurement implications: vendor solutions containing PRC-origin AI components create disqualification risk under COV contracts. This requirement is not limited to DeepSeek by name; it reflects a broader principle that AI components with PRC provenance are incompatible with COV systems.

### EO 26 Control Mapping

| EO 26 Requirement | Framework Control | NIST AI RMF | Reference |
|---|---|---|---|
| Prohibition on PRC-origin AI on COV devices and networks | Supply chain security — origin and provenance verification for all AI components; third-party model provenance screening | MAP (MP.4); MANAGE (MG.2) | [ai-security/supply-chain-security.md](../../ai-security/supply-chain-security.md), [compliance/third-party-model-risk.md](../third-party-model-risk.md) |
| Vendor solutions must not incorporate PRC-origin AI components | Model selection criteria include provenance check; foreign AI component identification in procurement intake | MAP (MP.4) | [llm-lifecycle/model-selection.md](../../llm-lifecycle/model-selection.md) |
| Data exfiltration risk from PRC-origin AI — protect COV data | Data residency and LLM deployment data controls; adversarial robustness testing | MEASURE (MS.1, MS.3) | [compliance/data-residency-llm.md](../data-residency-llm.md), [ai-security/adversarial-robustness.md](../../ai-security/adversarial-robustness.md) |
| Agency IT security to audit for unauthorized PRC-origin AI installations | Continuous monitoring; supply chain security audit procedures | MEASURE (MS.3); MANAGE (MG.3) | [ai-security/supply-chain-security.md](../../ai-security/supply-chain-security.md), [model-lifecycle/monitoring.md](../../model-lifecycle/monitoring.md) |

### Foreign AI Provenance Checklist for Virginia Engagements

Vendors submitting AI-enabled solutions under COV contracts (eVA, cooperative agreements, direct buys) should document the following before submission:

- Identify the country of origin for each foundation model or AI component in the solution
- Confirm no training data, model weights, or inference infrastructure is controlled by entities headquartered or operationally based in the PRC, including Hong Kong and Macao
- Document model provenance in the third-party model risk register
- Include provenance attestation language in vendor representations and certifications
- Apply framework supply chain security controls at intake for any new AI component added post-award

---

## Spanberger Administration EO and Directive (February 4, 2026)

### Background

Governor Spanberger took office in January 2026. On February 4, 2026, the new administration signed an Executive Order and an accompanying Directive addressing AI governance. The key operative effect of this action was advancing EO 30's Directive 4 (law enforcement AI standards) that the Youngkin administration did not fulfill by the October 2024 deadline.

The VITA Policy Standard and EA-225 remain operative under the Spanberger administration. Successor or revised VITA standards are expected as the new administration develops its technology policy posture. Practitioners should monitor VITA's published standards page and the Commonwealth's regulatory calendar for updates.

### Spanberger EO/Directive — Control Mapping

| Requirement | Framework Control | NIST AI RMF | Reference |
|---|---|---|---|
| Law enforcement AI standards (EO 30 Directive 4 obligation fulfilled) — risk-based approach to facial recognition, predictive analytics, and automated decision tools | Agentic AI risk matrix for consequential decisions; T1 classification triggers; human oversight requirements | MAP (MP.2, MP.4, MP.5); MANAGE (MG.2) | [risk-classification/agentic-ai-risk.md](../../risk-classification/agentic-ai-risk.md), [responsible-ai/human-in-loop-patterns.md](../../responsible-ai/human-in-loop-patterns.md) |
| Transparency to the public about law enforcement AI use | Transparency standards for AI outputs; public disclosure obligations | GOVERN (GV.1, GV.6) | [responsible-ai/transparency-standards.md](../../responsible-ai/transparency-standards.md) |
| Bias auditing requirements for law enforcement AI | Bias detection and fairness testing protocols | MEASURE (MS.1, MS.2) | [responsible-ai/bias-detection-llm.md](../../responsible-ai/bias-detection-llm.md) |
| VITA EA-225 and Policy Standard remain in effect — vendors must continue compliance | All EO 30 Directive 1 and 2 controls remain applicable | GOVERN (GV.1, GV.5) | See EO 30 sections above |
| Expected successor VITA standards — practitioners should monitor for updates | Regulatory change monitoring process | GOVERN (GV.1) | [compliance/regulatory-change-monitoring.md](../regulatory-change-monitoring.md) |

---

## HB 2094 (2025 Session) — Vetoed March 24, 2025

### Background

HB 2094 was introduced during the 2025 General Assembly session. It would have imposed impact-assessment requirements and anti-discrimination duties on entities deploying "high-risk AI" systems in Virginia, covering employment, housing, credit, and public services contexts.

Governor Youngkin vetoed the bill on March 24, 2025. HB 2094 is **not in force** and creates no current legal obligation.

### Significance for Practitioners

HB 2094 is documented here because:

1. The Virginia General Assembly has signaled intent to legislate on high-risk AI, and successor legislation under the Spanberger administration is plausible.
2. The bill's definitions of "high-risk AI" and required impact assessment content align closely with the EU AI Act's approach and with NIST AI RMF MAP function expectations.
3. Vendors building compliance postures for Virginia today who implement the controls below will be well-positioned if successor legislation passes.

### HB 2094 Prospective Control Mapping

| HB 2094 Provision (Vetoed — Not in Force) | Framework Control | NIST AI RMF | Reference |
|---|---|---|---|
| Impact assessment required before deploying "high-risk AI" in consequential decisions | Risk classification with impact scoring; T1/T2 deployment gates requiring documented assessment | MAP (MP.5); GOVERN (GV.5) | [risk-classification/risk-matrix.md](../../risk-classification/risk-matrix.md), [llm-lifecycle/deployment-gates.md](../../llm-lifecycle/deployment-gates.md) |
| Anti-discrimination testing — AI must not produce discriminatory outcomes on protected characteristics | Bias detection LLM protocols; red-teaming for protected class bias | MEASURE (MS.1); MAP (MP.5) | [responsible-ai/bias-detection-llm.md](../../responsible-ai/bias-detection-llm.md), [ai-security/red-teaming-protocol.md](../../ai-security/red-teaming-protocol.md) |
| Consumer notice when AI is used in consequential decisions affecting them | Transparency standards; public-facing AI disclosure requirements | GOVERN (GV.1) | [responsible-ai/transparency-standards.md](../../responsible-ai/transparency-standards.md) |
| Right to explanation for adverse AI-driven decisions | Explainability requirements in validation; human-in-the-loop for T1 systems | MANAGE (MG.2) | [responsible-ai/human-in-loop-patterns.md](../../responsible-ai/human-in-loop-patterns.md) |
| Record retention for impact assessments | Audit trail and documentation retention requirements | MANAGE (MG.4) | [compliance/audit-trail-requirements.md](../audit-trail-requirements.md) |

---

## Procurement Implications for Virginia Engagements

### Applicable Procurement Vehicles

| Vehicle | Type | Relevance |
|---|---|---|
| eVA (Virginia's eProcurement system) | State procurement portal for goods and services | Primary vehicle for direct agency AI services contracts; all COV agencies use eVA for competitive procurements |
| Cooperative Master Agreements (CMA) | Pre-competed agreements available to state and local government | AI tool and SaaS subscriptions often procured through CMAs; EO 30 and EA-225 obligations flow through to CMA-purchased solutions |
| IT Direct Buy (under VITA thresholds) | Small-dollar IT purchases below competitive threshold | Subject to COV IT standards including EA-225 even at small dollar values |
| VITA Master Solution Provider Contract | VITA-managed contract for technology services | Highest scrutiny; full EA-225 compliance expected at proposal stage |

### Vendor Compliance Obligations in COV Procurement

The following obligations flow from EO 30, EO 26, and EA-225 to vendors providing AI-enabled solutions under COV contracts:

1. **Pre-award disclosure**: Identify all AI components in the proposed solution, including foundation models, inference APIs, and AI-enabled subcomponents.
2. **Provenance attestation**: Certify that no AI components originate from PRC-controlled entities (EO 26).
3. **Risk classification support**: Provide documentation supporting the agency's EA-225 risk assessment, including system purpose, data inputs, output types, and human oversight design.
4. **VITA Archer/Planview registration support**: Provide technical documentation in formats compatible with agency registration requirements.
5. **Ongoing monitoring reporting**: Define SLAs for anomaly and incident reporting to agency IT security teams.
6. **Third-party AI governance attestation**: Document AI vendor governance controls, including model provenance, data handling, and incident response.

---

## Implementation Checklist for Virginia Engagements

Use this checklist for AI system deployments touching COV agencies or COV-funded programs.

### Pre-Deployment

- [ ] Complete risk classification assessment (T1–T4) using framework risk matrix
- [ ] Verify all AI components for PRC provenance — document findings (EO 26)
- [ ] Obtain agency-head or designee approval in writing before go-live (EO 30, Directive 1)
- [ ] Register system in agency Archer GRC instance and CTP/Planview (EA-225)
- [ ] Document system purpose, data inputs, outputs, and human oversight level
- [ ] Conduct bias and fairness evaluation for any system touching consequential decisions
- [ ] Confirm public disclaimer design for AI-generated outputs delivered to citizens
- [ ] Complete human-in-the-loop design review — T1 systems require human override capability
- [ ] Deliver AI literacy orientation to agency staff who will interact with the system

### Post-Deployment

- [ ] Activate production monitoring — configure drift detection and alerting thresholds
- [ ] Establish incident escalation path to VITA/agency CISO per EA-225 requirements
- [ ] Schedule first governance review per operating model review cadence
- [ ] Maintain prompt and decision audit trail for all citizen-impacting outputs
- [ ] Monitor VITA published standards for successor or revised standards under Spanberger administration
- [ ] Subscribe to regulatory change monitoring for Virginia AI legislation (HB 2094 successor bills)

---

## Currency Note — Spanberger Administration (January 2026)

Governor Spanberger took office January 2026. As of the date of this document (June 2026), the following is the operative posture:

- EO 30 (Youngkin, January 2024) remains in effect. Its directives have not been rescinded.
- EO 26 (Youngkin, February 2025) remains in effect.
- VITA EA-225 and VITA AI Policy Standard remain operative; VITA has not yet published successor standards under the new administration, though revision is expected.
- The February 4, 2026 Spanberger EO and Directive addressed the unmet EO 30 Directive 4 law enforcement AI obligation and signals the new administration's intent to be more active on AI governance.
- HB 2094 successor legislation is not currently pending but should be monitored for the 2026 and 2027 General Assembly sessions.

**Practitioners should verify the current status of VITA standards directly at the VITA published standards page before finalizing compliance documentation for COV procurements.**

---

## Cross-References

| Related Document | Relevance |
|---|---|
| [compliance/nist-ai-rmf-mapping.md](../nist-ai-rmf-mapping.md) | Full NIST AI RMF function-to-control mapping; Virginia EOs use AI RMF vocabulary |
| [compliance/third-party-model-risk.md](../third-party-model-risk.md) | Third-party model risk framework; applies to EO 26 provenance screening |
| [compliance/audit-trail-requirements.md](../audit-trail-requirements.md) | Audit trail standards; required for EA-225 documentation and law enforcement AI obligations |
| [compliance/data-residency-llm.md](../data-residency-llm.md) | Data residency controls; applies to COV data handled by LLM-based systems |
| [compliance/responsible-ai-checklist.md](../responsible-ai-checklist.md) | Responsible AI checklist; maps to EO 30 ethical use principles |
| [ai-security/supply-chain-security.md](../../ai-security/supply-chain-security.md) | Supply chain security; primary control for EO 26 PRC-origin AI prohibition |
| [responsible-ai/human-in-loop-patterns.md](../../responsible-ai/human-in-loop-patterns.md) | Human oversight patterns; required for T1 law enforcement and consequential decision systems |
| [risk-classification/agentic-ai-risk.md](../../risk-classification/agentic-ai-risk.md) | Agentic AI risk taxonomy; applies to autonomous decision support in COV contexts |

---

*Maintained as part of the 12th House AI extension of this framework. Virginia EO citations are based on publicly available text. Practitioners should verify current VITA standards and EO status directly with source documents before relying on this mapping for contract compliance representations.*
