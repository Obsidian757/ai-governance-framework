# AI Governance Framework

**Practical governance patterns for AI and GenAI systems in regulated industries**

*Forked from [sunilp/ai-governance-framework](https://github.com/sunilp/ai-governance-framework) and extended with a Virginia state government compliance layer by [12th House AI](https://12thhouseai.com) — Veteran-Owned, Chesapeake, Virginia.*

---

## Philosophy

Governance is enablement, not gatekeeping. The goal is not to slow down AI adoption — it is to make AI adoption durable, defensible, and scalable across a regulated organization.

This framework provides opinionated, field-tested patterns for governing both traditional ML and GenAI/LLM systems in financial services, healthcare, state and local government, and other industries where model risk, data privacy, and regulatory compliance are non-negotiable.

The Virginia compliance module (`framework/compliance/virginia/`) extends the base framework with jurisdiction-specific controls for organizations operating under Virginia EO 30, EO 26, VITA EA-225, VITA Policy Standards, and the Spanberger administration's 2026 AI directives.

## Who This Is For

- **Chief Risk Officers** who need confidence that AI systems meet regulatory expectations
- **CTOs and Engineering VPs** who need repeatable standards for AI productionization
- **AI/ML leads** who need clear guardrails without bureaucratic overhead
- **Compliance teams** who need to map AI controls to regulatory requirements
- **CISOs** who need to assess the security surface of LLM and agentic AI systems
- **Board members** who need to understand AI risk posture without operational detail
- **Virginia state agency technology officers** subject to EO 30, VITA EA-225, and VITA Policy Standards
- **EdTech vendors** navigating Virginia's AI Education Guidelines and student data privacy requirements
- **State and local government AI leads** across the mid-Atlantic and Southeast seeking a NIST AI RMF-aligned assessment baseline

## Framework Components

### Risk Classification
Define how AI systems are tiered by risk and what governance intensity each tier requires.
- [Risk Matrix (Traditional ML)](framework/risk-classification/risk-matrix.md) — tiering criteria for classical ML models
- [GenAI Risk Matrix](framework/risk-classification/genai-risk-matrix.md) — risk dimensions specific to LLMs and generative AI
- [Agentic AI Risk](framework/risk-classification/agentic-ai-risk.md) — risk taxonomy for autonomous AI agents (single and multi-agent)
- [Multimodal AI Risk Matrix](framework/risk-classification/multimodal-risk-matrix.md) — risk dimensions for vision, audio, video, and mixed-modality systems
- [Assessment Template](framework/risk-classification/assessment-template.yaml) — structured risk assessment

### Model Lifecycle (Traditional ML)
Standards and gates across the full model lifecycle — from development through production monitoring.
- [Development Standards](framework/model-lifecycle/development.md)
- [Validation Requirements](framework/model-lifecycle/validation.md)
- [Deployment Gates](framework/model-lifecycle/deployment.md)
- [Production Monitoring](framework/model-lifecycle/monitoring.md)

### LLM Lifecycle (GenAI)
Governance standards specific to large language models and generative AI systems.
- [Foundation Model Selection](framework/llm-lifecycle/model-selection.md) — evaluation criteria for choosing LLMs
- [Prompt Engineering Standards](framework/llm-lifecycle/prompt-engineering-standards.md) — version control, review, testing
- [Fine-Tuning Governance](framework/llm-lifecycle/fine-tuning-governance.md) — when and how to fine-tune safely
- [RAG Governance](framework/llm-lifecycle/rag-governance.md) — retrieval quality, access controls, document lifecycle
- [GenAI Deployment Gates](framework/llm-lifecycle/deployment-gates.md) — what must pass before GenAI goes live
- [LLM Production Monitoring](framework/llm-lifecycle/monitoring.md) — output quality, drift, cost, safety
- [Evaluation Governance](framework/llm-lifecycle/evaluation-governance.md) — what to evaluate, thresholds by tier, release criteria, dataset governance
- [Multimodal Governance](framework/llm-lifecycle/multimodal-governance.md) — input/output governance for non-text modalities
- [Multi-Agent Governance](framework/llm-lifecycle/multi-agent-governance.md) — orchestration, coordination, and accountability for multi-agent systems
- [Open-Source Model Governance](framework/llm-lifecycle/open-source-model-governance.md) — evaluation, licensing, and maintenance for open-weight models
- [Model Deprecation Governance](framework/llm-lifecycle/model-deprecation-governance.md) — sunsetting, migration, and archival

### AI Security
Standards for securing AI systems against adversarial threats.
- [Red-Teaming Protocol](framework/ai-security/red-teaming-protocol.md) — structured adversarial testing methodology
- [Adversarial Robustness](framework/ai-security/adversarial-robustness.md) — defenses against jailbreaking, prompt injection, model extraction, data poisoning
- [Supply Chain Security](framework/ai-security/supply-chain-security.md) — model provenance, open-source risk, AI bill of materials

### Compliance Mapping
How framework controls map to specific regulatory requirements.
- [NIST AI RMF Mapping](framework/compliance/nist-ai-rmf-mapping.md) — Govern, Map, Measure, Manage function alignment
- [ISO/IEC 42001 Mapping](framework/compliance/iso-42001-mapping.md) — AI management system certification backbone
- [Regulatory Change Monitoring](framework/compliance/regulatory-change-monitoring.md) — horizon scanning and impact assessment
- [Prompt Audit Trail](framework/compliance/prompt-audit-trail.md) — logging, retention, reconstruction
- [Data Residency for LLMs](framework/compliance/data-residency-llm.md) — data flows in LLM architectures
- [Third-Party Model Risk](framework/compliance/third-party-model-risk.md) — vendor assessment and ongoing monitoring
- [Responsible AI Checklist](framework/compliance/responsible-ai-checklist.md)
- [Audit Trail Requirements](framework/compliance/audit-trail-requirements.md)

### Virginia State Government Compliance
*Added by 12th House AI — jurisdiction-specific module for Commonwealth of Virginia agencies and vendors.*

Virginia operates a layered AI governance regime: executive orders set direction, VITA standards define technical and policy controls, and IA standards govern security. This module maps all layers to framework controls.

- [Virginia Overview](framework/compliance/virginia/README.md) — instruments, procurement paths, Spanberger administration watch items
- [Executive Order Mapping](framework/compliance/virginia/eo-mapping.md) — EO 30 (2024), EO 26 (PRC-origin ban 2025), Spanberger EO/Directive (2026), HB 2094 (vetoed)
- [VITA EA-225 Mapping](framework/compliance/virginia/vita-ea225-mapping.md) — architecture standard: CTP/Planview registration, decision-path logging, performance monitoring
- [VITA Policy Standard Mapping](framework/compliance/virginia/vita-policy-standard-mapping.md) — governance policy: agency-head approval workflow, ethical-use controls, vendor obligations
- [VITA IA Standards Mapping](framework/compliance/virginia/vita-ia-standards.md) — ITRM SEC 501-09, SEC 525-01, SEC 528-02, GOV 519-02 — security and privacy controls for AI systems on COV infrastructure
- [Education Guidelines Mapping](framework/compliance/virginia/education-guidelines-mapping.md) — K-12 LEA, VCCS, SCHEV requirements; student data privacy; EdTech vendor checklist

### US State AI Policies — Mid-Atlantic and Southeast
*Added by 12th House AI.*

- [Mid-Atlantic and Southeast State Policies](framework/compliance/us-states/mid-atlantic-southeast.md) — Virginia, Maryland, North Carolina, Tennessee, West Virginia, South Carolina: binding status, procurement teeth, NIST AI RMF integration notes, cross-state compliance matrix

### Responsible AI
Standards for ethical and responsible deployment of AI systems.
- [Bias Detection for LLMs](framework/responsible-ai/bias-detection-llm.md) — counterfactual testing, metrics, monitoring
- [Hallucination Policy](framework/responsible-ai/hallucination-policy.md) — tolerance levels, measurement, mitigation
- [Transparency Standards](framework/responsible-ai/transparency-standards.md) — disclosure, labeling, explainability
- [Human-in-the-Loop Patterns](framework/responsible-ai/human-in-loop-patterns.md) — when and how humans review AI output

### Operating Model
Who does what, when, and how decisions escalate.
- [AI CoE Design & Evolution](framework/operating-model/ai-coe-design.md) — from centralized CoE to distributed operating model
- [GenAI Roles & Responsibilities](framework/operating-model/roles-genai.md) — prompt engineers, AI risk analysts, LLMOps
- [Roles & Responsibilities (RACI)](framework/operating-model/roles-responsibilities.md)
- [Review Cadence](framework/operating-model/review-cadence.md)
- [Escalation Paths](framework/operating-model/escalation-paths.md)
- [Board Reporting](framework/operating-model/board-reporting.md) — quarterly risk report structure, material incident criteria, risk appetite
- [Governance Metrics & KPIs](framework/operating-model/governance-metrics.md) — measuring governance program health
- [Cost Governance](framework/operating-model/cost-governance.md) — budgeting, attribution, optimization governance
- [GRC Integration](framework/operating-model/grc-integration.md) — COSO, ISO 31000, three lines of defense
- [Incident Forensics](framework/operating-model/incident-forensics.md) — post-incident investigation and evidence preservation

### Governance Operations
The operational backbone — controls, evidence, and the end-to-end process.
- [Control Register](framework/governance-operations/control-register.md) — master mapping of every control to its evidence, owner, and escalation
- [Governance Workflow](framework/governance-operations/governance-workflow.md) — end-to-end process from idea intake to retirement, with gates and evidence packs

## Templates
Ready-to-use templates for immediate adoption:

**Traditional ML:**
- [Model Card Template](templates/model-card-template.yaml)
- [Impact Assessment Template](templates/impact-assessment-template.md)
- [Incident Report Template](templates/incident-report-template.md)

**GenAI / LLM:**
- [LLM Model Card Template](templates/llm-model-card.yaml) — model card for LLM-based systems
- [GenAI Use Case Assessment](templates/genai-use-case-assessment.md) — risk assessment for new GenAI projects
- [Prompt Review Checklist](templates/prompt-review-checklist.md) — pre-deployment prompt review
- [GenAI Incident Report](templates/incident-report-genai.md) — GenAI-specific incident template
- [Board AI Risk Report](templates/board-ai-risk-report.md) — quarterly board reporting template
- [Red-Team Report](templates/red-team-report.md) — adversarial testing findings template

**Virginia State Government** *(added by 12th House AI):*
- [Virginia EO 30 Readiness Assessment](templates/virginia/eo30-readiness-assessment.md) — engagement deliverable template for EO 30 / VITA / EA-225 assessments; covers agencies, LEAs, IHEs, and vendors
- [VITA AI System Registration Guide](templates/virginia/vita-ai-system-registration.md) — step-by-step Archer + CTP/Planview registration with field-to-field framework mapping

## Worked Examples
See the framework applied to real-world use cases:

**Traditional ML:**
- [Credit Scoring Model](examples/credit-scoring-model/) — T1 (Critical), heavily regulated, full validation
- [Fraud Detection System](examples/fraud-detection/) — T2 (High), real-time, high-autonomy

**GenAI / LLM:**
- [Customer Service Chatbot](examples/customer-service-chatbot/) — T1 (Critical), customer-facing, RAG-based, [complete governance case file](examples/customer-service-chatbot/governance-case-file.md)
- [Document Summarization](examples/document-summarization/) — T2 (High), compliance docs, human-reviewed
- [Agentic Research Assistant](examples/agentic-research-assistant/) — T1 (Critical), agentic AI with tool access
- [Internal Knowledge Search](examples/internal-knowledge-search/) — T3 (Medium), internal RAG, lighter governance

## Adoption Approach

This framework is designed for phased rollout:

1. **Phase 1 (Week 1–2):** Adopt the risk classification matrix. Tier your existing AI and GenAI systems.
2. **Phase 2 (Month 1):** Apply lifecycle standards to one high-risk system as a pilot.
3. **Phase 3 (Month 2–3):** Roll out templates (model cards, impact assessments, prompt review checklists) org-wide.
4. **Phase 4 (Ongoing):** Establish the operating model — governance cadence, escalation paths, RACI.
5. **Phase 5 (GenAI):** Apply LLM lifecycle standards — model selection, prompt governance, RAG governance, deployment gates.
6. **Phase 6 (Security):** Establish red-teaming program, adversarial robustness standards, supply chain governance.
7. **Phase 7 (Compliance):** Extend compliance mapping to all applicable jurisdictions; implement regulatory change monitoring.

Start where the risk is highest. Expand as the organization builds muscle memory.

## Regulatory Alignment

This framework has been designed with explicit alignment to:

| Regulation | Coverage |
|---|---|
| **NIST AI RMF** | Govern, Map, Measure, Manage functions — full category-level mapping |
| **ISO/IEC 42001** | AI management system — clause-by-clause implementation mapping for certification |
| **SR 11-7 (Fed/OCC)** | Model risk management — development, validation, governance |

## Contributing

Contributions are welcome. If you work in regulated industries and have governance patterns worth sharing, open a PR. Practical experience matters more than theoretical frameworks.

## Changelog

### March 2026 — Comprehensive Update

- **AI Security:** Added red-teaming protocol, adversarial robustness standards, supply chain security
- **Regulatory breadth:** Added NIST AI RMF mapping, ISO/IEC 42001 mapping, regulatory change monitoring
- **Frontier AI coverage:** Added multimodal AI risk matrix and governance, multi-agent governance, open-source model governance, model deprecation governance
- **Enterprise operations:** Added board reporting, governance metrics/KPIs, cost governance, GRC integration, incident forensics
- **Templates:** Added board risk report and red-team report templates
- **Examples:** Added T3 internal knowledge search (lighter governance demonstration)

## License

Apache 2.0 — see [LICENSE](LICENSE).
