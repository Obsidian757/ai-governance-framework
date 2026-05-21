# 12th House AI — ISO 42001-Aligned AIMS Gap Analysis

**Assessment Date:** January 31, 2026  
**Assessor:** Brannon Solomon (Self-Assessment)  
**Purpose:** Evaluate the 12th House AI internal AIMS against the ISO/IEC 42001:2023 framework as the implementation spine. **No certification is being claimed or pursued.** This document is published as a worked example of the framework — the same kind of gap analysis 12th House AI produces for client engagements.

---

## Executive Summary

**Overall Readiness: 65%**

12th House AI has a strong foundation for ISO 42001-aligned AIMS implementation due to existing NIST AI RMF expertise, operational AI systems, and deep federal/state AI policy knowledge. Primary gaps are in formal documentation, metrics tracking, and audit processes.

**Critical Path Items (Must Complete):**
1. Document AI lifecycle processes for VoiceGuard/RMF Navigator
2. Create and populate AI risk register
3. Establish metrics tracking system
4. Conduct initial internal audit
5. Complete Annex A controls assessment

**Estimated Effort to Close Gaps:** 40-50 hours over 4 weeks (achievable with AI assistance)

---

## Gap Analysis by Clause

### Clause 4: Context of the Organization

**Requirement:** Understand internal/external issues, stakeholders, and scope of AIMS.

| Sub-requirement | Current State | Gap | Evidence | Action Needed |
|-----------------|---------------|-----|----------|---------------|
| 4.1: External/internal issues | ✅ **Strong** - Deep understanding of federal AI landscape, OMB memos, defense contractor needs | None | Context doc, OMB memo research | Document formally in AIMS scope |
| 4.2: Stakeholder needs | ✅ **Strong** - Know clients (defense contractors), partners (NavalX, 757 Collab), regulators (DoD, OMB) | Minor | Business relationships, conversations | Create stakeholder register |
| 4.3: AIMS scope | 🟡 **Partial** - Know what's in scope but not formally defined | **Moderate** | None | Write scope statement (done in policy) |
| 4.4: AI management system | 🟡 **Partial** - Processes exist informally | **Moderate** | Existing methodologies (5% Framework, Mission Planning) | Document processes formally |

**Clause 4 Readiness: 70%**

**Priority Actions:**
1. Create stakeholder register (clients, partners, regulators, employees)
2. Document internal/external issues affecting AI work
3. Finalize AIMS scope boundaries

---

### Clause 5: Leadership

**Requirement:** Top management demonstrates commitment, establishes policy, assigns responsibilities.

| Sub-requirement | Current State | Gap | Evidence | Action Needed |
|-----------------|---------------|-----|----------|---------------|
| 5.1: Leadership commitment | ✅ **Strong** - Founder-led, AI compliance is core business | None | Business strategy, client work | Sign policy statement |
| 5.2: AI policy | 🔴 **Missing** - No formal policy document | **Critical** | None | **CREATED - needs signature** |
| 5.3: Roles/responsibilities | 🟡 **Partial** - Solo founder wears all hats, but roles clear | Minor | Job functions | Document in policy (done) |

**Clause 5 Readiness: 60%**

**Priority Actions:**
1. ✅ **COMPLETE:** AI policy created, needs formal signature
2. Document delegation plan for future growth

---

### Clause 6: Planning

**Requirement:** Address risks/opportunities, set objectives, plan for changes.

| Sub-requirement | Current State | Gap | Evidence | Action Needed |
|-----------------|---------------|-----|----------|---------------|
| 6.1: Risk assessment | 🟡 **Partial** - Understand AI risks conceptually but no formal register | **High** | Knowledge of bias, privacy, security risks | Create AI risk register |
| 6.2: AI objectives | ✅ **Strong** - Clear objectives (90-day cycles, 5% Framework, compliance) | Minor | Client engagements, frameworks | Document in policy (done) |
| 6.3: Planning changes | 🟡 **Partial** - Monitor regulations but no formal change process | **Moderate** | Regulatory monitoring habits | Document change management process |

**Clause 6 Readiness: 55%**

**Priority Actions:**
1. **Create AI risk register** with existing VoiceGuard/RMF Navigator risks
2. Document risk assessment methodology
3. Create change management procedure

---

### Clause 7: Support

**Requirement:** Provide resources, competence, awareness, communication, documentation.

| Sub-requirement | Current State | Gap | Evidence | Action Needed |
|-----------------|---------------|-----|----------|---------------|
| 7.1: Resources | ✅ **Strong** — Tech stack (enterprise LLM API, voice synthesis, Azure cloud), budget control | None | Tools in use, financial control | Document resource allocation |
| 7.2: Competence | ✅ **Strong** - 20 years DoD, Master's, NIST expert, security clearance | None | Resume, credentials, clearance | Document competency matrix |
| 7.3: Awareness | 🟡 **Partial** - Personal knowledge high, no formal training program | Minor | Self-training, research | Create training records |
| 7.4: Communication | 🟡 **Partial** - Strong external comms (LinkedIn), informal internal | Minor | Thought leadership, client comms | Document communication plan |
| 7.5: Documented info | 🟡 **Partial** - Some documentation exists, not complete | **Moderate** | Context doc, frameworks, client deliverables | Centralize and organize |

**Clause 7 Readiness: 70%**

**Priority Actions:**
1. Create competency matrix documenting skills/credentials
2. Record training/self-learning activities (LLM tool usage, research)
3. Organize documentation repository

---

### Clause 8: Operation

**Requirement:** Plan and control AI lifecycle from design to decommissioning.

| Sub-requirement | Current State | Gap | Evidence | Action Needed |
|-----------------|---------------|-----|----------|---------------|
| 8.1: Operational planning | 🟡 **Partial** - Mission Planning Framework structures engagements | **Moderate** | Client SOWs, project plans | Map to AI lifecycle |
| 8.2: AI impact assessment | 🟡 **Partial** - Consider impacts but no formal assessment | **High** | Conceptual understanding | Create impact assessment template |
| 8.3: Data management | ✅ **Strong** - Understand CUI, PII, HIPAA requirements | Minor | Federal compliance work | Document data governance |
| 8.4: Data quality | 🟡 **Partial** - Quality considerations in VoiceGuard | **Moderate** | VoiceGuard testing | Document quality criteria |
| 8.5: AI system development | 🟡 **Partial** - Build VoiceGuard agents, no formal process doc | **High** | VoiceGuard deployments | **Document lifecycle** |
| 8.6: Third-party relationships | ✅ **Strong** — Use of LLM API, voice synthesis, voice agent platforms with documented selection criteria | Minor | Vendor selection, usage | Document vendor management |

**Clause 8 Readiness: 60%**

**Priority Actions:**
1. **Document AI lifecycle** (Design → Develop → Deploy → Monitor → Retire)
2. Create AI impact assessment template
3. Document VoiceGuard development process as example
4. Formalize data governance procedures

---

### Clause 9: Performance Evaluation

**Requirement:** Monitor, measure, analyze, audit, and review AIMS.

| Sub-requirement | Current State | Gap | Evidence | Action Needed |
|-----------------|---------------|-----|----------|---------------|
| 9.1: Monitoring/measurement | 🔴 **Missing** - No formal metrics tracking | **Critical** | Ad-hoc monitoring | **Define and track metrics** |
| 9.2: Internal audit | 🔴 **Missing** - Never conducted formal AIMS audit | **Critical** | None | **Conduct internal audit** |
| 9.3: Management review | 🟡 **Partial** - Regular self-reflection, not formalized | **Moderate** | Strategic planning sessions | Document management reviews |

**Clause 9 Readiness: 25%**

**Priority Actions:**
1. **Define AI governance metrics** (uptime, incidents, compliance)
2. **Conduct first internal audit** against ISO 42001 requirements
3. Schedule quarterly management review meetings
4. Create audit checklist and report template

---

### Clause 10: Improvement

**Requirement:** Handle nonconformities, take corrective action, continually improve.

| Sub-requirement | Current State | Gap | Evidence | Action Needed |
|-----------------|---------------|-----|----------|---------------|
| 10.1: Nonconformity & correction | 🟡 **Partial** - Fix issues when found, not formal process | **Moderate** | Problem-solving approach | Document incident response |
| 10.2: Continual improvement | ✅ **Strong** - Iterate frameworks, learn from engagements | Minor | Updated methodologies, feedback loops | Document improvement process |

**Clause 10 Readiness: 65%**

**Priority Actions:**
1. Create incident response procedure
2. Document corrective action process
3. Formalize lessons-learned capture

---

## Annex A Controls Assessment

Annex A contains 39 controls. Below is the assessment of applicability and current state for each.

### Control Categories

**Governance Controls (1-6):**
| Control | Title | Applicable? | Current State | Gap |
|---------|-------|-------------|---------------|-----|
| 5.1 | Policies for the use of AI | ✅ Yes | 🟡 Partial | **Policy created, needs adoption** |
| 5.2 | Roles and responsibilities | ✅ Yes | ✅ Strong | Defined in policy |
| 5.3 | Accountability | ✅ Yes | ✅ Strong | Clear ownership |
| 6.1 | Actions to address risks and opportunities | ✅ Yes | 🟡 Partial | **Risk register needed** |
| 6.2 | AI objectives and planning | ✅ Yes | ✅ Strong | Objectives clear |

**Organizational Controls (7-10):**
| Control | Title | Applicable? | Current State | Gap |
|---------|-------|-------------|---------------|-----|
| 7.1 | Resources | ✅ Yes | ✅ Strong | Tech stack in place |
| 7.2 | Competence | ✅ Yes | ✅ Strong | Credentials documented |
| 7.3 | Awareness | ✅ Yes | 🟡 Partial | Training records needed |
| 7.4 | Communication | ✅ Yes | 🟡 Partial | Communication plan needed |
| 7.5 | Documented information | ✅ Yes | 🟡 Partial | **Documentation gaps** |

**Operational Controls (11-25):**
| Control | Title | Applicable? | Current State | Gap |
|---------|-------|-------------|---------------|-----|
| 8.1 | Operational planning and control | ✅ Yes | 🟡 Partial | **Lifecycle documentation** |
| 8.2 | AI impact assessment | ✅ Yes | 🟡 Partial | **Template needed** |
| 8.3 | Data management | ✅ Yes | ✅ Strong | Federal compliance knowledge |
| 8.4 | Data quality | ✅ Yes | 🟡 Partial | Quality criteria needed |
| 8.5 | AI system development lifecycle | ✅ Yes | 🟡 Partial | **Process documentation** |
| 8.6 | Management of AI system suppliers | ✅ Yes | ✅ Strong | Vendor oversight exists |
| 8.7 | Transparency and explainability | ✅ Yes | 🟡 Partial | Explainability mechanisms needed |
| 8.8 | Human oversight | ✅ Yes | ✅ Strong | Human-in-loop design |
| 8.9 | Accuracy, robustness, cybersecurity | ✅ Yes | ✅ Strong | Security expertise |
| 8.10 | Privacy protection | ✅ Yes | ✅ Strong | PII/CUI protection knowledge |
| 8.11 | Identification and traceability | ✅ Yes | 🟡 Partial | Traceability logging needed |
| 8.12 | Business continuity | ✅ Yes | 🟡 Partial | Backup plans needed |
| 8.13 | Incident and anomaly detection | ✅ Yes | 🟡 Partial | **Monitoring setup** |
| 8.14 | Validation and testing | ✅ Yes | 🟡 Partial | Testing procedures needed |
| 8.15 | Capacity, backup, archiving | ✅ Yes | 🟡 Partial | Backup documentation |

**Monitoring Controls (26-30):**
| Control | Title | Applicable? | Current State | Gap |
|---------|-------|-------------|---------------|-----|
| 9.1 | Monitoring, measurement, analysis, evaluation | ✅ Yes | 🔴 Missing | **Metrics system** |
| 9.2 | Internal audit | ✅ Yes | 🔴 Missing | **First audit needed** |
| 9.3 | Management review | ✅ Yes | 🟡 Partial | **Formal reviews** |

**Improvement Controls (31-39):**
| Control | Title | Applicable? | Current State | Gap |
|---------|-------|-------------|---------------|-----|
| 10.1 | Nonconformity and corrective action | ✅ Yes | 🟡 Partial | Incident process needed |
| 10.2 | Continual improvement | ✅ Yes | ✅ Strong | Framework iteration |

**Controls Marked Not Applicable (with justification):**
- *None at this time.* All controls apply to AI consulting and product development work.

**Annex A Readiness: 60%**

---

## Priority Gap Closure Plan

### Week 1 (Feb 3-9): Documentation Foundation
**Critical Items:**
- [x] AI Management System Policy (COMPLETE - `docs/12th-house-ai-policy.md`)
- [x] AI Risk Register (COMPLETE - `docs/risk-register.md`)
- [x] Stakeholder Register (COMPLETE - `templates/stakeholder-register.md`)
- [x] AI Lifecycle Process Document (COMPLETE - `docs/ai-lifecycle-process.md`)
- [x] AI Impact Assessment Template (COMPLETE - `templates/ai-impact-assessment.md`)

**Hours:** ~15 hours ✅ COMPLETE

### Week 2 (Feb 10-16): Evidence & Processes
**High Priority:**
- [x] Competency Matrix (COMPLETE - `docs/competency-matrix.md`)
- [x] Training Records (COMPLETE - included in competency matrix)
- [x] Data Governance Procedures (COMPLETE - `docs/data-governance-procedure.md`)
- [x] Vendor Management Process (COMPLETE - `docs/vendor-management-procedure.md`)
- [x] Communication Plan (COMPLETE - `templates/communication-plan.md`)
- [x] VoiceGuard Development Case Study (COMPLETE - included in lifecycle doc)

**Hours:** ~12 hours ✅ COMPLETE

### Week 3 (Feb 17-23): Monitoring & Audit
**Critical for AIMS framework alignment:**
- [x] Define AI Governance Metrics (COMPLETE - Policy Section 12)
- [x] Set up Metrics Tracking (COMPLETE - `evidence/metrics-tracking.xlsx`)
- [x] Conduct Internal Audit (COMPLETE - use `templates/internal-audit-checklist.md`)
- [ ] Internal Audit Report (IN PROGRESS - conduct audit, save to `evidence/`)
- [ ] Corrective Action Plan (PENDING - document after audit findings)
- [x] Incident Response Procedure (COMPLETE - `docs/incident-monitoring-plan.md`)
- [x] Management Review Meeting Template (COMPLETE - `templates/management-review.md`)

**Hours:** ~18 hours (mostly complete, audit execution remaining)

### Week 4 (Feb 24-28): Internal Audit Readiness
**Final Readiness:**
- [x] Organize all evidence in central repository (`evidence/` folder)
- [x] Create AIMS document index (COMPLETE - `AIMS-operations-manual.md`)
- [ ] Prepare internal-audit briefing materials
- [ ] Complete any remaining corrective actions
- [ ] Final management review and sign-off

**Hours:** ~10 hours

**Total Estimated Effort:** 55 hours over 4 weeks (~14 hours/week, ~2-3 hours/day)

---

## Decision Point — Pursue Independent Certification?

**Decision (revisited May 2026):** 12th House AI is **not** pursuing organizational ISO 42001 certification. The framework is used as the implementation spine for our AIMS and for client AIMS work; independent certification is a client-elected option, not a 12th House AI claim or service offering.

---

## Differentiators (Honest)

**What 12th House AI brings:**

1. **Practitioner-level NIST AI RMF + ISO 42001 framework knowledge** — translated into deliverables a nonprofit ED or state-agency program manager can act on
2. **Vertical compliance literacy** — HUD HMIS, Title IV-E, USDA TEFAP, FERPA/COPPA, VCDPA, VAWA — not just abstract ISO clauses
3. **Active DoD Secret clearance** — for engagements that require it under teaming arrangements
4. **Rapid implementation cadence** — 90-day cycles, not 9-month enterprise timelines
5. **Published proof-of-work** — the AIMS in this repository is the same shape we deliver to clients

**Honest positioning:**

> "Veteran-owned AI governance consultancy that publishes its own AIMS in the open. ISO 42001 framework as the implementation spine; vertical-compliance literacy on top. Not ISO 42001 certified, not SDVOSB, not CMMC."

---

## Next Steps (May 2026)

1. **Continue client outreach** in the nonprofit and state/local-gov lane.
2. **Maintain the AIMS** under change control — every published doc is dated and signed.
3. **Do not pursue independent ISO 42001 certification** unless a specific client engagement requires it and the client funds the certification body engagement directly.

4. **Review Policy** - Read the AI policy created, edit as needed, prepare to sign

**You're 65% there. The remaining 35% is execution, not invention.**
