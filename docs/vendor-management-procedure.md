# 12th House AI - Third-Party AI Vendor Management

**Document Control**
- Version: 1.0
- Effective Date: February 1, 2026
- Owner: Brannon Solomon (Technical Lead)
- Next Review: February 1, 2027

---

## 1. Purpose

This procedure establishes requirements for selecting, managing, and monitoring third-party AI vendors to ensure compliance with ISO/IEC 42001:2023 (Clause 8.6), NIST AI RMF, and federal requirements including EO 14110 which holds contractors liable for third-party AI compliance.

---

## 2. Scope

This procedure applies to all third-party AI technologies used by 12th House AI, including:
- Large language model APIs and services
- Voice / speech / multimodal AI services
- AI models and frameworks (pre-trained models, embeddings)
- AI-enabled cloud platforms
- AI components embedded in broader SaaS solutions

---

## 3. Third-Party AI Vendor Inventory (categorized)

Specific vendor identities are recorded in the per-engagement Vendor Management record, not in this publicly published procedure. The category-level inventory below shows the *kinds* of vendors in scope and the controls that apply.

### Active vendor categories

| Vendor Category | Service | Classification | Data Allowed | Selection Rules |
|---|---|---|---|---|
| **Large language model API (enterprise tier)** | Primary LLM service | Enterprise | Internal, Confidential | For federal-facing engagements, only federally-cleared providers; for foreign-AI-excluded engagements, foreign-AI providers are excluded |
| **Voice synthesis / voice agent platforms** | Voice automation | Business | Internal, Confidential | DPA required; data residency confirmed |
| **Multi-model API gateways** | Routed access to multiple LLMs | Standard | Public, Internal only | No client confidential data unless the gateway is itself enterprise-tier and the underlying model is approved |
| **Cloud AI platforms (e.g., Microsoft Azure AI)** | Cloud AI services | Enterprise | All (commercial) | Under enterprise agreement with documented data-residency and "do not train" terms |

### Conditional/Restricted vendor categories

| Vendor Category | Status | Restriction | Action Required |
|---|---|---|---|
| **Free-tier AI services** | Prohibited for production | No client or sensitive data | Use business/enterprise tiers only |
| **Consumer-grade chat assistants** | Prohibited for client work | No work data | Do not use for client work |
| **Foreign-AI-component providers** (where prohibited by client procurement terms, e.g., Advancing American AI Act §7223 flow-downs) | Prohibited for in-scope engagements | Excluded entirely | Flag at vendor selection; document exclusion in engagement Vendor Management record |
| **Federally-blacklisted providers** for federal-facing engagements | Prohibited for federal-facing client work | No federal-facing engagement use | Flag at vendor selection; route federal-facing work to a federally-cleared provider |

---

## 4. Vendor Selection Criteria

### 4.1 Mandatory Requirements

All third-party AI vendors must meet these criteria before approval:

**Security:**
- [ ] SOC 2 Type II certification (or equivalent)
- [ ] Encryption at rest and in transit (AES-256 minimum)
- [ ] Access controls and authentication (SSO/SAML preferred)
- [ ] Incident response process documented
- [ ] Regular security testing/pen testing

**Privacy:**
- [ ] Data Processing Agreement (DPA) available
- [ ] GDPR/CCPA compliance documented
- [ ] "Do not train on customer data" policy or opt-out available
- [ ] Data residency options (U.S. required for federal work)
- [ ] Data deletion capabilities

**Transparency:**
- [ ] AI model capabilities and limitations documented
- [ ] Known biases and failure modes disclosed
- [ ] Version control and change notification
- [ ] SLA and support terms clear

**Compliance:**
- [ ] FedRAMP authorization (for federal work)
- [ ] HIPAA BAA available (for healthcare use cases)
- [ ] Terms allow use for intended purpose

### 4.2 Preferred Requirements

Nice-to-have features that increase vendor score:

- Model explainability features
- Audit logging and access to logs
- Customization/fine-tuning options
- Multi-region deployment
- 24/7 support availability
- API rate limits suitable for production
- Cost transparency and predictability

### 4.3 Vendor Scoring

Score each vendor 1-5 on these dimensions:

| Dimension | Weight | Score (1-5) | Weighted |
|-----------|--------|-------------|----------|
| Security posture | 25% | ___ | ___ |
| Privacy controls | 20% | ___ | ___ |
| Compliance coverage | 20% | ___ | ___ |
| Technical capability | 15% | ___ | ___ |
| Cost effectiveness | 10% | ___ | ___ |
| Support quality | 10% | ___ | ___ |
| **Total** | 100% | | ___ / 5.0 |

**Approval thresholds:**
- 4.0+: Approved for all use cases
- 3.0-3.9: Approved with conditions (document limitations)
- 2.0-2.9: Approved for low-risk use only
- <2.0: Not approved

---

## 5. Vendor Approval Process

### 5.1 New Vendor Request

1. **Business justification:** Why is this vendor needed? What alternatives were considered?
2. **Technical assessment:** Does vendor meet mandatory requirements?
3. **Contract review:** Are terms acceptable? DPA in place?
4. **Risk assessment:** What could go wrong? What data will be exposed?
5. **Approval decision:** Approve, approve with conditions, or reject

### 5.2 Approval Authority

| Vendor Risk Level | Approval Authority |
|-------------------|-------------------|
| Low (public data only) | Technical Lead (self-approval) |
| Medium (internal/confidential) | CEO approval required |
| High (regulated data) | CEO + legal review required |

### 5.3 Documentation

For each approved vendor, maintain:
- Vendor assessment scorecard
- Contract and DPA copies
- Approval record with date and approver
- Conditions or restrictions documented
- Annual review schedule

---

## 6. Vendor Contract Requirements

### 6.1 Minimum Contract Terms

All third-party AI vendor contracts must include:

**Data Protection:**
- Vendor will not train on customer data without explicit consent
- Data encrypted at rest and in transit
- Data deleted upon contract termination (with certification)
- Data localization (U.S. only for federal work)

**Security:**
- Security incident notification within 72 hours
- Right to audit upon request (annually minimum)
- Maintain SOC 2 or equivalent certification

**Compliance:**
- Comply with applicable laws (GDPR, CCPA, HIPAA if applicable)
- Cooperate with regulatory inquiries
- Indemnification for vendor-caused compliance failures

**Service:**
- Defined SLA (uptime, response time)
- 30-day notice for material changes
- Clear termination and exit provisions

### 6.2 HIPAA Business Associate Agreement (BAA)

For vendors processing PHI:
- Standard BAA executed before PHI processing
- Vendor listed as Business Associate in compliance documentation
- Annual confirmation of BAA status
- Incident response aligned with HIPAA timelines

**Current BAA Status:**

| Vendor Category | BAA Available? | BAA Executed? | Notes |
|---|---|---|---|
| Voice synthesis (enterprise tier) | Yes (Enterprise) | Pending | Required before healthcare deployments |
| Voice agent platform | Per-vendor evaluation | No | Evaluate before healthcare use |
| Cloud AI platform (Microsoft Azure AI) | Yes | Yes | Standard Microsoft HIPAA BAA |
| Enterprise LLM API | Per-vendor; check at engagement scoping | Pending | Required for healthcare-related work |

### 6.3 Federal Contract Flow-Down

For vendors used in federal work:
- DFARS 252.204-7012 compliance required (CUI)
- FedRAMP High authorization (or equivalent)
- Made in U.S.A. requirements if applicable
- Security clearance for personnel accessing CUI

---

## 7. Ongoing Vendor Monitoring

### 7.1 Continuous Monitoring

**Daily/Automatic:**
- API availability and latency (monitoring dashboards)
- Error rates and anomalies
- Usage against quotas

**Weekly:**
- Review vendor security advisories
- Check for service announcements or changes
- Monitor vendor news for security incidents

**Monthly:**
- Usage and cost analysis
- Performance trends
- Compare against SLA commitments

### 7.2 Quarterly Vendor Review

For each active vendor, conduct quarterly review:

1. **Performance assessment:**
   - Uptime met SLA? (target: 99.5%+)
   - Incidents or outages?
   - Support responsiveness?

2. **Security update:**
   - Any reported vulnerabilities?
   - Certifications still current?
   - Policy changes?

3. **Cost review:**
   - Actual vs. budgeted spend
   - Cost optimization opportunities
   - Pricing changes

4. **Continuing need:**
   - Still using this vendor?
   - Better alternatives available?
   - Consolidation opportunities?

### 7.3 Annual Vendor Recertification

Annual recertification includes:
- Full vendor assessment scorecard refresh
- Contract review and renewal decision
- DPA/BAA confirmation
- Security certification verification
- Formal approval renewal

---

## 8. Vendor Risk Assessment

### 8.1 Risk Categories

| Risk | Description | Likelihood | Impact | Mitigation |
|------|-------------|------------|--------|------------|
| **Data breach at vendor** | Vendor security incident exposes client data | Medium | High | Encryption, DPA, incident response plan |
| **Service outage** | Vendor unavailable, impacting production | Medium | Medium | Multi-vendor strategy, graceful degradation |
| **Model degradation** | Vendor AI quality degrades | Low | Medium | Performance monitoring, alternative providers |
| **Pricing changes** | Vendor raises prices significantly | Medium | Medium | Budget buffer, multi-vendor options |
| **Policy changes** | Vendor changes terms of service | Medium | Low | 30-day notice requirement, contract terms |
| **Vendor exit** | Vendor discontinues service | Low | High | Data portability, abstraction layer |
| **Compliance failure** | Vendor fails regulatory requirement | Low | High | Due diligence, audit rights, indemnification |

### 8.2 Risk Mitigation Strategies

**Multi-Vendor Strategy:**
- Don't over-rely on single vendor for critical capabilities
- Maintain abstraction layers for easy vendor switching
- Keep alternatives evaluated and ready

**Data Protection:**
- Encrypt data before sending to vendors where possible
- Minimize data sent to vendors (data minimization)
- Use vendor data residency controls

**Contractual Protection:**
- Indemnification for vendor-caused failures
- Audit rights
- Exit provisions with data return/deletion
- Change notification requirements

**Technical Resilience:**
- Graceful degradation when vendor unavailable
- Caching and fallback mechanisms
- Regular backup of vendor-dependent configurations

---

## 9. Vendor Incident Management

### 9.1 Vendor Incident Triggers

**Immediate escalation required if vendor reports:**
- Security breach affecting customer data
- Unauthorized access to systems
- Service outage >4 hours
- Compliance certification loss
- Material terms of service changes

### 9.2 Response Procedure

1. **Assess impact:** What data/systems are affected?
2. **Communicate:** Notify affected clients if needed
3. **Contain:** Suspend vendor integration if necessary
4. **Document:** Record incident details and vendor response
5. **Recover:** Resume operations when vendor issue resolved
6. **Review:** Post-incident analysis, update risk assessment

### 9.3 Vendor Incident Log

Track all vendor incidents:
- Date and time
- Vendor name
- Incident description
- Impact to 12th House AI/clients
- Vendor response
- Resolution timeline
- Follow-up actions

---

## 10. Vendor Exit Management

### 10.1 Exit Triggers

- Contract expires and not renewing
- Vendor fails to meet requirements
- Better alternative available
- Vendor discontinues service
- Vendor acquired or exits market

### 10.2 Exit Procedure

1. **Notice:** Provide required notice per contract
2. **Data:** Request full data export in usable format
3. **Deletion:** Request vendor data deletion with written confirmation
4. **Transition:** Migrate to alternative vendor or internal solution
5. **Verification:** Confirm data deleted, access revoked
6. **Documentation:** Update vendor inventory, archive records

### 10.3 Data Portability Requirements

Before selecting vendors, confirm:
- Data can be exported in standard formats
- No proprietary lock-in for model weights or configurations
- Reasonable timeline for data export (30 days max)
- Written deletion confirmation available

---

## 11. Vendor Category Profiles

Specific vendor identities are recorded in the per-engagement Vendor Management record under change control, not published in this procedure. The category profiles below describe the *controls* applied to each kind of vendor.

### 11.1 Enterprise LLM API Provider (primary)

**Use:** Primary LLM for code generation, analysis, documentation

**Tier:** Business/Enterprise

**Data Allowed:** Public, Internal, Confidential (per DPA)

**DPA Requirement:** Executed before any non-public data flows

**Security Baseline:** SOC 2 Type II, encryption, no training on prompts by default

**Restrictions:**
- For federal-facing engagements, the selected provider must be federally cleared. Providers under federal supply-chain restriction are excluded from federal-facing client work; private/internal company use is governed separately.
- For foreign-AI-prohibited engagements (e.g., Advancing American AI Act §7223 flow-down), the selected provider must not contain a prohibited foreign-AI component.
- No CUI without an appropriate sovereign-cloud or federally-authorized deployment path.
- No PHI without a Business Associate Agreement on the enterprise tier.

**Renewal Cadence:** Annual

---

### 11.2 Voice Synthesis Platform

**Use:** Voice synthesis for AI workflow products

**Tier:** Business

**Data Allowed:** Internal, Confidential (per DPA)

**DPA Requirement:** Executed

**Security Baseline:** SOC 2, encryption

**Restrictions:**
- No PHI until BAA executed
- Voice cloning requires explicit consent documentation
- Voice-data retention per retention policy (default 30 days)

**HIPAA Ready:** Pending BAA execution

**Renewal Cadence:** Annual

---

### 11.3 Voice Agent Conversation Platform

**Use:** Voice agent conversation platform

**Tier:** Business

**Data Allowed:** Internal, Confidential

**DPA Requirement:** In progress at intake

**Security Baseline:** Encryption, access controls

**Restrictions:**
- No PHI until HIPAA compliance confirmed
- No CUI unless the specific vendor is FedRAMP-authorized

**Renewal Cadence:** Annual

---

### 11.4 Multi-Model API Gateway

**Use:** Routed access to multiple LLM providers (testing, non-sensitive workloads)

**Tier:** Standard

**Data Allowed:** Public, Internal only

**DPA Status:** Standard terms

**Security Baseline:** Basic encryption

**Restrictions:**
- Do NOT use for confidential or regulated data
- Use only for testing and non-sensitive workloads
- Underlying-model selection at the gateway must itself satisfy federal-facing / foreign-AI-exclusion rules for any in-scope engagement

---

### 11.5 Microsoft Azure AI Services

**Use:** Enterprise AI platform, hosted models, Cognitive Services

**Tier:** Enterprise Agreement

**Data Allowed:** All (commercial cloud)

**DPA Status:** Microsoft Online Services DPA

**Security:** SOC 2, ISO 27001, FedRAMP (GovCloud), HIPAA BAA available

**Compliance:**
- Standard commercial: SOC 2, HIPAA ready
- GovCloud: FedRAMP High, IL5, CUI approved

**Restrictions:**
- GovCloud required for CUI workloads
- Additional cost for Gov-specific services

**Renewal Date:** Per EA terms

**Alternative:** AWS AI, Google Cloud AI

---

## 12. Documentation and Records

Maintain the following vendor records:

- Vendor inventory (current list with status)
- Assessment scorecards (selection and annual)
- Contracts and DPAs
- BAAs (for HIPAA vendors)
- Incident log
- Quarterly review notes
- Annual recertification records

**Retention:** 3 years past vendor relationship end

---

**Document Revision History:**

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | Feb 1, 2026 | Brannon Solomon | Initial vendor management procedure for ISO 42001 |
