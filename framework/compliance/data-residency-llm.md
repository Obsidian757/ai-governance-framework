# Data Residency for LLM Architectures

## Overview

LLM architectures introduce data residency complexities that traditional ML deployments do not. Data flows through multiple processing stages — prompt assembly, API transmission, inference, response delivery, logging — each potentially crossing organizational or jurisdictional boundaries.

This document maps data flows in common LLM architectures and defines residency controls.

---

## Data Flow Stages in LLM Systems

### 1. Prompt Assembly

| Stage | Data Involved | Residency Consideration |
|-------|--------------|------------------------|
| User input capture | User query, session context | Processed in application layer; governed by application hosting location |
| Context retrieval (RAG) | Enterprise documents, knowledge base | Retrieved from internal stores; residency governed by existing data governance |
| Prompt construction | System prompt + user input + retrieved context | Assembled in application layer; may contain PII, confidential data, or regulated information |

### 2. Model Inference

| Architecture | Data Transit | Residency Risk |
|-------------|-------------|---------------|
| Vendor API (OpenAI, Google, etc.) | Full prompt transmitted to vendor infrastructure | Data crosses to vendor's processing region; subject to vendor's DPA |
| Self-hosted (on-premises or own cloud) | Data stays within organizational infrastructure | Full control; no cross-boundary transit |
| Virtual Private Cloud (vendor-managed) | Data processed in dedicated tenant within vendor's infrastructure | Reduced risk; verify isolation guarantees |
| Regional API endpoints | Vendor offers region-specific inference endpoints | Verify that data does not leave the specified region at any stage |

### 3. Response Processing

| Stage | Data Involved | Residency Consideration |
|-------|--------------|------------------------|
| Raw response receipt | Model output | Received from vendor infrastructure; enters application layer |
| Guardrail processing | Response filtered for safety, PII, compliance | Processed in application layer |
| Delivery to user | Final response | Delivered through application infrastructure |

### 4. Logging and Storage

| Data Type | Residency Requirement |
|-----------|----------------------|
| Audit trail (prompts + responses) | Must comply with regulatory retention and residency requirements |
| Monitoring data | May contain PII; residency-controlled |
| Evaluation data | May contain PII or sensitive data; residency-controlled |
| User feedback | Linked to user identity; PII-controlled |

---

## Residency Requirements by Data Classification

| Data Classification | Residency Requirement | Vendor API Permitted? |
|--------------------|----------------------|----------------------|
| Public data | No restrictions | Yes |
| Internal data | Organizational policy applies | Yes, with DPA |
| Confidential data | Organizational and regulatory restrictions may apply | Conditional — DPA required; regional endpoint preferred |
| PII (customer data) | Applicable data protection law applies; regional processing required | Conditional — DPA required; data processing region verified |
| MNPI (material non-public information) | Strict controls; may be prohibited from external processing | Generally no for external APIs; self-hosted or VPC required |
| Regulated data (credit, AML, sanctions) | Sectoral regulations apply | Case-by-case; legal review required |

---

## Architecture Patterns and Residency

### Pattern 1: External Vendor API

```
User → Application (your cloud) → Vendor API (vendor's region) → Application → User
```

**Residency controls:**
- Verify vendor's data processing regions
- Confirm data is not retained by vendor (or retention terms are acceptable)
- Confirm data is not used for model training
- Data Processing Agreement (DPA) in place with adequate clauses
- PII redaction before API call (where feasible)

**Suitable for:** Internal tools with non-sensitive data; public-facing applications with no PII in prompts.

### Pattern 2: Self-Hosted Model

```
User → Application (your cloud) → Model inference (your cloud) → Application → User
```

**Residency controls:**
- All data stays within organizational infrastructure
- Standard cloud security and residency controls apply
- No vendor data processing concerns

**Suitable for:** Use cases with strict data residency requirements; MNPI processing; high-sensitivity regulated data.

### Pattern 3: Vendor API with PII Redaction

```
User → Application → PII Redactor → Vendor API → PII Re-inserter → User
```

**Residency controls:**
- PII is stripped before data leaves organizational infrastructure
- Vendor processes de-identified data only
- PII redaction/re-insertion logic must be validated for completeness
- Residual re-identification risk must be assessed

**Suitable for:** Use cases where vendor API capability is needed but data contains PII.

### Pattern 4: Private Endpoint / VPC

```
User → Application (your cloud) → Vendor inference (dedicated VPC/private endpoint) → Application → User
```

**Residency controls:**
- Vendor provides dedicated compute in specified region
- Network traffic stays within private network
- Verify that data does not egress to vendor's shared infrastructure
- DPA with enhanced isolation guarantees

**Suitable for:** High-sensitivity use cases where self-hosting is not feasible but vendor capability is required.

---

## Vendor Assessment Checklist

Before using an external LLM API:

| Question | Acceptable Answer |
|----------|-------------------|
| Where is inference performed? | Named region(s) that comply with your residency requirements |
| Is data retained after inference? | No, or retention terms are acceptable and documented |
| Is data used for model training? | No, contractually excluded |
| Are there sub-processors? | Disclosed and assessed |
| Can you specify data processing region? | Yes, with contractual commitment |
| Is there a Data Processing Agreement (DPA) available? | Yes, covering applicable data protection requirements |
| What certifications does the vendor hold? | SOC 2 Type II, ISO 27001 at minimum |
| Is there a breach notification procedure? | Yes, within required notification timeframes per applicable law |
| Can data be encrypted with your keys? | Preferred; required for T1 use cases |

---

## Compliance Mapping

The applicable data residency regulations depend on the organization's sector and operating jurisdictions. Common US-applicable requirements:

| Regulation | Residency Requirement | LLM Impact |
|-----------|----------------------|------------|
| HIPAA | PHI must remain within covered entity control; BAA required with cloud vendors | Prompts containing PHI require a Business Associate Agreement with the LLM vendor |
| GLBA | Non-public personal financial information must be safeguarded | Customer financial data in prompts requires enhanced vendor controls and DPA |
| CCPA / CPRA | California consumers have rights over personal data; processing restrictions apply | California resident PII in prompts subject to CCPA data processing obligations |
| FedRAMP | Federal data must be processed on FedRAMP-authorized infrastructure | Government data requires FedRAMP-authorized LLM vendors or self-hosted deployment |
| FISMA / NIST 800-53 | Federal information systems must meet security categorization controls | AI systems processing federal data must comply with applicable NIST 800-53 controls |
| Sectoral banking regulations | Customer data may have processing restrictions per OCC / Fed / FDIC guidance | External LLM APIs processing customer banking data require legal and compliance review |

Consult legal counsel for jurisdiction-specific requirements before deploying LLM systems that process regulated data.
