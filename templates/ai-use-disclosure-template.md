# AI Use Disclosure — Per-Engagement

**Customer-Facing One-Page Disclosure**

**12th House AI, LLC** · Veteran-owned · Virginia Beach, VA
Source framework: `github.com/Obsidian757/ai-governance-framework`

---

> **Purpose.** This one-pager is filled in *per engagement* and shared with the client (and, where applicable, the prime contractor and the customer's privacy / records officer) before AI-assisted work begins. It names the AI systems in use, the data they will touch, the human-in-the-loop checkpoints, the audit trail, and the incident contact. It is the artifact procurement officers and grant compliance reviewers ask for when "how is AI being used on this engagement?" comes up.
>
> Pair this disclosure with the matching system-prompt controls template (`federal-contractor-system-prompt-security-controls-template.md` for federal-contractor scope, `state-local-gov-system-prompt-security-controls-template.md` for Virginia state/local scope). This disclosure documents *what is in use on this specific engagement*; the controls template documents *how the AI system is governed*.
>
> **Mirror-verb discipline.** This disclosure documents what 12th House AI uses, how it is hosted, and how it is governed. It does not claim certification under any framework. Where alignment is stated, the language is *aligns with* / *maps to* / *operationalizes* — never *certified to*.

---

## SECTION 1 — Engagement Identification

| Field | Value |
|---|---|
| Engagement / project name | [PROJECT NAME] |
| Client / customer organization | [CLIENT LEGAL NAME] |
| Customer point of contact | [NAME, TITLE, EMAIL] |
| Engagement scope summary (one sentence) | [ONE-LINE SUMMARY] |
| Engagement type | [DIRECT / SUBCONTRACTED VIA PRIME / GRANT-FUNDED / RFP RESPONSE / PILOT] |
| Prime contractor (if subcontracted) | [PRIME NAME or N/A] |
| Subcontract / contract / grant ID | [NUMBER or N/A] |
| Engagement start / end | [START DATE] — [END DATE] |
| Disclosure version | v[N] dated [YYYY-MM-DD] |
| Prepared by | [NAME, TITLE, 12th House AI] |
| Customer acknowledgement | [NAME, TITLE, SIGNATURE / DATE — captured at engagement kickoff] |

---

## SECTION 2 — Regulatory Posture

Regulatory regimes that apply to this engagement (check all that apply, fill in the section that lists scope-specific identifiers):

- [ ] **Federal contractor / defense** — DFARS 252.204-7012, NIST SP 800-171, FAR 52.204-21, OMB M-25-21 / M-25-22, EO 14179, CUI Program (32 CFR Part 2002)
- [ ] **Virginia state / local government** — Virginia EO 30, VITA Commonwealth Information Security Standard (SEC525 family), VITA Enterprise Architecture Standard EA-225, Virginia Public Procurement Act (Va. Code § 2.2-4300 *et seq.*), Virginia Public Records Act (Va. Code § 42.1-76 *et seq.*), Virginia FOIA (Va. Code § 2.2-3700 *et seq.*)
- [ ] **Federal funds passing through (grant or pass-through)** — OMB M-24-10, OMB M-24-18, 2 CFR Part 200 Uniform Guidance
- [ ] **Privacy / consumer data** — Privacy Act of 1974 (federal), VCDPA (Virginia Consumer Data Protection Act), Va. Code § 18.2-186.6 breach notification
- [ ] **Vertical regimes** — [HIPAA / FERPA / COPPA / VAWA / HUD HMIS / Title IV-E / USDA TEFAP / PCI-DSS / IRS Publication 1075 / CJIS / ITAR / EAR — list applicable]
- [ ] **Other** — [identify]

**Cross-cutting framework alignment:** NIST AI Risk Management Framework 1.0 (*GOVERN / MAP / MEASURE / MANAGE*). ISO/IEC 42001:2023 is used as the AIMS implementation framework.

**Credential posture for this engagement:**
- 12th House AI does **not** hold and is **not** pursuing ISO 42001 organizational certification, CMMC certification or CMMC Registered Practitioner status, FedRAMP authorization, or 8(a) / HUBZone / WOSB designations.
- **In process — not yet granted, not yet claimed:** SDVOSB (federal, via SBA VetCert — gated on SAM.gov CAGE-code issuance) and SWaM-V (Virginia state, via DSBSD — application #845183, projected decision July–August 2026). Until granted, these are not claimed and corresponding socioeconomic boxes are not checked on federal or state solicitations.

---

## SECTION 3 — AI Systems In Use on This Engagement

| AI System | Role | Model / Version | Provider | Hosting Jurisdiction | Tenancy / Boundary |
|---|---|---|---|---|---|
| [SYSTEM 1] | [primary inference / drafting / classification / RAG retrieval / etc.] | [MODEL NAME + VERSION] | [PROVIDER NAME] | [U.S. — region, e.g., us-east-1; GovCloud; GCC-High; on-prem; customer-VPC] | [shared multi-tenant / single-tenant / customer-controlled / on-premises] |
| [SYSTEM 2] | [fallback / specialized task] | [MODEL NAME + VERSION] | [PROVIDER NAME] | [HOSTING] | [TENANCY] |
| [SYSTEM 3] | [embedding / vector store / orchestrator] | [MODEL / SERVICE] | [PROVIDER] | [HOSTING] | [TENANCY] |

**Foreign-AI exclusion (federal-scope engagements):** Where the engagement involves CUI, source-selection information, or federal contract data, no foreign-developed AI components are used. Provenance verification is documented per Advancing American AI Act § 7223 posture. *[Confirmed for this engagement on [DATE] / Not applicable — engagement is non-federal]*

**Authorization boundary (where required):** [FedRAMP Moderate / FedRAMP High / DoD IL4 / DoD IL5 / state-equivalent / customer environment / N/A — name the boundary that applies and the provider's authorization that covers it]

**Version-pinning posture:** [Models are version-pinned for the duration of this engagement / Provider may rotate the underlying model — risk and re-baseline cadence documented below]

---

## SECTION 4 — Data the AI Will Touch

| Data Category | In Scope? | Source | Where Stored | Retention |
|---|---|---|---|---|
| Public records / open data | [Y/N] | [SOURCE] | [STORAGE] | [RETENTION] |
| Proprietary or NDA-protected data | [Y/N] | [SOURCE] | [STORAGE] | [RETENTION] |
| Controlled Unclassified Information (CUI) | [Y/N — if Y, list categories from CUI Registry] | [SOURCE] | [STORAGE] | [RETENTION] |
| FOIA-exempt records (state/local) | [Y/N — if Y, list applicable Va. Code § 2.2-3705 exemptions] | [SOURCE] | [STORAGE] | [RETENTION] |
| Personally Identifiable Information (PII) | [Y/N — if Y, list categories: name, address, SSN, DOB, financial, biometric, clearance] | [SOURCE] | [STORAGE] | [RETENTION] |
| Protected Health Information (PHI) | [Y/N] | [SOURCE] | [STORAGE] | [RETENTION] |
| Education records (FERPA) | [Y/N] | [SOURCE] | [STORAGE] | [RETENTION] |
| Procurement-sensitive (pre-award) | [Y/N] | [SOURCE] | [STORAGE] | [RETENTION] |
| Export-controlled (ITAR / EAR) | [Y/N] | [SOURCE] | [STORAGE] | [RETENTION] |
| Other regulated category | [SPECIFY] | [SOURCE] | [STORAGE] | [RETENTION] |

**Data flow (one paragraph, client-readable):**
> [Plain-English narrative: where the data originates, who transfers it, how it reaches the AI system, what the AI does with it, where outputs go, who reviews outputs, and where the audit trail is written. Avoid jargon. Two to four sentences.]

**Training / fine-tuning posture:** [Customer data is NOT used to train any provider's models — confirmed per provider enterprise terms / Customer data is used to fine-tune a customer-controlled model only, never a provider's foundation model / Other — specify].

---

## SECTION 5 — Risk Classification

**NIST AI RMF risk tier for this engagement:** [LOW / MODERATE / HIGH] — *justification:*
> [One sentence on why this tier — typically driven by sensitivity of data, reversibility of decisions the AI informs, and population affected.]

**VITA EA-225 risk classification (Virginia state/local engagements only):** [LOW / MODERATE / HIGH / N/A — non-VA] — *justification:*
> [One sentence.]

**OMB M-25-21 categorization (federal engagements only):** [Rights-impacting / Safety-impacting / Neither / N/A — non-federal] — *justification:*
> [One sentence.]

**High-risk-use-case indicators (check any that apply):**
- [ ] AI output informs a decision affecting an individual's rights, benefits, services, or obligations
- [ ] AI output informs a decision with safety implications
- [ ] AI output is consumed by an external regulator, court, or compliance auditor
- [ ] AI output cites regulations, statutes, contract identifiers, or dollar figures
- [ ] AI system handles a protected class as a feature, target, or proxy
- [ ] AI system operates without a real-time human reviewer in the loop

Any checked box triggers categorical human review of every AI-assisted output before delivery, per Section 6.

---

## SECTION 6 — Human-in-the-Loop Checkpoints

| Workflow Stage | AI Role | Human Reviewer | Reviewer Authority | Required Before |
|---|---|---|---|---|
| [Stage 1, e.g., intake summarization] | [Drafts / classifies / suggests] | [Name, Title] | [Approve / reject / modify] | [Next step in workflow] |
| [Stage 2, e.g., compliance crosswalk] | [Drafts / cites / cross-checks] | [Name, Title] | [Approve / reject / modify] | [Next step] |
| [Stage 3, e.g., final deliverable] | [Drafts] | [Name, Title — typically 12th House AI principal] | [Sign-off] | [Delivery to client] |
| [Stage 4, e.g., client review] | [None — human-authored summary only] | [Client POC, Title] | [Accept / request revision] | [Acceptance] |

**Decisions the AI system is NOT authorized to make on this engagement** (list explicitly — at minimum, anything triggered by a Section 5 high-risk indicator):
- [Make final FOIA exemption determinations]
- [Approve or deny benefit / eligibility / clearance / classification decisions]
- [Issue enforcement findings or penalties]
- [Release public records or CUI on its own determination]
- [Interpret contract terms in a manner binding on any party]
- [Cite a regulation or statute that has not been retrieved from an authoritative source and verified by a human reviewer]
- [Add or modify named entities, dollar figures, or contract identifiers in a customer-facing output without grounded retrieval]

---

## SECTION 7 — Audit Trail and Logging

**What is logged on this engagement:**
- [ ] Every AI request and the retrieved-context summary
- [ ] Every AI-assisted output (with model, version, timestamp)
- [ ] Every human review action (approve / modify / reject)
- [ ] Every declined request (any tier)
- [ ] Every security-threat detection
- [ ] Every hallucination-incident detection and resolution

**Where logs are stored:** [STORAGE SYSTEM — e.g., customer-controlled environment / 12th House AI engagement workspace / shared with prime per subcontract]

**Retention period:** [DURATION — minimum 3 years for federal-contractor scope per DFARS 252.204-7012 preservation; per Library of Virginia retention schedule for state/local; per grant award terms for federally-funded grants; per engagement contract otherwise]

**Log access:** [Restricted to: 12th House AI engagement lead, named client reviewer, prime contractor if subcontracted delivery, authorized auditors]

---

## SECTION 8 — Incident Contacts and Reporting Cadence

| Role | Name | Title | Email | Phone | Reporting Window |
|---|---|---|---|---|---|
| 12th House AI engagement lead | Brannon Joseph Solomon Jr. | Founder | info@12thhouseai.com | 757.502.3594 | First contact for any AI-related concern |
| 12th House AI security / privacy contact | [NAME] | [TITLE] | [EMAIL] | [PHONE] | [WINDOW] |
| Client point of contact | [NAME] | [TITLE] | [EMAIL] | [PHONE] | [WINDOW] |
| Prime contractor security contact (if subcontracted) | [NAME] | [TITLE] | [EMAIL] | [PHONE] | [WINDOW] |
| Customer privacy officer / records custodian | [NAME] | [TITLE] | [EMAIL] | [PHONE] | [WINDOW] |

**Federal cyber-incident reporting (federal-contractor scope only):** Reportable cyber incidents under DFARS 252.204-7012(c) are reported to DoD via DIBNet within 72 hours of discovery, in addition to (not in lieu of) any prime-contractor reporting obligation.

**State / local incident reporting (Virginia scope only):** Citizen-PII breaches trigger Va. Code § 18.2-186.6 notification timelines. VITA SEC525 incident-reporting expectations apply where the customer is a Commonwealth agency.

---

## SECTION 9 — Client Rights on This Engagement

- **Right to Explanation.** The client may request, at any time, an explanation of any AI-assisted output — what model produced it, what context the model retrieved, and which human reviewed it.
- **Right to Appeal.** The client may challenge any AI-assisted output and request human-only re-work. Re-work is provided at no additional cost on this engagement.
- **Right to Data.** The client owns its data. 12th House AI deletes engagement data on instruction and at end-of-engagement per the data-handling terms in the engagement contract.
- **Right to Audit.** The client (or its designated auditor) may inspect the engagement audit trail described in Section 7 on reasonable notice.
- **Right to Update.** This disclosure is updated when AI systems, data scope, or risk classification materially change. The client receives the updated version before the change takes effect.

---

## SECTION 10 — AI Provenance Statement

This disclosure was drafted with the assistance of a large language model under human review. The 12th House AI engagement lead named in Section 8 is accountable for every statement in this document. No AI system in the 12th House AI workflow makes consequential client-facing decisions without a human-in-the-loop checkpoint as described in Section 6.

---

**Signatures**

**12th House AI:**
Name: ______________________________  Title: ______________________________
Signature: ___________________________  Date: ______________________________

**Client / Customer:**
Name: ______________________________  Title: ______________________________
Signature: ___________________________  Date: ______________________________

**Prime Contractor (if subcontracted delivery):**
Name: ______________________________  Title: ______________________________
Signature: ___________________________  Date: ______________________________

---

**12th House AI, LLC** · Federal & Public-Sector AI Governance · Veteran-owned, Virginia Beach, VA
Source framework: `github.com/Obsidian757/ai-governance-framework`
Contact: info@12thhouseai.com

© 2026 12th House AI, LLC. All rights reserved.
