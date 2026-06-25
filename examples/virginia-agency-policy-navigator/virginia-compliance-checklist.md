# Virginia State Agency AI Compliance Checklist
# Benefits Policy Navigator — VDSS
# Checklist Date: June 2026

This checklist maps the Benefits Policy Navigator to all Virginia-specific AI governance requirements. It must be completed and signed off before agency-head approval or VITA registration can be obtained. For the full control mapping, see the [Virginia compliance module](../../framework/compliance/virginia/).

---

## EO 30 (2024) — Responsible and Transparent Use of Artificial Intelligence

Governor Youngkin's EO 30 requires all executive branch agencies to govern AI use responsibly, maintain human oversight, and register AI systems.

| Requirement | Status | Evidence Required | Notes |
|-------------|:------:|-------------------|-------|
| AI system inventoried and risk-assessed | **Complete** | This risk assessment | |
| Use case not in EO 30 prohibited category | **Complete** | Risk assessment Section: Virginia-Specific Risk Factors | No autonomous citizen decisions; no biometric data; no law enforcement use |
| Human oversight model documented | **Complete** | Model card — human-on-the-loop | Case workers make all eligibility determinations |
| Responsible use principles applied (fairness, transparency, accountability) | In progress | Responsible AI checklist; model card limitations section | |
| Agency annual AI compliance self-assessment completed | Not started | EO 30 annual review | Schedule for June 2027 after first year in production |
| System registered with VITA per EO 30 | Not started | VITA registration confirmation | Required before production deployment |

---

## EO 46 (2025) — Prohibition on PRC-Origin Technology

Governor Youngkin's EO 46 prohibits Virginia executive branch agencies from procuring or using technology products with ties to the People's Republic of China on COV systems.

| Component | PRC-Origin Status | Verification Method | Cleared? |
|-----------|:-----------------:|---------------------|:--------:|
| Foundation model provider | Pending | Review vendor country of incorporation, ownership, and control | No |
| Inference infrastructure (COV Azure) | Compliant | Microsoft US — verified COV procurement vehicle | Yes |
| Embedding model | Pending | Verify at procurement | No |
| Vector database | Pending | Verify vendor origin and ownership | No |
| RAG pipeline libraries / dependencies | Pending | Software Bill of Materials (SBOM) review | No |

**Action required:** Complete EO 46 verification for all pending components before production deployment. Document findings in AI-BOM. Any PRC-origin component finding must be escalated to VDSS CISO and VITA before deployment.

---

## VITA EA-225 — Artificial Intelligence Architecture Standard

VITA EA-225 governs how AI systems are registered, architected, and monitored on Commonwealth infrastructure.

### Section 4.1 — Registration

| Requirement | Status | Action |
|-------------|:------:|--------|
| System registered in VITA CTP (Commonwealth Technology Portfolio) | Not started | Submit CTP registration form; assign project manager |
| System registered in Planview (COV project management system) | Not started | Create Planview project record; link to CTP |
| EA-225 technical questionnaire submitted | Not started | Complete and submit to VITA Enterprise Architecture |
| VITA Enterprise Architect review completed | Not started | Schedule review after questionnaire submission |

### Section 4.2 — Decision-Path Logging

| Requirement | Status | Evidence |
|-------------|:------:|----------|
| All AI-assisted decisions logged with input, output, and timestamp | In design | Model card audit logging section; prompt-audit-trail framework |
| Logs retained per COV records retention schedule | In design | 7-year retention configured in logging architecture |
| Logs accessible for VITA review on request | In design | Access controls configured for VITA / VDSS CISO |
| Human override events logged | In design | Worker flag events captured in audit trail |

### Section 4.3 — Performance Monitoring

| Requirement | Status | Evidence |
|-------------|:------:|----------|
| Performance monitoring plan documented | In design | Model card monitoring section |
| Baseline performance metrics established before production | Not started | Run evaluation suite; document baseline |
| Monitoring alerts routed to responsible party | Not started | Configure alerting to VDSS OTS and policy team |
| Annual performance review conducted | Not started | Schedule for June 2027 |

---

## VITA Policy Standard — AI Governance Policy

The VITA AI Governance Policy Standard establishes agency accountability, ethical use requirements, and vendor obligations for AI systems.

### Agency-Head Accountability

| Requirement | Status | Notes |
|-------------|:------:|-------|
| Agency-head (Commissioner or designee) approval documented | Not started | Deputy Commissioner, Economic Assistance must sign |
| Approval documentation filed with VITA | Not started | Submit with CTP registration |
| Accountability ownership confirmed in writing | Not started | Include in agency AI governance record |

### Ethical Use Controls

| Requirement | Status | Evidence |
|-------------|:------:|----------|
| Prohibited use review completed | **Complete** | Risk assessment confirms no prohibited use categories apply |
| Bias and fairness assessment for affected populations | In progress | Policy corpus bias review (ensure policy documents reflect equitable coverage) |
| Transparency disclosure to users (AI-generated content labeled) | In design | System UI displays "AI-generated summary — verify with source policy" on all responses |
| User training on AI limitations and advisory-only role | Not started | Required before access provisioned |

### Vendor / Third-Party Obligations

| Requirement | Status | Notes |
|-------------|:------:|-------|
| Vendor data processing agreement (DPA) executed | In progress | Legal review in progress |
| DPA covers: no prompt retention, no training data use, breach notification | In progress | Required DPA terms under review |
| Vendor security certifications verified (FedRAMP Moderate or equivalent) | Not started | Verify at procurement selection |
| Sub-processor list reviewed and approved | Not started | Request from vendor; assess each sub-processor |
| Vendor ongoing compliance monitoring schedule established | Not started | Annual review; triggered review on material vendor change |

### AI Ethics Training

| Requirement | Status | Notes |
|-------------|:------:|-------|
| VITA-required AI ethics training identified and deployed | Not started | Source VITA training or approved equivalent |
| All user accounts blocked from access until training complete | Not started | Configure access provisioning workflow |
| Training completion rate tracked (≥ 90% required before production) | Not started | Integrate with VDSS LMS |
| Training refresh schedule for new hires and annual renewal | Not started | Add to VDSS onboarding checklist |

---

## VITA IA Standards — Information Security Controls

### ITRM SEC 501-09 — Information Security Standard

| Control | Status | Evidence |
|---------|:------:|----------|
| FIPS 199 security categorization completed (expected: Moderate) | Not started | Required for all systems on COV infrastructure |
| System Security Plan (SSP) documented | Not started | Required for Moderate-impact systems |
| Access control implemented — least privilege, role-based | In design | SSO + Active Directory role assignment |
| Multi-factor authentication enforced | In design | COV SSO enforces MFA |
| Audit logging enabled per SEC 501-09 | In design | All queries/responses logged; access logged |
| Incident response plan updated for AI-specific scenarios | Not started | Extend VDSS IR plan; cover: hallucination incident, PII detection alert, prompt injection |
| Security awareness training for system administrators | Not started | Cover AI-specific risks |

### ITRM SEC 525-01 — Data Privacy Standard

| Control | Status | Evidence |
|---------|:------:|----------|
| Privacy Impact Assessment (PIA) completed | Not started | Required — system processes employee query data |
| PII minimization documented | **Complete** | Client PII blocked from input; no client data in knowledge base |
| Data retention policy defined and implemented | In design | 7-year log retention; corpus update/deletion policy |
| Right-to-delete mechanism for employee query data | Not started | Implement query log pseudonymization to support deletion requests |
| Privacy notice to users of the system | Not started | Brief disclosure at login: what data is logged, how it is used, retention period |

### ITRM GOV 519-02 — IT Governance Standard

| Control | Status | Evidence |
|---------|:------:|----------|
| IT governance approval obtained | Not started | Route through VDSS IT governance committee |
| Change management process documented for post-deployment updates | Not started | Define: what changes require re-review (model update, corpus expansion, prompt change) |
| Disaster recovery / business continuity documented | Not started | Define: acceptable downtime, fallback procedure (return to manual policy lookup) |

---

## Pre-Production Sign-Off Summary

All items in this table must be complete and evidenced before the Benefits Policy Navigator may be deployed to production. This table serves as the formal deployment gate checklist for Virginia compliance.

| Sign-Off Item | Authority | Status |
|---------------|-----------|:------:|
| Risk assessment approved | VDSS AI Risk Analyst | **Complete** |
| Model card completed | VDSS AI Risk Analyst | **Complete** |
| EO 46 PRC-origin clearance for all components | VDSS CISO / Procurement | Not started |
| Vendor / DPA review completed | VDSS Legal | In progress |
| Domain eval suite executed; hallucination rate documented | VDSS OTS | Not started |
| PII detection end-to-end test completed | Security team | Not started |
| VITA security review (SEC 501-09) completed | VITA / VDSS CISO | Not started |
| Privacy Impact Assessment approved | VDSS Privacy Officer | Not started |
| Penetration test completed | VITA IA | Not started |
| VITA EA-225 architecture review approved | VITA Enterprise Architect | Not started |
| VITA CTP / Planview registration confirmed | VITA Project Management | Not started |
| AI ethics training deployed; ≥ 90% completion | VDSS OTS / HR | Not started |
| Agency-head (Deputy Commissioner) approval signed | Deputy Commissioner, Economic Assistance | Not started |

**Production deployment is blocked until all items above are complete.**

---

## Ongoing Virginia Compliance Obligations

After production deployment, the following obligations apply on a recurring basis.

| Obligation | Frequency | Owner |
|-----------|:---------:|-------|
| EO 30 annual compliance self-assessment | Annual (June) | VDSS AI Risk Analyst |
| VITA CTP / Planview registration review and update | Annual or on material change | VDSS OTS |
| VITA EA-225 architecture review | Annual | VDSS OTS |
| VITA IA security review | Annual | VDSS CISO |
| EO 46 supply chain re-verification (vendor changes) | On material vendor change | Procurement / CISO |
| AI ethics training refresh — new users | On-hire / on-access provisioning | VDSS HR / OTS |
| AI ethics training annual refresh — existing users | Annual | VDSS HR |
| Policy corpus update | Monthly | VDSS Policy Division |
| Hallucination audit | Quarterly | VDSS AI Risk Analyst |
| Worker feedback and flag rate review | Quarterly | VDSS OTS / Policy |
| Full framework risk assessment update | Annual (June) or on material system change | VDSS AI Risk Analyst |
