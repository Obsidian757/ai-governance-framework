# VITA EA-225 Enterprise Solutions Architecture for Artificial Intelligence — Mapping

## Overview

VITA Enterprise Architecture Standard EA-225, "Enterprise Solutions Architecture for Artificial Intelligence," version 1.2 (November 16, 2023) defines the technical architecture requirements for all Commonwealth of Virginia (COV) AI systems and the vendors and contractors that supply them.

EA-225 is a technical standard, not a governance policy. It specifies how AI systems shall be built, monitored, registered, and integrated into COV enterprise architecture — regardless of who built them. The companion governance policy is documented separately: see [vita-policy-standard-mapping.md](vita-policy-standard-mapping.md).

Vendors and contractors providing AI systems or AI components to COV agencies are subject to EA-225 requirements as a condition of procurement. Systems that do not conform cannot be approved for COV deployment under the VITA Procurement Review process.

---

## Scope

### What EA-225 Covers

| Scope Category | Description |
|----------------|-------------|
| Stand-alone AI systems | AI applications deployed as independent systems (dedicated AI tools, decision-support platforms) |
| Embedded AI systems | AI components integrated into larger systems (AI features within an ERP, CRM, or case management platform) |
| Generative AI systems | Large language models, text-to-image generators, code generation tools, and similar GenAI deployed in COV contexts |
| Internally developed AI | AI systems developed by or for a COV agency using in-house teams or contracted developers |
| Third-party AI | Commercially procured AI applications, SaaS AI platforms, and vendor-supplied AI components |
| Training data inputs | Data used to train or fine-tune AI models that will serve COV use cases |
| Decision-support outputs | AI outputs used to inform, recommend, or support human decisions by COV personnel |
| AI procurement | Evaluation and acquisition of AI applications through VITA-managed procurement channels |

### What EA-225 Does Not Directly Cover

- AI used exclusively in personal productivity tools without COV data ingestion
- Research or proof-of-concept systems that produce no outputs used in operations
- Algorithms that do not meet the threshold of "AI" under COV definitions (e.g., deterministic rule engines)

Note: Even where a specific tool falls outside EA-225's scope, the Commonwealth AI Policy Standard (see [vita-policy-standard-mapping.md](vita-policy-standard-mapping.md)) may still apply.

---

## AI Type Classification Under EA-225

EA-225 recognizes three AI deployment types. A single system may span multiple types.

| Type | Definition | Examples |
|------|------------|---------|
| Stand-Alone AI | An AI application that operates as an independent system with its own interface, data pipeline, and decision output | Document classification tools, standalone risk-scoring platforms, workforce analytics applications |
| Embedded AI | AI capability integrated into a broader host application; the AI is a component, not the full system | AI-assisted case routing within a case management system; fraud flagging within a payments platform; content moderation within a constituent portal |
| Generative AI | AI systems that produce novel text, code, images, audio, or other content in response to prompts | Large language models used for summarization, drafting, or Q&A; code generation assistants; AI-generated reports or correspondence |

Practical implication for vendors: if a proposed solution embeds GenAI within a larger application (e.g., an AI chatbot within a citizen services portal), it is classified as both Embedded and Generative, and requirements from both categories apply. This is a common scenario for AI readiness assessment tools that include a GenAI-powered analysis engine.

---

## Requirements Mapping Table

Each row below maps a specific EA-225 requirement to the corresponding control in this governance framework, the framework file that contains the control detail, and the form of implementation evidence a vendor should maintain.

| EA-225 Requirement | Framework Control | Framework Reference | Implementation Evidence |
|-------------------|-------------------|--------------------|-----------------------|
| COV AI systems shall conform to Commonwealth information security standards | Security review gate (SR-001, SR-002, SR-003); third-party security assessment for vendor-supplied AI | [ai-security/red-teaming-protocol.md](../../ai-security/red-teaming-protocol.md), [ai-security/adversarial-robustness.md](../../ai-security/adversarial-robustness.md), [ai-security/supply-chain-security.md](../../ai-security/supply-chain-security.md), [virginia/vita-ia-standards.md](vita-ia-standards.md) | Red-team report; adversarial robustness configuration document; supply chain provenance verification. For vendor systems: COV-equivalent security assessment or agency-accepted third-party audit. See vita-ia-standards.md for the specific VITA security standards to which conformance is required |
| Decision paths in COV AI systems shall be logged for traceability and replay | Audit trail logging (all tiers); prediction-level logging including input hash, output, confidence, downstream decision, and human override | [compliance/audit-trail-requirements.md](../audit-trail-requirements.md) | Append-only audit log schema documentation; sample log record demonstrating required fields; data retention schedule meeting or exceeding COV standards |
| AI monitoring shall include metrics and thresholds for model performance and accuracy | Production monitoring configured before go-live (PM-001, PM-002); drift detection; quality metric thresholds established per tier | [llm-lifecycle/monitoring.md](../../llm-lifecycle/monitoring.md), [model-lifecycle/monitoring.md](../../model-lifecycle/monitoring.md) | Monitoring configuration documentation; dashboard reference; defined alert thresholds for performance and accuracy metrics; evidence of alerting activation |
| AI systems shall be registered in CTP/Planview as part of the Commonwealth Technology Portfolio | System inventory requirement; lifecycle events logged (model registered, deployed, retired) | [governance-operations/control-register.md](../../governance-operations/control-register.md) (Control DA-001, DA-002); [responsible-ai/transparency-standards.md](../../responsible-ai/transparency-standards.md) | Completed CTP/Planview registration record (vendor-assisted or agency-led); system inventory entry with required fields populated |
| AI systems shall have defined roles accountable for performance, security, and compliance | Roles and RACI matrix; single accountability per system | [operating-model/roles-responsibilities.md](../../operating-model/roles-responsibilities.md), [operating-model/roles-genai.md](../../operating-model/roles-genai.md) | Named roles documented in system model card; agency Program Owner and AITR identified and acknowledged in deployment approval |
| AI systems shall document training data provenance and quality | Data governance checklist for training and fine-tuning data (DE-005); data lineage records (T1/T2) | [compliance/audit-trail-requirements.md](../audit-trail-requirements.md) | Training dataset identifier and version; data source documentation; transformation pipeline version; data quality assessment results; exclusion justifications |
| AI systems that produce outputs used in decisions shall include human oversight provisions | Human-in-the-loop controls proportional to risk tier; human oversight operational before go-live (PM-003) | [responsible-ai/human-in-loop-patterns.md](../../responsible-ai/human-in-loop-patterns.md) | Human oversight process document; staffing confirmation; override-rate monitoring in place; escalation path defined |
| AI systems shall be evaluated for bias and fairness before deployment | Bias evaluation completed pre-deployment (EV-005); fairness monitoring in production for T1/T2 | [responsible-ai/bias-detection-llm.md](../../responsible-ai/bias-detection-llm.md) | Bias evaluation report with counterfactual test results; demographic parity metrics; fairness monitoring schedule |
| GenAI outputs shall be disclosed as AI-generated to end users | Public-facing AI disclosure requirement; AI-generated content metadata | [responsible-ai/transparency-standards.md](../../responsible-ai/transparency-standards.md) | Disclosure text in system interface; AI-generated content metadata schema; sample disclosure for public-facing outputs |
| Third-party AI systems shall meet the same EA-225 requirements as internally developed systems | Third-party model risk assessment (AR-005); vendor assessment depth by tier | [compliance/third-party-model-risk.md](../third-party-model-risk.md) | Completed vendor risk assessment; DPA; security certification verification; contractual EA-225 compliance attestation |
| AI systems shall have documented rollback and incident response procedures | Rollback plan documented and tested (DA-004); incident response playbook (IR-001) | [governance-operations/governance-workflow.md](../../governance-operations/governance-workflow.md), [operating-model/incident-forensics.md](../../operating-model/incident-forensics.md) | Tested rollback procedure; GenAI incident playbook; on-call rotation record |

---

## Decision-Path Logging Requirements

The EA-225 requirement that decision paths shall be logged for traceability and replay is the most technically specific requirement in the standard. It requires more than operational logging — it requires reconstruction capability.

### What "Traceability and Replay" Means

A COV agency (or auditor) must be able to answer, for any AI-assisted decision: what input was received, which model version processed it, what output was produced, and what human action (if any) followed. This is not achievable with aggregate metrics alone.

### Minimum Log Record — EA-225 Compliance

The framework's audit trail requirements define the following minimum fields required for decision-path traceability. All fields are required for T1 and T2 systems; T3 systems require the fields marked with an asterisk.

| Field | Purpose | EA-225 Relevance |
|-------|---------|-----------------|
| `prediction_id` * | Unique identifier for each AI output event | Enables point-in-time retrieval for replay |
| `timestamp` * | UTC timestamp | Establishes the precise moment of decision |
| `model_id` * | System identifier | Identifies which AI system produced the output |
| `model_version` * | Exact version string | Required for replay — same version must produce same output |
| `input_hash` | Hash of input features | Allows input verification without storing PII in plain text |
| `input_features` | Full input (T1) | Enables full replay of the decision path |
| `output` * | AI prediction, score, or generated content | The actual decision input |
| `confidence` | Confidence score or probability | Documents the system's certainty level |
| `explanation` | Feature contributions or reasoning trace | Satisfies traceability for complex or multi-step outputs |
| `decision` | Downstream human decision taken | Documents what actually happened, not just what AI recommended |
| `human_override` | Whether a human changed the AI output | Critical for accountability chain |
| `override_reason` | Documented reason for override | Enables pattern analysis of override frequency and causes |
| `request_source` * | Which system or workflow triggered the AI | Establishes the process context |

### Log Storage Requirements for EA-225 Alignment

- Logs must be stored in append-only, tamper-evident storage
- Logs must be encrypted at rest and in transit
- Storage must remain within COV-approved data residency boundaries
- Logs must be separable from operational data to support independent audit access
- Write access restricted to the model serving infrastructure; read access extended to agency ISO, AITR, and authorized auditors
- All access to audit logs must itself be logged

### Retention

COV AI decision logs should be retained for a minimum of five years for T2 systems and seven years for T1 systems, consistent with state records management requirements and the framework's standard retention schedule.

---

## Model Performance Monitoring Requirements

EA-225 requires that AI monitoring include defined metrics and thresholds for model performance and accuracy. Monitoring must be active before a system handles live COV data or decisions.

### Performance Monitoring Implementation by AI Type

| AI Type | Key Performance Metrics | Drift Indicators | Alert Triggers |
|---------|------------------------|-----------------|----------------|
| Stand-alone AI (predictive/scoring) | Primary business metric (AUC, precision, recall); calibration; prediction score distribution | PSI on key input features; output distribution shift | Performance drop >5% relative (warning); >10% relative (critical) |
| Embedded AI | Component-level accuracy metrics; error injection rate; throughput impact on host system | Input distribution changes from host system data changes | Any component failure affecting host system SLA |
| Generative AI | Faithfulness, relevance, hallucination rate; format compliance; guardrail trigger rate | Query distribution shift; output length/sentiment drift; model provider version change | PII leakage (immediate P1); hallucination rate threshold breach; guardrail trigger rate deviation >2 standard deviations |

### Minimum Monitoring Dashboard Elements — EA-225 Compliance

Monitoring dashboards must be configured and validated before a system processes live traffic (Control PM-001). Minimum elements:

- Request volume, latency percentiles (p50, p95, p99), and error rate (real-time)
- Model performance metrics against established baseline (daily for T1, weekly for T2)
- Guardrail trigger rates and safety metric trends (GenAI systems)
- Cost accumulation against approved budget (daily)
- Drift indicators with defined alert thresholds

---

## CTP/Planview Registration

All COV AI systems must be registered in the Commonwealth Technology Portfolio (CTP), managed through Planview, before deployment. This is an EA-225 procurement and architecture governance requirement.

### Registration Information Required

The framework's system inventory fields in [responsible-ai/transparency-standards.md](../../responsible-ai/transparency-standards.md) map directly to CTP registration fields:

| CTP/Planview Field | Framework Equivalent |
|-------------------|---------------------|
| System name | System name in model card |
| Agency sponsor | Business Owner / Program Owner |
| AI type (stand-alone / embedded / GenAI) | EA-225 AI type classification |
| Data classification | Data classification from deployment gates (Gate 1) |
| Risk tier | T1–T4 tier assignment |
| Vendor/model | Foundation model provider and version (if applicable) |
| Deployment status | Lifecycle state (development / production / deprecated) |
| Last review date | Most recent governance review date |

### Vendor Role in CTP Registration

Vendors do not directly register in CTP — that is an agency responsibility. However, vendors must provide the information the agency needs to complete registration. Specifically:

- AI type classification under EA-225
- Data classification of inputs and outputs
- Model card or technical specification with model identifier and version
- Confirmation of EA-225 compliance posture

Withholding this information delays procurement approval. Including it proactively in proposal technical volumes is a differentiating practice.

---

## Procurement Review Implications

EA-225 applies during vendor evaluation, not only after contract award. When a COV agency issues an RFP or RFI for an AI system, vendor responses will be evaluated against EA-225 alignment.

### When EA-225 Applies in the Procurement Sequence

| Procurement Stage | EA-225 Application |
|------------------|--------------------|
| RFP technical requirements | Agency may incorporate EA-225 by reference; vendor must demonstrate how proposed solution satisfies each requirement |
| Proposal evaluation | Technical evaluators assess EA-225 alignment as a scored criterion; absence of audit trail, monitoring plan, or decision-path logging capability is a deficiency |
| Oral presentations / demonstrations | Agency may require demonstration of logging, monitoring dashboard, and override capability |
| Contract negotiation | EA-225 compliance obligations incorporated into contract and SOW; flow-down to subcontractors |
| Post-award compliance | Agency AITR and ISO verify EA-225 implementation before production cutover; any gaps discovered post-award must be remediated at vendor cost |

### Demonstrating EA-225 Compliance in Proposals

Proposals addressing Virginia state and local government AI procurement should include, at minimum:

1. An explicit statement that the proposed solution conforms to VITA EA-225 v1.2
2. A table mapping the proposal's technical approach to EA-225 requirements (this document can serve as a template)
3. Description of the audit logging schema and retention capability
4. Description of the monitoring dashboard and defined performance thresholds
5. Description of the GenAI disclosure mechanism (if GenAI is included)
6. Reference to third-party security assessments or certifications that satisfy the COV security standard requirement

---

## Relationship to Other Virginia Standards

| Standard | Relationship to EA-225 |
|----------|------------------------|
| VITA AI Policy Standard (Rev 3, June 2024) | Governance and approval policy; EA-225 is the technical implementation standard. Both apply. See [vita-policy-standard-mapping.md](vita-policy-standard-mapping.md) |
| VITA Information Security Standards | EA-225 references COV security standards for the security conformance requirement; these standards define what conformance means. See [vita-ia-standards.md](vita-ia-standards.md) for the detailed standard-to-control mapping |
| NIST AI RMF | EA-225 is consistent with NIST AI RMF functions; see [../nist-ai-rmf-mapping.md](../nist-ai-rmf-mapping.md) for the full cross-reference |
| ISO 42001 | EA-225 is consistent with ISO 42001 AI management system requirements; see [../iso-42001-mapping.md](../iso-42001-mapping.md) |

---

## Gaps and Remediations

The following framework capabilities require supplemental documentation to fully satisfy EA-225 for COV engagements.

| Gap | Recommended Remediation |
|-----|------------------------|
| Framework's audit trail retention schedules reference banking regulations (SR 11-7, BCBS 239); COV has its own records management requirements | Supplement audit-trail-requirements.md with a COV-specific addendum citing the Virginia Public Records Act and agency-specific retention schedules |
| CTP/Planview registration is not a native framework workflow | Add a CTP registration checklist to the deployment gates (Gate 5) for COV-targeted engagements |
| Framework's security review references general enterprise security; COV requires alignment to VITA security standards specifically | Document explicit alignment between the framework's SR controls and VITA SEC501-09 and SEC525 in a COV security addendum |

---

*Maintained by 12th House AI. This mapping reflects VITA EA-225 v1.2 (November 16, 2023). Verify against the current standard published at vita.virginia.gov before use in procurement responses.*
