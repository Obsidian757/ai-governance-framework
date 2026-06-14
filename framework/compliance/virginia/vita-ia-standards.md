# VITA Information Assurance Standards — AI Systems Applicability

## Overview

The Virginia Information Technologies Agency (VITA) administers the Commonwealth's Information Technology Resource Management (ITRM) Policy and Standards series. These standards govern the security, privacy, risk management, and operational compliance of all Commonwealth of Virginia (COV) information systems — including AI systems sold to or operated on behalf of COV agencies.

Virginia Executive Order 30 (2024) and the VITA AI Policy Standard (EA-225 v1.2) direct all COV AI Systems to conform to applicable VITA ITRM standards. This document maps each relevant VITA IA standard to the controls in this framework, identifies AI-specific application requirements that the standards do not explicitly address, and provides practical implementation guidance for vendors seeking to deploy AI systems within the Commonwealth.

This document is a companion to the EA-225 compliance mapping. Where EA-225 establishes the AI-specific governance regime, the VITA IA standards establish the foundational security and risk management baseline. Both layers apply concurrently.

---

## Scope

This mapping applies to any AI system that:

- Is deployed at a COV executive branch agency, authority, or institution of higher education subject to VITA policy
- Processes Commonwealth data classified at any sensitivity level
- Is offered by a vendor under a state contract, PPEA proposal, or agency-specific procurement
- Is registered or required to be registered in the Commonwealth Technology Portfolio

Systems operated exclusively by independent authorities not subject to VITA jurisdiction (certain constitutional offices, the General Assembly, and the judiciary) should confirm their applicable standards with their own technology policy authority.

---

## Applicable VITA ITRM Standards

The following VITA ITRM standards are directly applicable to AI system deployments. Each is treated in a dedicated section below.

| Standard | Title | Primary AI Relevance |
|----------|-------|----------------------|
| SEC 501-09 | Information Security Standard | System classification, access control, audit logging, incident response |
| SEC 525-01 | Risk Management Standard | Authorization to operate, risk assessment, continuous monitoring |
| SEC 528-02 | Encryption Standard | Data at rest and in transit, FIPS 140-2 requirements for COV data |
| GOV 519-02 | Privacy Standard | PII handling, VCDPA alignment, data minimization, automated decision transparency |
| CTP / Planview | Commonwealth Technology Portfolio Registration | Operational registration requirement for all AI systems |
| Archer GRC | Agency Risk and Compliance System | Agency-head approval documentation, control evidence intake |

---

## Summary Table

| VITA IA Standard | Key AI Requirement | Framework Mapping | Evidence Artifact |
|------------------|--------------------|-------------------|-------------------|
| SEC 501-09 | Classify the AI system per FIPS 199; apply controls scaled to Low/Moderate/High impact | [Risk Classification](../../risk-classification/risk-matrix.md), [Deployment Gates](../../llm-lifecycle/deployment-gates.md) | Signed risk assessment (RA-001), system security plan |
| SEC 501-09 | Audit logging of all AI inference requests, user access, and output events | [Audit Trail Requirements](../audit-trail-requirements.md), [Prompt Audit Trail](../prompt-audit-trail.md) | Production audit logs, log retention evidence |
| SEC 501-09 | Incident response procedures covering AI-specific failure modes | [Incident Forensics](../../operating-model/incident-forensics.md), [Escalation Paths](../../operating-model/escalation-paths.md) | Incident response plan, post-incident reports |
| SEC 525-01 | AI system authorized to operate under COV RMF process (ATO analogue) | [Governance Workflow](../../governance-operations/governance-workflow.md), [Control Register](../../governance-operations/control-register.md) | ATO package: risk assessment + security plan + authorization memo |
| SEC 525-01 | Continuous monitoring plan for the AI system | [LLM Monitoring](../../llm-lifecycle/monitoring.md), [Model Lifecycle Monitoring](../../model-lifecycle/monitoring.md) | Monitoring dashboard evidence, alert configuration records |
| SEC 528-02 | FIPS 140-2 validated encryption for training data, model weights, API traffic, stored outputs | [Supply Chain Security](../../ai-security/supply-chain-security.md), [Deployment Gates](../../llm-lifecycle/deployment-gates.md) | Encryption configuration documentation, FIPS module certificates |
| GOV 519-02 | Training data PII inventory; data minimization attestation; re-identification risk assessment | [Fine-Tuning Governance](../../llm-lifecycle/fine-tuning-governance.md), [RAG Governance](../../llm-lifecycle/rag-governance.md) | Training data provenance log, DPIA (RA-005) |
| GOV 519-02 | Automated decision transparency; human review pathway documented | [Human-in-the-Loop Patterns](../../responsible-ai/human-in-loop-patterns.md), [Transparency Standards](../../responsible-ai/transparency-standards.md) | Human oversight design record, transparency disclosure implementation |
| CTP / Planview | All COV AI systems registered before deployment | [Governance Workflow](../../governance-operations/governance-workflow.md) | CTP registration record with system metadata |
| Archer GRC | Agency-head approval and control attestations entered in Archer | [Control Register](../../governance-operations/control-register.md) | Archer intake package, signed agency-head authorization memo |

---

## Standard 1: ITRM SEC 501-09 — Information Security Standard

### Standard Summary

SEC 501-09 is the master Commonwealth information security standard. It establishes baseline security requirements for all COV information systems derived from NIST SP 800-53 and organized by FIPS 199 impact level (Low, Moderate, High). All AI systems deployed at COV agencies are IT systems subject to SEC 501-09 requirements in full.

### AI-Specific Application

SEC 501-09 was written for IT systems broadly. Applying it to AI systems requires interpretation in several areas:

**System Classification (FIPS 199)**

The FIPS 199 impact level for an AI system is determined by assessing the confidentiality, integrity, and availability impacts of a security event on the system and the information it processes. For AI systems, the relevant considerations include:

- Confidentiality: What is the sensitivity of the training data? What is the sensitivity of the inference inputs and outputs? Model weights themselves may warrant protection if they encode proprietary or sensitive patterns.
- Integrity: What is the harm if the AI system produces corrupted, adversarially manipulated, or hallucinated outputs that are acted upon? For systems that influence decisions affecting benefits, services, or enforcement, integrity failures may be High impact.
- Availability: What is the operational impact if the AI system is unavailable? For systems integrated into agency workflows, availability failures may require Moderate or High classification.

Most COV AI systems operating on agency data will classify as Moderate impact at minimum. Systems processing sensitive law enforcement, health, or benefit eligibility data should be assessed for High impact classification.

**Access Control Requirements**

SEC 501-09 access control requirements apply to all AI system components:

| Component | Access Control Requirement |
|-----------|--------------------------|
| Training data repositories | Role-based access; only authorized AI development personnel; audit logged |
| Model weight storage | Controlled access; no anonymous read access; integrity-checked on load |
| Inference API endpoints | Authenticated access only; agency identity management integration required |
| Output storage | Classified per sensitivity of outputs; access restricted to authorized consumers |
| Administrative interfaces | Privileged access management; MFA required; all access logged |
| Monitoring dashboards | Read access for operations; write access for platform team only |

**Audit Logging Requirements**

SEC 501-09 requires audit records sufficient to reconstruct security-relevant events. For AI systems, this extends to:

- Every inference request: timestamp, authenticated user or service identity, input hash, model version, output hash
- All model lifecycle events: deployment, configuration changes, version updates, retirement
- All access to training data, model weights, and output stores
- All administrative actions on AI infrastructure
- Security-relevant AI events: anomalous input patterns, output policy violations, inference latency spikes that may indicate adversarial probing

The framework's audit trail and prompt audit trail controls satisfy these requirements when fully implemented. See [Audit Trail Requirements](../audit-trail-requirements.md) and [Prompt Audit Trail](../prompt-audit-trail.md) for field-level specifications.

**Incident Response**

AI systems must be included in the agency's incident response plan with AI-specific playbooks covering:

- Model output failure causing harm to a citizen or agency operation
- Adversarial input detected (prompt injection, jailbreak attempt)
- Training data breach
- Model weight exfiltration or tampering
- API endpoint compromise
- Hallucination causing a materially incorrect government action

See [Incident Forensics](../../operating-model/incident-forensics.md) and [Escalation Paths](../../operating-model/escalation-paths.md) for incident response procedures.

### Framework Mapping

| SEC 501-09 Requirement | Framework Control | Reference |
|------------------------|-------------------|-----------|
| System categorization per FIPS 199 | Risk tier determination (T1–T4); FIPS 199 impact level maps to tier | [Risk Matrix](../../risk-classification/risk-matrix.md) |
| Security controls scaled to impact level | Tiered governance controls; deployment gate checklist | [Deployment Gates](../../llm-lifecycle/deployment-gates.md) |
| Access control (AC family) | Deployment gate operational readiness; model serving infrastructure access controls | [Deployment Gates](../../llm-lifecycle/deployment-gates.md) |
| Audit and accountability (AU family) | Audit trail requirements; prompt audit trail | [Audit Trail](../audit-trail-requirements.md), [Prompt Audit Trail](../prompt-audit-trail.md) |
| Incident response (IR family) | Escalation paths; incident forensics; incident report templates | [Escalation Paths](../../operating-model/escalation-paths.md), [Incident Forensics](../../operating-model/incident-forensics.md) |
| Configuration management (CM family) | Model versioning; deployment gate requirements; lifecycle change management | [Governance Workflow](../../governance-operations/governance-workflow.md) |
| Supply chain risk management (SR family) | AI Bill of Materials; supply chain security controls | [Supply Chain Security](../../ai-security/supply-chain-security.md) |
| System and information integrity (SI family) | Adversarial robustness; red-teaming; monitoring for output integrity | [Adversarial Robustness](../../ai-security/adversarial-robustness.md), [Red-Teaming Protocol](../../ai-security/red-teaming-protocol.md) |

### Evidence Artifacts Required

- System security plan (SSP) covering the AI system and its components
- FIPS 199 system categorization worksheet
- Access control matrix for all AI system components
- Audit log configuration and sample records
- Incident response plan with AI-specific playbooks
- AI-BOM (AI Bill of Materials) per supply chain security standard

---

## Standard 2: ITRM SEC 525-01 — Risk Management Standard

### Standard Summary

SEC 525-01 aligns COV IT risk management to NIST SP 800-37 Revision 2 (Risk Management Framework). It requires that all COV information systems be subject to a structured risk management process including categorization, security control selection, implementation, assessment, system authorization, and continuous monitoring. The system authorization step — equivalent to an Authority to Operate (ATO) — requires explicit approval from a designated authorizing official before a system is placed in operation.

### AI-Specific Application

EO 30 and VITA EA-225 require that AI systems obtain agency-head approval before deployment. This requirement is functionally an ATO requirement under SEC 525-01. The agency-head authorization memo under EA-225 serves as the authorizing official's decision under the COV RMF process.

Vendors should treat the EA-225 approval workflow as the ATO process for AI systems:

1. Risk assessment and system classification (matches RMF Step 1: Categorize and Step 2: Select Controls)
2. Control implementation and documentation (matches RMF Step 3: Implement)
3. Control assessment and evidence compilation (matches RMF Step 4: Assess)
4. Authorization package submission to agency head (matches RMF Step 5: Authorize)
5. Continuous monitoring plan activation (matches RMF Step 6: Monitor)

**Continuous Monitoring**

SEC 525-01 requires an ongoing authorization posture through continuous monitoring. For AI systems, this includes:

- Model performance monitoring: drift, degradation, fairness metric changes
- Security monitoring: access anomalies, adversarial input patterns, API abuse
- Operational health monitoring: latency, error rates, availability
- Regulatory and policy monitoring: changes to VITA standards, EO 30 guidance updates, or new AI-specific requirements

The framework's monitoring standards satisfy continuous monitoring requirements when the monitoring plan is formally documented and linked to the authorization package.

**Risk Assessment Cadence**

SEC 525-01 requires periodic risk assessments. For AI systems:

- Initial risk assessment: required before first deployment (maps to ATO package)
- Annual reassessment: required for all COV information systems
- Triggered reassessment: required on significant change to the AI system (new model version, new data sources, expanded use case, new agency deployment)

The framework's review cadence and change-triggered re-tiering process satisfy these requirements. See [Review Cadence](../../operating-model/review-cadence.md).

### Framework Mapping

| SEC 525-01 Requirement | Framework Control | Reference |
|------------------------|-------------------|-----------|
| System categorization | Risk tier determination with FIPS 199 overlay | [Risk Matrix](../../risk-classification/risk-matrix.md) |
| Control selection and tailoring | Tier-appropriate controls from governance control register | [Control Register](../../governance-operations/control-register.md) |
| Control implementation documentation | Lifecycle governance workflow producing implementation evidence | [Governance Workflow](../../governance-operations/governance-workflow.md) |
| Security control assessment | Red-teaming, adversarial robustness testing, deployment gate review | [Red-Teaming Protocol](../../ai-security/red-teaming-protocol.md), [Deployment Gates](../../llm-lifecycle/deployment-gates.md) |
| System authorization (ATO) | Agency-head approval per EA-225; authorization package assembly | [Control Register](../../governance-operations/control-register.md) |
| Continuous monitoring | Production monitoring (LLM and ML); governance metrics; review cadence | [LLM Monitoring](../../llm-lifecycle/monitoring.md), [Model Lifecycle Monitoring](../../model-lifecycle/monitoring.md) |
| Plan of action and milestones (POA&M) | Open findings tracking in control register; incident follow-up tracking | [Control Register](../../governance-operations/control-register.md) |

### Evidence Artifacts Required

- Authorization package: risk assessment + security plan + control assessment results
- Agency-head authorization memo (signed, dated, specifying the AI system and use case)
- Continuous monitoring plan with metric definitions and alert thresholds
- POA&M for any open control gaps identified during assessment
- Annual reassessment schedule and completed reassessment reports

---

## Standard 3: ITRM SEC 528-02 — Encryption Standard

### Standard Summary

SEC 528-02 establishes Commonwealth encryption requirements for data at rest and in transit. It requires FIPS 140-2 validated cryptographic modules for protecting sensitive COV data. The standard applies to all systems that store, process, or transmit Commonwealth information at Moderate or High sensitivity.

### AI-Specific Application

AI systems present encryption requirements across multiple components that may not be addressed in traditional IT encryption coverage:

**Training Data**

Training datasets used to fine-tune or adapt models for COV use cases may contain sensitive COV data. These datasets must be encrypted at rest using FIPS 140-2 validated encryption at all storage layers:

- Local training data stores on development infrastructure
- Cloud storage buckets or object stores used in the training pipeline
- Intermediate checkpoints and cached datasets
- Archived training datasets retained for audit purposes

Training data encryption must be in place before any COV-sensitive data is incorporated into a training pipeline, not retroactively applied after the fact.

**Model Weights**

If the AI system includes fine-tuned or agency-specific model weights (rather than relying exclusively on a commercial API), those weights must be treated as sensitive artifacts:

- Encrypted at rest in model registries and artifact stores
- Encrypted in transit during deployment (model weight transfer from registry to inference infrastructure)
- Access-controlled with encryption key management separate from the model storage system

**API Traffic for Inference**

All inference traffic between:
- Agency systems and inference endpoints
- Inference endpoints and any external API providers
- Internal microservices within the AI system architecture

must be encrypted in transit using TLS 1.2 at minimum. TLS 1.3 is preferred. Certificate management must follow COV PKI standards or an approved equivalent.

**Stored Outputs**

AI system outputs that contain or may reveal COV data must be encrypted at rest. This includes:

- Logged inference responses retained for audit purposes
- Intermediate outputs stored in retrieval-augmented generation (RAG) pipelines
- AI-generated documents or reports stored in agency systems
- Model evaluation results that contain or reference COV data

**Key Management**

Key management for encryption covering COV AI systems must use hardware security modules (HSMs) or FIPS 140-2 validated software key management where HSMs are not operationally feasible. Key rotation schedules must be documented.

### Framework Mapping

| SEC 528-02 Requirement | Framework Control | Reference |
|------------------------|-------------------|-----------|
| Data at rest encryption (training data) | Fine-tuning governance data security requirements | [Fine-Tuning Governance](../../llm-lifecycle/fine-tuning-governance.md) |
| Data at rest encryption (model weights) | Supply chain security; model artifact management | [Supply Chain Security](../../ai-security/supply-chain-security.md) |
| Data in transit encryption (inference API) | Deployment gate operational readiness: API security review | [Deployment Gates](../../llm-lifecycle/deployment-gates.md) |
| Data at rest encryption (stored outputs) | Audit trail storage requirements: encrypted storage | [Audit Trail](../audit-trail-requirements.md) |
| FIPS 140-2 validated cryptography | Supply chain security: infrastructure component validation | [Supply Chain Security](../../ai-security/supply-chain-security.md) |
| Key management | Deployment gate: security review checkpoint | [Deployment Gates](../../llm-lifecycle/deployment-gates.md) |

### Evidence Artifacts Required

- Encryption configuration documentation for each AI system component (training, weights, API, outputs)
- FIPS 140-2 module certificates for all cryptographic implementations
- TLS configuration records for inference API endpoints
- Key management policy and key rotation schedule
- For cloud-hosted components: vendor encryption attestation (SOC 2 Type II, FedRAMP authorization) confirming FIPS 140-2 compliance

---

## Standard 4: ITRM GOV 519-02 — Privacy Standard

### Standard Summary

GOV 519-02 establishes Commonwealth privacy requirements for the collection, use, storage, disclosure, and disposal of information relating to individuals. It aligns to the Virginia Consumer Data Protection Act (VCDPA, Va. Code § 59.1-571 et seq.) and Commonwealth privacy policies. The standard requires data minimization, purpose limitation, individual rights support, and privacy risk assessment for systems processing personally identifiable information.

### AI-Specific Application

AI systems create privacy risks that traditional IT systems do not, and GOV 519-02 must be applied with AI-specific interpretations in several areas:

**Training Data Provenance and PII Inventory**

Any training, fine-tuning, or evaluation dataset that includes COV data must undergo a PII inventory before use. The inventory must identify:

- Categories of personal information present
- Sensitivity level of each category
- Source system and legal basis for collection
- Whether individuals whose data is included would expect this use
- Whether data minimization or de-identification is feasible without degrading model utility

The framework's fine-tuning governance and RAG governance controls require training data provenance documentation. This documentation satisfies the GOV 519-02 PII inventory requirement when it includes the above elements.

**Data Minimization**

GOV 519-02 requires that only data necessary for the stated purpose be collected and retained. For AI systems:

- Training datasets should be scoped to the minimum information necessary to achieve the system's stated purpose
- RAG retrieval systems should be configured to retrieve the minimum context necessary to answer a query — not broad data dumps
- Inference logs should capture the minimum fields necessary for audit purposes; full prompts containing citizen PII should not be retained longer than operationally necessary
- Output retention should be limited to what is required for audit, legal hold, or operational purposes

**Re-Identification Risk**

AI models trained on COV data can re-identify individuals even from nominally de-identified inputs, particularly in low-population or niche-context queries. The privacy standard requires assessment of disclosure risk. For AI systems, this means:

- Formal re-identification risk assessment for any model trained on de-identified COV data
- Output monitoring for inadvertent disclosure of individual information
- Differential privacy or other technical mitigations for high-risk use cases
- Prohibition on prompting an AI system with de-identified data in contexts where re-identification is plausible and harmful

**Automated Decision Transparency**

The VCDPA grants individuals the right to opt out of automated profiling producing legal or similarly significant effects. EO 30 requires human oversight of consequential AI decisions. GOV 519-02's transparency requirements compound these obligations:

- Any AI-assisted decision affecting a citizen's access to government services, benefits, or regulatory enforcement must be disclosed as AI-assisted
- Citizens must have access to a human review pathway for AI-assisted decisions
- The basis for an AI-assisted decision must be documentable and explainable in terms a non-technical recipient can understand

The framework's human-in-the-loop patterns and transparency standards satisfy these requirements. See [Human-in-the-Loop Patterns](../../responsible-ai/human-in-loop-patterns.md) and [Transparency Standards](../../responsible-ai/transparency-standards.md).

**VCDPA Alignment**

Vendors operating AI systems that process Virginia consumer data (which includes COV citizen data when agencies are acting in a commercial or service capacity) must ensure:

- Data processing agreements (DPAs) with the agency address AI-specific processing
- Consent or legal basis documented for each data category used in AI training or inference
- Individual rights (access, correction, deletion, opt-out) implementable for AI-processed data
- Data protection assessments (DPAs) completed for high-risk AI processing activities

### Framework Mapping

| GOV 519-02 Requirement | Framework Control | Reference |
|------------------------|-------------------|-----------|
| PII inventory for training data | Fine-tuning governance: training data documentation | [Fine-Tuning Governance](../../llm-lifecycle/fine-tuning-governance.md) |
| Data minimization | RAG governance: retrieval scoping; audit trail: minimum logging fields | [RAG Governance](../../llm-lifecycle/rag-governance.md), [Audit Trail](../audit-trail-requirements.md) |
| Re-identification risk assessment | Risk assessment template: data sensitivity dimension; impact assessment | [Assessment Template](../../risk-classification/assessment-template.yaml), [GenAI Risk Matrix](../../risk-classification/genai-risk-matrix.md) |
| Automated decision transparency | Human-in-the-loop patterns; transparency standards; bias detection | [Human-in-the-Loop Patterns](../../responsible-ai/human-in-loop-patterns.md), [Transparency Standards](../../responsible-ai/transparency-standards.md) |
| Privacy risk assessment (DPIA) | Risk assessment workflow produces DPIA as control RA-005 | [Governance Workflow](../../governance-operations/governance-workflow.md) |
| Data subject rights support | Deployment gate: compliance review includes rights-support verification | [Deployment Gates](../../llm-lifecycle/deployment-gates.md) |

### Evidence Artifacts Required

- Training data PII inventory (one per training dataset)
- Data minimization attestation for training and inference pipelines
- Re-identification risk assessment for models trained on de-identified data
- Data Protection Impact Assessment (DPIA, control RA-005) for any high-risk AI processing
- Human oversight design record showing the review pathway for AI-assisted citizen decisions
- Transparency disclosure implementation evidence (screenshots, technical specification, or design record)
- Data processing agreement with the agency addressing AI-specific data uses

---

## Standard 5: Commonwealth Technology Portfolio (CTP) / Planview Registration

### Standard Summary

The Commonwealth Technology Portfolio (CTP), managed through Planview, is the official registry of technology systems operated by or on behalf of COV agencies. VITA requires that all significant IT investments, including AI systems, be registered in CTP before deployment. Registration provides VITA and agencies with portfolio visibility, enables oversight, and is a prerequisite for procurement approvals under certain thresholds.

### Application to AI Systems

EA-225 v1.2 extends the CTP registration requirement explicitly to COV AI Systems. An AI system is not considered authorized for COV agency use until it is registered in CTP and the registration has been reviewed by the agency technology leader (typically the agency CIO or designee).

**What Constitutes a Registerable AI System**

For CTP purposes, a registerable AI system is any system that:

- Uses machine learning, large language models, or other AI techniques to process COV data or inform COV agency decisions
- Is operated by or on behalf of a COV agency
- Represents a distinct technology investment, whether developed internally, procured as a SaaS product, or delivered by a vendor under a professional services contract

A single AI platform serving multiple agency use cases may be registered as one system with multiple use case entries, or as separate systems per use case — the agency CIO determines the appropriate registration granularity.

**Information Required for CTP Registration**

| Registration Field | Description | Source Document |
|--------------------|-------------|-----------------|
| System name | Formal name of the AI system | Vendor-provided |
| System owner | Agency business owner (not the technology team) | Agency-designated |
| Technology owner | Agency CIO or designee | Agency-designated |
| System description | Plain-language description of purpose, function, and user population | Vendor-provided |
| Data classification | FIPS 199 impact level; types of COV data processed | Risk assessment (RA-001) |
| Vendor / service provider | Organization responsible for the AI system | Vendor-provided |
| Hosting environment | On-premises, cloud (specify provider and region), hybrid | Architecture documentation |
| AI risk tier | T1–T4 per EA-225 / framework classification | Risk assessment (RA-001) |
| Authorization status | ATO status; agency-head approval date | Authorization memo |
| VITA IA standards compliance | Self-attestation of SEC 501-09, SEC 525-01, SEC 528-02, GOV 519-02 compliance | Compliance attestation |
| Planned review date | Next scheduled annual review or significant change review | Continuous monitoring plan |

**Maintenance Obligations**

CTP registration is a living record. Vendors must coordinate with the agency to update the registration when:

- The AI system undergoes a significant change (new model version, new data sources, expanded scope)
- The system's risk tier changes
- The authorization status changes (reauthorization, suspension, or decommission)
- Vendor ownership or hosting environment changes

### Framework Mapping

| CTP Requirement | Framework Control | Reference |
|-----------------|-------------------|-----------|
| System registration before deployment | Governance workflow: Stage 1 intake captures registration-ready metadata | [Governance Workflow](../../governance-operations/governance-workflow.md) |
| Risk tier documentation | Risk assessment (RA-001) provides tier and FIPS 199 classification | [Risk Matrix](../../risk-classification/risk-matrix.md) |
| Compliance attestation | Control register tracks compliance with each IA standard | [Control Register](../../governance-operations/control-register.md) |
| Registration maintenance on change | Review cadence: significant change triggers re-tiering and CTP update | [Review Cadence](../../operating-model/review-cadence.md) |

### Evidence Artifacts Required

- CTP system registration record (agency-held; vendor provides input data)
- System description document suitable for CTP entry
- Architecture documentation identifying hosting environment and data flows
- Compliance attestation letter signed by vendor's authorized representative

---

## Standard 6: Archer GRC — Risk and Compliance Registration

### Standard Summary

Archer is the Commonwealth's enterprise GRC (governance, risk, and compliance) platform used by many COV agencies to track IT system risks, control assessments, and authorization records. EO 30 and VITA EA-225 require that agency-head approval of AI systems be formally documented. For agencies using Archer, this documentation is entered as a GRC record linked to the AI system's CTP entry.

### Application to AI Systems

Archer GRC records for AI systems serve multiple compliance functions:

- Document the agency-head authorization decision and the basis for approval
- Track the AI system's control assessment results and open findings
- Record the continuous monitoring plan and status
- Provide auditable evidence that the COV RMF process was followed

**Archer Intake Package for AI Systems**

When a COV agency uses Archer, the vendor should prepare an Archer intake package that the agency's risk management staff can enter or upload. The standard intake package for an AI system includes:

| Archer Record Field | Content | Source |
|--------------------|---------|--------|
| System identifier | CTP system ID | CTP registration |
| System name and description | As registered in CTP | CTP registration |
| Risk tier | T1–T4 | Risk assessment (RA-001) |
| FIPS 199 categorization | Low / Moderate / High | Risk assessment (RA-001) |
| Authorizing official | Agency head name and title | Agency-designated |
| Authorization decision | Approved / Conditional / Denied | Agency-head authorization memo |
| Authorization date | Date of agency-head signature | Authorization memo |
| Authorization expiration | One year from authorization date (annual reauthorization cycle) | Authorization memo |
| Control assessment summary | Count of controls satisfied, conditionally satisfied, and open | Control register summary |
| Open findings (POA&M) | Description, risk level, remediation owner, target date | Control register |
| Continuous monitoring status | Active / Not yet active; last monitoring report date | Monitoring plan |
| Next review date | Annual or triggered by significant change | Continuous monitoring plan |

**How Framework Evidence Satisfies Archer Intake**

The framework's governance workflow produces evidence artifacts that map directly to Archer intake fields:

| Archer Field | Framework Evidence | Framework Reference |
|--------------|--------------------|---------------------|
| Risk tier | RA-001: signed risk assessment | [Risk Matrix](../../risk-classification/risk-matrix.md) |
| Authorization decision | Agency-head authorization memo (produced as part of Stage 5 approval) | [Governance Workflow](../../governance-operations/governance-workflow.md) |
| Control assessment summary | Control register showing control-by-control status | [Control Register](../../governance-operations/control-register.md) |
| Open findings | Control register open items | [Control Register](../../governance-operations/control-register.md) |
| Continuous monitoring status | Monitoring plan and most recent monitoring report | [LLM Monitoring](../../llm-lifecycle/monitoring.md) |

**Annual Reauthorization**

Archer records must be updated annually. For AI systems, the annual reauthorization cycle requires:

- Updated risk assessment confirming no significant changes or documenting changes and their impact
- Control assessment refresh confirming all controls remain satisfied
- Monitoring report summary covering the past year
- Agency-head signature on updated authorization memo

Significant system changes trigger an out-of-cycle reauthorization process before the change goes into production.

### Framework Mapping

| Archer Requirement | Framework Control | Reference |
|--------------------|-------------------|-----------|
| Authorization documentation | Governance workflow Stage 5: approval and authorization | [Governance Workflow](../../governance-operations/governance-workflow.md) |
| Control evidence | Control register: evidence artifacts for each control | [Control Register](../../governance-operations/control-register.md) |
| Open findings tracking | Control register: open items with owner and target date | [Control Register](../../governance-operations/control-register.md) |
| Continuous monitoring record | Monitoring standards: plan and periodic reports | [LLM Monitoring](../../llm-lifecycle/monitoring.md) |
| Annual reauthorization | Review cadence: annual review with full reauthorization package | [Review Cadence](../../operating-model/review-cadence.md) |

### Evidence Artifacts Required

- Completed Archer intake package (vendor prepares; agency enters)
- Agency-head authorization memo (signed original retained by agency; copy provided to vendor for records)
- Control register export in format suitable for Archer upload
- Annual monitoring summary report
- Significant change notification records (if applicable)

---

## Gap Analysis: Where VITA IA Standards Are Silent on AI Specifics

VITA ITRM IA standards were developed as general IT security and risk management standards. They do not yet address AI-specific risks explicitly. The following gaps exist, and EA-225 v1.2 partially fills them.

| Gap Area | IA Standard Limitation | EA-225 / Framework Fill |
|----------|------------------------|------------------------|
| Model hallucination risk | No provision in SEC 501-09 or SEC 525-01 for output reliability beyond system integrity in the traditional sense | EA-225 requires accuracy and reliability requirements; framework's hallucination policy and evaluation governance address this. See [Hallucination Policy](../../responsible-ai/hallucination-policy.md) |
| Algorithmic bias and fairness | GOV 519-02 addresses discrimination in general; no specific technical requirements for AI fairness testing | EA-225 requires bias assessment; framework's bias detection standard provides the technical approach. See [Bias Detection](../../responsible-ai/bias-detection-llm.md) |
| Foundation model supply chain | SEC 501-09 supply chain controls (SR family) were not written with AI supply chains in mind; no guidance on model provenance, training data attestation, or model card review | Framework's supply chain security standard extends SR family controls to AI-specific supply chain. See [Supply Chain Security](../../ai-security/supply-chain-security.md) |
| Adversarial AI attacks | SEC 501-09 SI family addresses malware and code integrity; no provision for prompt injection, adversarial examples, or model inversion attacks | Framework's adversarial robustness and red-teaming protocol address these attack vectors. See [Adversarial Robustness](../../ai-security/adversarial-robustness.md), [Red-Teaming Protocol](../../ai-security/red-teaming-protocol.md) |
| Agentic AI risk | No standard in the VITA ITRM series addresses AI systems that autonomously execute multi-step tasks with access to agency systems | Framework's agentic AI risk standard and multi-agent governance address this. See [Agentic AI Risk](../../risk-classification/agentic-ai-risk.md), [Multi-Agent Governance](../../llm-lifecycle/multi-agent-governance.md) |
| LLM-specific monitoring | SEC 525-01 continuous monitoring addresses traditional security metrics; no guidance on model drift, hallucination rate, or LLM-specific behavioral drift | Framework's LLM monitoring standard fills this gap. See [LLM Monitoring](../../llm-lifecycle/monitoring.md) |
| AI system retirement and data disposition | SEC 501-09 covers media sanitization; no AI-specific guidance on model weight disposal, training data disposition, or embedded-knowledge risk | Framework's model deprecation governance addresses this. See [Model Deprecation Governance](../../llm-lifecycle/model-deprecation-governance.md) |
| Re-identification from AI outputs | GOV 519-02 addresses de-identification of source data; no provision for re-identification risk created by AI model inference | Framework's GenAI risk matrix and RAG governance address output re-identification. See [GenAI Risk Matrix](../../risk-classification/genai-risk-matrix.md), [RAG Governance](../../llm-lifecycle/rag-governance.md) |

Where these gaps exist, the framework controls are the applicable requirement for COV AI system deployments. Vendors should document these controls in their authorization package as AI-specific extensions to the applicable VITA IA standards.

---

## Implementation Notes for Vendors

### Pre-Engagement Checklist

Before beginning an AI system deployment at a COV agency, confirm the following:

- [ ] Determine the applicable agency: confirm the agency is subject to VITA jurisdiction (executive branch agencies generally are; constitutional offices, General Assembly, and courts may have separate authority)
- [ ] Identify the agency CIO or technology leader who will be the registration and authorization contact
- [ ] Confirm whether the agency uses Archer GRC, an alternative GRC platform, or manual documentation for authorization records
- [ ] Confirm the agency's data classification scheme and whether COV data to be processed is Moderate or High impact
- [ ] Identify any agency-specific security standards that supplement VITA ITRM standards
- [ ] Verify whether the proposed AI system includes fine-tuning or training on COV data, which triggers additional requirements under SEC 528-02 and GOV 519-02

### Authorization Package Assembly

The authorization package for a COV AI system should be assembled as a single deliverable containing:

1. System description and architecture diagram
2. FIPS 199 system categorization worksheet
3. Risk assessment (RA-001) with tier determination and dimension scoring
4. Data Protection Impact Assessment (RA-005) if PII is processed
5. AI-BOM (AI Bill of Materials)
6. Control assessment results mapped to applicable VITA IA standards
7. Encryption configuration documentation with FIPS 140-2 module certificates
8. Incident response plan with AI-specific playbooks
9. Continuous monitoring plan with metric definitions
10. Compliance attestation letter from vendor
11. Draft CTP registration data sheet
12. Draft Archer intake package (if agency uses Archer)

Present this package to the agency CIO for review before submitting for agency-head authorization.

### Ongoing Compliance Obligations

After authorization, vendors have the following ongoing obligations:

| Obligation | Frequency | Trigger |
|-----------|-----------|---------|
| Monitoring report to agency | Monthly or as agreed | Contractual obligation |
| Significant change notification | As events occur | Model version change, scope expansion, hosting change |
| Annual reassessment | Annually | Calendar year or contract anniversary |
| Annual reauthorization package | Annually | 90 days before authorization expiration |
| CTP registration update | As events occur | Any change to registration fields |
| Incident notification to agency | Within 24 hours (security) / 72 hours (operational) | Incident detection |
| Control gap remediation reporting | As agreed in POA&M | Remediation milestone dates |

### What to Keep as Evidence

All evidence artifacts should be retained for the life of the AI system plus a minimum of three years after decommission, consistent with audit trail requirements. The following artifacts are minimum required evidence:

- All signed risk assessments and authorization memos
- Control register with point-in-time snapshots at each significant event
- All monitoring reports produced during the authorization period
- Incident reports and post-incident reviews
- Training data provenance logs and PII inventories
- Encryption configuration documentation
- AI-BOM versions corresponding to each deployed model version
- CTP registration history

Evidence should be stored in a manner that is retrievable within 48 hours to support regulatory examination or agency audit request, consistent with [Audit Trail Requirements](../audit-trail-requirements.md).

---

## Related Framework Documents

- [EA-225 Compliance Mapping](ea-225-mapping.md) — Virginia-specific AI governance requirements under EO 30 and VITA Policy Standard
- [NIST AI RMF Mapping](../nist-ai-rmf-mapping.md) — Federal AI risk management framework alignment
- [Audit Trail Requirements](../audit-trail-requirements.md) — Logging and retention requirements applicable to COV AI systems
- [Prompt Audit Trail](../prompt-audit-trail.md) — LLM-specific audit logging
- [Supply Chain Security](../../ai-security/supply-chain-security.md) — AI supply chain risk management extending SEC 501-09 SR controls
- [Adversarial Robustness](../../ai-security/adversarial-robustness.md) — AI-specific attack mitigations extending SEC 501-09 SI controls
- [Red-Teaming Protocol](../../ai-security/red-teaming-protocol.md) — Adversarial testing in support of authorization
- [Fine-Tuning Governance](../../llm-lifecycle/fine-tuning-governance.md) — Training data controls satisfying SEC 528-02 and GOV 519-02
- [RAG Governance](../../llm-lifecycle/rag-governance.md) — Retrieval pipeline controls for privacy and data minimization
- [Human-in-the-Loop Patterns](../../responsible-ai/human-in-loop-patterns.md) — Human oversight controls required by EA-225 and GOV 519-02
- [Transparency Standards](../../responsible-ai/transparency-standards.md) — Disclosure requirements for AI-assisted government decisions
- [Agentic AI Risk](../../risk-classification/agentic-ai-risk.md) — Risk classification for autonomous AI systems
- [Multi-Agent Governance](../../llm-lifecycle/multi-agent-governance.md) — Governance for multi-agent AI architectures

---

*Prepared by 12th House AI. This document reflects publicly available VITA ITRM standards and EA-225 v1.2 as of June 2026. VITA standards are subject to revision; verify current versions at vita.virginia.gov before relying on this mapping for a specific procurement or authorization package. This document does not constitute legal advice.*
