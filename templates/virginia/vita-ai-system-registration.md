# VITA AI System Registration Guide

**Applies to:** Commonwealth of Virginia executive branch agencies and procurement vendors whose AI systems are subject to EO 30, the VITA Policy Standard for Utilization of AI by COV (Rev 3, June 27 2024), and EA-225 v1.2.

**Registration systems:** Commonwealth Technology Portfolio (CTP) / Planview · Virginia Integrated Risk Management (Archer GRC)

---

## Overview

Virginia EO 30 and the VITA Policy Standard require that every AI system used by or procured for a Commonwealth executive branch agency be:

1. Registered in the **Commonwealth Technology Portfolio (CTP)** managed in Planview
2. Logged in the **Archer GRC platform** as part of the agency's IT risk inventory
3. Approved by the **Agency Head** (or delegated authority) before deployment — with approval recorded in Archer

This document guides agencies and vendors through the information required for each registration step and maps each data element to the framework controls that generate the underlying evidence.

---

## Step 1: Determine Registration Scope

| Question | If Yes | If No |
|----------|--------|-------|
| Is this AI system used by or on behalf of a COV executive branch agency? | Proceed to Step 2 | Registration not required under EO 30 (check agency-specific policies) |
| Was this AI system procured by or on behalf of a COV agency? | Proceed to Step 2 | Not in scope |
| Is this AI embedded in a third-party SaaS the agency procures? | Proceed — embedded AI is explicitly in scope under the Policy Standard | |
| Is this a generative AI feature inside a broader enterprise application? | Proceed — explicitly in scope | |

**Note:** The scope is intentionally broad. When in doubt, register. Failure to register a system that should be registered is a higher risk than registering one that did not strictly require it.

---

## Step 2: Prepare Registration Data

Gather the following before entering either system.

### 2.1 System Identification

| Data Element | Description | Framework Source |
|--------------|-------------|-----------------|
| System name | Official name of the AI system or application | AI system inventory |
| System owner | Named individual (Agency role + name) | `../../operating-model/roles-responsibilities.md` |
| Agency / business unit | Owning COV agency and sub-unit | |
| Primary use case | One-sentence plain-language description | Use case assessment |
| AI category (EA-225) | Stand-alone / Embedded / Generative | `vita-ea225-mapping.md` |
| Data classification (COV) | Sensitive / Confidential / Restricted / Public | ITRM SEC 501-09 classification |
| Go-live date (actual or planned) | Date system entered or will enter production | AI lifecycle documentation |
| System status | Planned / In development / Pilot / Production / Decommissioning | |

### 2.2 Risk and Compliance Data

| Data Element | Description | Framework Source |
|--------------|-------------|-----------------|
| Risk tier | High / Medium / Low (per VITA Policy Standard risk-based approach) | `../../risk-classification/genai-risk-matrix.md` |
| Impact assessment completed | Yes / No / Date completed | `../impact-assessment-template.md` |
| PII in training data | Yes / No — if Yes, describe categories | `vita-ia-standards.md` (GOV 519-02) |
| PII in runtime outputs | Yes / No — if Yes, describe categories | |
| Decision type | Advisory (human decides) / Automated (AI decides) / Hybrid | `../../responsible-ai/human-in-loop-patterns.md` |
| Consequential decision flag | Does AI support or automate decisions affecting individual rights, benefits, or safety? | |
| Foreign AI components | Yes / No — if Yes, identify country of origin and model | `../../ai-security/supply-chain-security.md` |
| PRC-origin AI component | Yes / No (EO 26 prohibition applies) | `eo-mapping.md` |

### 2.3 Technical Architecture Data (for Archer and EA-225)

| Data Element | Description | Framework Source |
|--------------|-------------|-----------------|
| Hosting model | SaaS / IaaS / On-premise / Hybrid | |
| Foundation model (if GenAI) | Model name, version, provider, hosting location | `../../llm-lifecycle/model-selection.md` |
| Training data sources | List of datasets, provenance, authorization status | `../../llm-lifecycle/rag-governance.md` |
| Third-party AI vendors | List all AI providers in the supply chain | `../../ai-security/supply-chain-security.md` |
| Decision-path logging | Logging mechanism and log retention period | `vita-ea225-mapping.md` |
| Performance monitoring | Metrics defined, thresholds set, alerting in place | `../../llm-lifecycle/monitoring.md` |
| Security standard conformance | Which ITRM standards applied (SEC 501-09, SEC 525-01, SEC 528-02, GOV 519-02) | `vita-ia-standards.md` |
| Integration points | What agency systems does this AI connect to? | |

---

## Step 3: CTP / Planview Registration

**What it is:** The Commonwealth Technology Portfolio is Virginia's enterprise IT asset inventory. AI systems are registered as technology assets.

**Registration process:**

1. Log in to Planview with COV credentials (AITR or designated IT coordinator)
2. Create a new **Technology Asset** record
3. Populate all fields in Section 2.1 above (Identification)
4. Attach the AI Impact Assessment as a supporting document
5. Record the **CTP Asset ID** — this is referenced in the Archer record

**Key fields unique to CTP:**
- Technology lifecycle stage
- Total cost of ownership (estimated)
- Related contracts / procurement vehicles (eVA PO number, cooperative master agreement reference)
- Planned retirement date

**Evidence artifact:** Screenshot or export of the CTP record + CTP Asset ID. File in the AI system's evidence package.

---

## Step 4: Archer GRC Registration

**What it is:** Virginia Integrated Risk Management (Archer) is the agency risk and compliance tracking system. AI systems are registered as IT assets with associated risk records.

**Registration process:**

1. Log in to Archer with COV credentials (ISO or designated risk coordinator)
2. Create or update the **IT Asset** record for the AI system
3. Link to the CTP Asset ID from Step 3
4. Create an associated **Risk Record** capturing:
   - Risk tier (from Section 2.2)
   - Key risks identified in the impact assessment
   - Planned mitigations and owners
   - Review schedule

**Agency-head approval recording:**
- Once agency-head approval is obtained (Step 5), record the approval in Archer:
  - Approval date
  - Approved-by (name and title)
  - Any conditions on the approval
  - Next review date

**Evidence artifact:** Archer record export or screenshot showing the approval record. File alongside CTP record.

---

## Step 5: Obtain and Document Agency-Head Approval

**Requirement:** VITA Policy Standard §III and EO 30 require written agency-head approval before any AI use case is deployed.

### 5.1 Approval Package Contents

| Item | Description | Template / Source |
|------|-------------|-------------------|
| AI system summary | One-page system description | From Section 2.1 |
| AI impact assessment | Risk, stakeholder, fairness, privacy analysis | `../impact-assessment-template.md` |
| Risk tier and treatment plan | How risks will be managed | `../../risk-classification/assessment-template.yaml` |
| Ethical use attestation | Affirms fairness, transparency, human oversight, harm minimization | `vita-policy-standard-mapping.md` |
| PRC-origin clearance | Attestation that no EO 26-prohibited AI components are present | `eo-mapping.md` |
| Performance monitoring plan | How the system will be monitored post-deployment | `../../llm-lifecycle/monitoring.md` |
| Disclaimer plan | How AI-generated outputs will carry required public disclosures | `vita-policy-standard-mapping.md` |

### 5.2 Approval Record

The approval package and the agency head's signed approval are retained as records per ITRM SEC 501-09 retention requirements. Record the approval in Archer (Step 4).

---

## Step 6: Post-Registration Maintenance

Registration is not a one-time event. Virginia's framework requires ongoing maintenance:

| Trigger | Required Action |
|---------|----------------|
| Material change to the AI system (new model, new data source, expanded use case) | Update CTP and Archer records; reassess whether new agency-head approval is needed |
| Annual review cycle | Confirm records are current; update risk register |
| EA-225 revision published | Review for changes that affect registered systems |
| VITA Policy Standard revision | Review for new registration or disclosure requirements |
| Incident involving the AI system | Update Archer risk record; document incident and resolution |
| System decommissioning | Update CTP lifecycle stage to "Retired"; close Archer risk record |

---

## Vendor Registration Obligations

Vendors selling AI systems to COV agencies are not typically direct users of CTP or Archer — those are agency-managed systems. However, vendors must:

1. **Provide the data elements in Section 2** as part of the procurement response or post-award onboarding
2. **Deliver a decision-path logging implementation** that satisfies EA-225 requirements (not just state that logging is supported)
3. **Provide annual attestations** confirming continued PRC-origin clearance (EO 26) and no material changes to AI components
4. **Notify the agency** of any material changes to the AI system (new foundation model, new training data, architectural changes) so the agency can update registrations and re-seek approval if needed

**Vendor evidence artifacts:**
- System security plan (SSP) or equivalent describing all data elements in Section 2
- Decision-path logging configuration documentation
- PRC-origin AI attestation (signed)
- Change notification process documentation

---

## Common Registration Gaps

| Gap | Risk | Remedy |
|-----|------|--------|
| AI embedded in SaaS not registered separately | EO 30 non-compliance; CTP/Archer record for the SaaS does not capture AI-specific risk | Register embedded AI as a sub-record or annotation on the parent SaaS record; consult AITR |
| Generative AI feature added post-registration | Registration is stale; agency-head approval may be required for the new capability | Trigger a material-change review; update records |
| PRC-origin clearance not obtained at procurement | EO 26 risk; contract may be voidable | Obtain vendor attestation retroactively; escalate to ISO if unclear |
| Decision-path logging not implemented | EA-225 non-conformance; traceability gap for audit | Engage vendor for logging configuration; document gap and remediation timeline in Archer |
| Agency-head approval documented in email only | Approval may not survive audit scrutiny | Transfer approval record to Archer; obtain signed approval memo if not already obtained |

---

*Cross-references: `eo-mapping.md` · `vita-ea225-mapping.md` · `vita-policy-standard-mapping.md` · `vita-ia-standards.md` · `../../governance-operations/control-register.md` · `../../ai-security/supply-chain-security.md`*

*Currency: Verify against current VITA publications. EA-225 v1.2 (November 2023) and VITA Policy Standard Rev 3 (June 2024) are the current operative documents as of June 2026. Spanberger administration revisions expected.*
