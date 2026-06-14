# VITA Policy Standard for AI — Mapping

## Overview

The VITA Policy Standard for the Utilization of Artificial Intelligence by the Commonwealth of Virginia, Revision 3 (June 27, 2024), is the primary governance policy for AI use across all Commonwealth of Virginia (COV) agencies. It establishes approval requirements, ethical-use principles, data protection obligations, role accountabilities, and compliance expectations that apply before any AI system may be deployed by a COV agency.

This document maps each Policy Standard requirement to corresponding controls in this governance framework and to NIST AI RMF functions (GOVERN / MAP / MEASURE / MANAGE). A cross-reference to the complementary technical architecture standard is maintained at [vita-ea225-mapping.md](vita-ea225-mapping.md).

---

## Scope

### What the Policy Standard Covers

The Policy Standard applies to all of the following, whether owned by the agency or supplied by a contractor or vendor:

| Category | Examples |
|----------|---------|
| Existing and new AI systems | Both legacy AI already in use and newly acquired or developed AI |
| Stand-alone AI systems | Dedicated AI applications with their own interface and output |
| Embedded AI systems | AI components integrated into broader platforms |
| Generative AI inside other systems | A summarization feature inside a case management system; an AI chatbot embedded in a constituent-facing portal |
| Agency-developed AI | AI built by agency staff or contracted developers on the agency's behalf |
| Third-party AI | Commercially licensed AI applications and SaaS platforms |
| Training data | Data used to train or fine-tune AI models serving COV use cases |
| Outputs supporting decisions | Any AI output that a COV employee uses to inform, recommend, or make a decision |
| AI procurement | Evaluation and acquisition of AI applications through any procurement vehicle |

### What Is Explicitly Out of Scope

The Policy Standard does not apply to general-purpose web search tools or traditional statistical analysis tools that do not use machine learning. However, the distinction between "traditional statistics" and "AI" is narrow in practice — if a system learns from data and produces outputs that influence decisions, it likely falls within scope.

---

## Roles Defined in the Policy Standard

The Policy Standard defines four accountable roles. These roles have counterparts in the framework's operating model.

| COV Role | Policy Standard Authority | Framework Counterpart | Reference |
|----------|--------------------------|----------------------|-----------|
| Agency Head | Final approval authority; must approve every AI use case before deployment; approval is recorded in Archer and CTP/Planview | AI Risk Committee (T1) / Head of AI (T2) — highest authority in the approval chain | [operating-model/roles-responsibilities.md](../../operating-model/roles-responsibilities.md) |
| Agency Information Technology Resource (AITR) | Technical accountability for AI systems; ensures EA-225 architectural conformance; coordinates CTP/Planview registration | Data Science Lead / AI Lead; Technical Owner | [operating-model/roles-responsibilities.md](../../operating-model/roles-responsibilities.md), [operating-model/roles-genai.md](../../operating-model/roles-genai.md) |
| Information Security Officer (ISO) | Security review of AI systems before deployment; ongoing security oversight | Security / CISO role in deployment gate sign-off | [ai-security/red-teaming-protocol.md](../../ai-security/red-teaming-protocol.md) |
| Program Owner | Day-to-day ownership of the AI system; monitors performance; responsible for ensuring the system operates within approved parameters | Business Owner / Product Owner | [operating-model/roles-responsibilities.md](../../operating-model/roles-responsibilities.md) |

---

## Requirements Mapping Table

| Policy Standard Requirement | NIST AI RMF Function | Framework Control | Framework Reference | Implementation Evidence |
|----------------------------|---------------------|-------------------|--------------------|-----------------------|
| Agency Head shall approve every AI use case before deployment | GOVERN (GV.1 — Policies; GV.2 — Accountability) | Deployment approval sign-off chain (DA-002); tiered approval authority | [governance-operations/governance-workflow.md](../../governance-operations/governance-workflow.md) (Stage 7), [governance-operations/control-register.md](../../governance-operations/control-register.md) | Signed deployment approval record with Agency Head (or delegated authority) signature; Archer and CTP/Planview registration confirming approval |
| Approval shall be recorded in Archer and CTP/Planview | GOVERN (GV.5 — Processes) | System inventory and lifecycle event logging; deployment approval record | [responsible-ai/transparency-standards.md](../../responsible-ai/transparency-standards.md), [compliance/audit-trail-requirements.md](../audit-trail-requirements.md) | Archer record number and CTP/Planview entry reference included in the deployment approval package |
| AI systems shall adhere to ethical-use principles: fairness, transparency, accountability, human oversight, minimization of harm | GOVERN (GV.1, GV.4) | Responsible AI checklist; bias evaluation; transparency standards; human-in-the-loop patterns; impact assessment | [compliance/responsible-ai-checklist.md](../responsible-ai-checklist.md), [responsible-ai/bias-detection-llm.md](../../responsible-ai/bias-detection-llm.md), [responsible-ai/transparency-standards.md](../../responsible-ai/transparency-standards.md), [responsible-ai/human-in-loop-patterns.md](../../responsible-ai/human-in-loop-patterns.md) | Signed responsible AI checklist; bias evaluation report; human oversight process document; impact assessment documenting minimization of harm controls |
| Personal data shall be protected throughout the AI lifecycle | MAP (MP.4 — Risks); MANAGE (MG.4 — Documentation) | DPIA completed before development (RA-005); PII handling verified in security gate; PII redaction from monitoring logs | [governance-operations/governance-workflow.md](../../governance-operations/governance-workflow.md) (Stage 2), [llm-lifecycle/deployment-gates.md](../../llm-lifecycle/deployment-gates.md) (Gate 3) | Filed DPIA with DPO or AITR sign-off; PII handling validation evidence from security review; monitoring configuration confirming PII redaction |
| Public-facing AI outputs shall include a disclaimer indicating AI involvement | GOVERN (GV.6 — Stakeholder Engagement); MANAGE (MG.3 — Risk Communication) | User interaction disclosure; AI-generated content metadata and labeling | [responsible-ai/transparency-standards.md](../../responsible-ai/transparency-standards.md) | Disclosure text incorporated into system interface design documentation; sample output demonstrating disclaimer placement; user communication materials |
| AI systems shall comply with Commonwealth information security standards | MAP (MP.4); MEASURE (MS.1 — Test and Evaluation) | Security review gate (SR-001 through SR-004); ISO sign-off in deployment gate | [ai-security/red-teaming-protocol.md](../../ai-security/red-teaming-protocol.md), [ai-security/adversarial-robustness.md](../../ai-security/adversarial-robustness.md), [ai-security/supply-chain-security.md](../../ai-security/supply-chain-security.md), [virginia/vita-ia-standards.md](vita-ia-standards.md) | Red-team report; adversarial robustness documentation; supply chain provenance; ISO sign-off on deployment approval. See vita-ia-standards.md for the specific VITA security standards applicable to AI systems |
| AI systems shall be monitored for performance, safety, and compliance throughout operation | MEASURE (MS.3 — Monitoring; MS.4 — Feedback) | Production monitoring configured before go-live (PM-001, PM-002, PM-004); ongoing governance review cadence | [llm-lifecycle/monitoring.md](../../llm-lifecycle/monitoring.md), [model-lifecycle/monitoring.md](../../model-lifecycle/monitoring.md), [operating-model/review-cadence.md](../../operating-model/review-cadence.md) | Monitoring configuration documentation; alert configuration; production evaluation schedule; latest evaluation results |
| Third-party AI systems are subject to the same Policy Standard requirements as internally developed AI | GOVERN (GV.2); MAP (MP.4) | Third-party model risk assessment (AR-005); vendor assessment depth by tier; contractual EA-225 and Policy Standard compliance obligations | [compliance/third-party-model-risk.md](../third-party-model-risk.md) | Completed vendor risk assessment; DPA; contractual Policy Standard compliance attestation; vendor-provided model card or technical specification |
| AI systems shall be inventoried and registered in CTP/Planview | GOVERN (GV.5) | Lifecycle event logging (model registered, deployed, retired); system inventory | [governance-operations/control-register.md](../../governance-operations/control-register.md), [responsible-ai/transparency-standards.md](../../responsible-ai/transparency-standards.md) | CTP/Planview registration record; system inventory entry with all required fields |
| Agencies shall assess risks before deploying AI, including bias, inaccuracy, and unintended consequences | MAP (MP.1 — Context; MP.4 — Risks; MP.5 — Impacts); MEASURE (MS.1) | Full risk assessment and tiering (RA-001 through RA-004); impact assessment (RA-003); bias evaluation (EV-005) | [governance-operations/governance-workflow.md](../../governance-operations/governance-workflow.md) (Stages 2, 5), [risk-classification/risk-matrix.md](../../risk-classification/risk-matrix.md), [risk-classification/genai-risk-matrix.md](../../risk-classification/genai-risk-matrix.md) | Signed risk assessment with dimension scoring; completed impact assessment; bias evaluation report |

---

## Agency Head Approval Workflow

The Policy Standard's requirement that Agency Head approval be obtained before deployment, and recorded in Archer and CTP/Planview, defines a specific workflow. The following maps the framework's governance workflow to the COV approval sequence.

### Stage-by-Stage Mapping

| COV Approval Step | Framework Governance Stage | Evidence Produced |
|-------------------|---------------------------|-------------------|
| AI use case identified; preliminary review | Stage 1: Idea Intake | Intake form with business justification; initial risk screening |
| Risk assessment and classification | Stage 2: Risk Assessment and Tiering | Signed risk assessment; tier determination; impact assessment; DPIA if PII |
| Architecture and vendor review | Stage 3: Architecture and Design Review | Architecture document; vendor risk assessment; data residency confirmation |
| Development, prompt engineering, data governance | Stage 4: Development | Model card; prompt review record; data governance checklist |
| Testing and evaluation | Stage 5: Evaluation and Testing | Evaluation report; safety evaluation; bias evaluation; RAG retrieval evaluation (if applicable) |
| Security review (ISO involvement) | Stage 6: Security and Red-Teaming | Red-team report; adversarial robustness documentation; ISO sign-off |
| Evidence pack assembly; Agency Head approval | Stage 7: Deployment Approval | Complete evidence pack; signed deployment approval record from Agency Head (or delegated authority); Archer record; CTP/Planview registration |
| Production cutover and monitoring | Stage 8: Production Operations | Monitoring configuration active; alerting active; human oversight staffed |

### Evidence Required for Agency Head Approval

For a T1 (highest risk) COV AI system, the complete evidence pack submitted for Agency Head approval includes all twelve items defined in the framework's deployment gate requirements, supplemented by two COV-specific artifacts:

1. Signed risk assessment with tier determination
2. Architecture review record
3. DPIA (if PII processed)
4. Model card
5. Prompt review record (GenAI systems)
6. Evaluation report (pre-release, safety, regression, RAG, bias)
7. Red-team report
8. Security assessment with ISO sign-off
9. Monitoring configuration
10. Incident response playbook
11. Rollback plan with test evidence
12. Deployment approval record (routed for Agency Head signature)
13. **COV-specific:** Archer risk record number
14. **COV-specific:** CTP/Planview registration confirmation

For T2 systems, items 1–12 apply with team-level rather than committee-level reviews at several stages. Items 13 and 14 apply regardless of tier.

### Delegation of Approval Authority

The Policy Standard places final approval with the Agency Head. In practice, many agencies have established delegated approval frameworks where the AITR or a designated AI governance officer holds delegated authority for lower-risk systems. Vendors should not assume delegation exists — confirm the specific agency's approval delegation policy before scoping the approval timeline.

---

## Ethical-Use Principles — Detailed Mapping

The Policy Standard's five ethical-use principles each have direct framework control counterparts.

| Ethical Principle | Policy Standard Intent | Framework Implementation | Reference |
|------------------|----------------------|-------------------------|-----------|
| Fairness | AI systems shall not produce outputs that discriminate on the basis of protected characteristics; decision rates across demographic groups shall be monitored | Pre-deployment bias evaluation; fairness monitoring in production (monthly for T1, quarterly for T2); counterfactual testing on protected attributes | [responsible-ai/bias-detection-llm.md](../../responsible-ai/bias-detection-llm.md) |
| Transparency | Users and affected parties shall understand when AI is involved and how AI-generated outputs were produced | User disclosure before first AI interaction; AI-generated content metadata; explainability mechanisms proportional to risk tier; source attribution for RAG outputs | [responsible-ai/transparency-standards.md](../../responsible-ai/transparency-standards.md) |
| Accountability | Named individuals are responsible for AI system performance, compliance, and outcomes | Single accountability principle: one Business Owner, one Technical Owner per system; no shared accountability; AITR and ISO have documented roles | [operating-model/roles-responsibilities.md](../../operating-model/roles-responsibilities.md) |
| Human Oversight | Consequential AI decisions shall have human review commensurate with the stakes; AI shall not make final decisions autonomously in high-stakes contexts | Human-in-the-loop pattern selection by risk tier; human oversight operational before go-live (PM-003); override capability required; override rate monitored | [responsible-ai/human-in-loop-patterns.md](../../responsible-ai/human-in-loop-patterns.md) |
| Minimization of Harm | AI systems shall be designed and operated to minimize risk of harm to individuals, groups, and the public | Impact assessment documenting harm scenarios; agentic AI risk controls; incident response with defined severity levels and response SLAs; rollback capability tested | [risk-classification/agentic-ai-risk.md](../../risk-classification/agentic-ai-risk.md), [operating-model/incident-forensics.md](../../operating-model/incident-forensics.md) |

---

## Vendor Implications: Demonstrating Compliance When Selling to COV Agencies

The Policy Standard applies to third-party AI systems on the same terms as internally developed AI. A vendor whose product is deployed by a COV agency must ensure that their system enables the agency to satisfy the Policy Standard's requirements. A system that is technically functional but cannot support the agency's compliance obligations will not pass procurement evaluation.

### What Vendors Must Enable

| Policy Standard Obligation | What the Vendor Must Provide |
|---------------------------|------------------------------|
| Agency Head approval requires documented risk assessment | Vendor-supplied technical documentation supporting the agency's risk assessment: AI type classification, data inputs and outputs, model card or equivalent, known limitations, bias evaluation results |
| Archer and CTP/Planview registration | Technical specification fields mapped to CTP registration fields; confirmation of EA-225 type classification; willingness to participate in agency onboarding review |
| Ethical-use principles | Bias and fairness testing results from the vendor's own evaluation; disclosure mechanisms (how the system notifies users of AI involvement); explainability capability documentation |
| Personal data protection | Data processing agreement (DPA) with explicit terms on retention, training data exclusion, and breach notification; documentation of PII handling within the system |
| Commonwealth security standards | Third-party security assessment (SOC 2 Type II, FedRAMP authorization, or VITA-equivalent security questionnaire); penetration test summary; adversarial robustness documentation |
| Monitoring and performance thresholds | Monitoring dashboard with configurable performance thresholds; API or export capability for audit trail data; alert notification configuration |
| AI-generated content disclaimer | Configurable disclosure text; documentation of where disclaimers appear and how they can be customized to agency requirements |
| Incident response | Vendor SLA for security incident notification; defined escalation contacts; documented rollback or service restoration procedures |

### Flow-Down Requirements

The Policy Standard requires compliance from vendors as a condition of procurement. In practice, this means:

- The prime contractor is responsible for ensuring all subcontractors and technology providers meet Policy Standard requirements
- AI components supplied by sub-tier vendors (e.g., a foundation model API used within a larger platform) must be covered by the prime's compliance attestation or by a separate sub-tier attestation
- VITA procurement templates and SOW boilerplate for AI acquisitions typically include an explicit Policy Standard compliance clause with audit rights

Vendors should anticipate that COV agencies will require a signed compliance attestation — a document stating that the proposed system, as delivered and configured, enables the agency to satisfy VITA Policy Standard Rev 3 requirements. Producing this attestation proactively demonstrates readiness and reduces pre-award evaluation friction.

---

## Third-Party AI Governance

The Policy Standard does not distinguish between AI the agency builds and AI the agency buys. The same obligations apply. This section addresses the specific governance controls that the framework provides for vendor-supplied AI.

### Key Controls for Third-Party AI

| Control | Purpose | Policy Standard Connection | Framework Reference |
|---------|---------|---------------------------|---------------------|
| Third-party model risk assessment (AR-005) | Structured evaluation of vendor AI for behavior risk, data privacy risk, operational risk, vendor viability risk, and legal/regulatory risk | Satisfies the agency's obligation to assess risks before deploying third-party AI | [compliance/third-party-model-risk.md](../third-party-model-risk.md) |
| Vendor assessment depth by risk tier | T1 systems require CISO, CRO, and Legal sign-off on vendor; T2 requires Head of AI and Security sign-off | Ensures the approval authority is proportional to the risk the vendor's system introduces | [compliance/third-party-model-risk.md](../third-party-model-risk.md) |
| Ongoing vendor monitoring | Domain evaluation suite executed continuously; provider changelog review; SLA compliance tracking | The Policy Standard requires ongoing monitoring — vendor monitoring is part of that obligation | [compliance/third-party-model-risk.md](../third-party-model-risk.md) |
| Exit strategy documentation | Alternative providers identified; migration effort estimated; data portability confirmed | Protects the agency if a vendor cannot sustain Policy Standard compliance or is acquired | [compliance/third-party-model-risk.md](../third-party-model-risk.md) |
| Concentration risk monitoring | Track aggregate dependency on any single vendor | Prevents single-vendor lock-in that would make compliance remediation difficult | [compliance/third-party-model-risk.md](../third-party-model-risk.md) |

### How the Agency's AI Approval Workflow Applies to Vendor Systems

When a COV agency acquires a third-party AI system, the agency's governance workflow does not stop at contract award. The agency must:

1. Complete a risk assessment for the vendor's system (not the vendor's assessment — the agency's own)
2. Complete the AITR's architecture review confirming EA-225 alignment
3. Review the vendor's security documentation (ISO sign-off is still required)
4. Complete the evaluation stage using the vendor's system in the agency's environment, not only vendor-supplied benchmark data
5. Obtain Agency Head approval before going live, regardless of whether the vendor's system is already approved elsewhere

Vendor systems approved for use by other COV agencies do not automatically carry that approval forward; each agency must complete its own approval process.

---

## Relationship to Other Virginia Standards and This Framework

| Document | Relationship |
|----------|-------------|
| [vita-ea225-mapping.md](vita-ea225-mapping.md) | EA-225 is the technical implementation standard; the Policy Standard is the governance policy. Both apply to all COV AI systems and their vendors. This document and the EA-225 mapping should be read together |
| [../nist-ai-rmf-mapping.md](../nist-ai-rmf-mapping.md) | The Policy Standard's requirements are consistent with NIST AI RMF. Where both apply, the NIST mapping provides additional implementation depth |
| [../responsible-ai-checklist.md](../responsible-ai-checklist.md) | The responsible AI checklist is the point-of-departure evidence document for the Policy Standard's ethical-use principles |
| [../audit-trail-requirements.md](../audit-trail-requirements.md) | The audit trail requirements satisfy the Policy Standard's data protection and accountability obligations |
| [../third-party-model-risk.md](../third-party-model-risk.md) | The third-party model risk assessment is the primary instrument for demonstrating Policy Standard compliance for vendor-supplied AI |

---

*Maintained by 12th House AI. This mapping reflects VITA Policy Standard for the Utilization of Artificial Intelligence by the Commonwealth of Virginia, Revision 3 (June 27, 2024). Verify against the current standard published at vita.virginia.gov before use in procurement responses.*
