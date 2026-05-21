# State AI Procurement Policies — Mid-Atlantic / Southeast Coverage

*Reference compiled for 12th House AI, LLC — Virginia Beach, Veteran-Owned. Citations dated; state AI policy is moving quickly through 2026. This document is a consultative reference, not a formal compliance opinion.*

---

## Evaluator's Quick Read

If you run procurement for a state agency, a county, a city, or a nonprofit funded through state pass-through dollars in the mid-Atlantic or Southeast, this document maps your state's AI governance regime to the same framework your peers cite: **NIST AI RMF 1.0**. Six states are covered (VA, MD, NC, WV, TN, SC), with primary-source citations and an honest read on which states have binding procurement teeth versus aspirational strategy. 12th House AI's AI management system (AIMS) is built around NIST AI RMF as the universal frame, with ISO 42001:2023 used as the implementation framework — not as a certification claim. The intent is to give you a single page that lets you say "yes, this vendor speaks our governance language" without having to translate.

---

## Universal Frame: NIST AI RMF 1.0

Every active state AI policy in the mid-Atlantic / Southeast region cites **NIST AI RMF 1.0** as the governing methodology. Virginia's VITA standards, Maryland's Responsible AI Policy, North Carolina's NCDIT framework, and Tennessee's STS 200-POL-007 all reference NIST AI RMF by name. ISO 42001 and CMMC are **not named** in any state AI policy reviewed for this document. The four NIST AI RMF functions — **GOVERN, MAP, MEASURE, MANAGE** — are the vocabulary state officials actually use in vendor reviews and capability statement evaluations. 12th House AI maps every assessment, deliverable, and AIMS artifact to those four functions first, then to state-specific overlays second.

---

## Cross-State Critical Facts

- **PRC-origin AI is explicitly banned or administratively prohibited in three of the six states covered.** Virginia (EO 26, Feb 2025) bans DeepSeek on Commonwealth devices and networks. Tennessee (Gov. Lee, March 6, 2025) bans DeepSeek and Manus on the state network. North Carolina (NCDIT, early 2025) banned DeepSeek administratively. Maryland and South Carolina enforce through procurement review rather than statutory ban — but PRC-origin model components would not survive a high-risk review in either state. Vendors carrying Chinese model lineage in their stack will not survive risk review in the active states.
- **Human-in-the-loop is required for consequential decisions in every active state regime.** This is universal language — no exceptions across VA, MD, NC, TN. Any vendor describing AI as "autonomous" in a benefits, eligibility, or rights-affecting context will be screened out.
- **Maryland is the strictest codified regime** — SB 818 (2024) codifies risk tiers and mandates contractor compliance flow-down on every contract.
- **Tennessee is the most operationally rigorous** — STS AI Review Committee gate plus the Standards Products List for LLM / NLP / LAM tools means vendors clear a real procurement gauntlet before contract.
- **Virginia has strong governance but vetoed statutory teeth** — HB 2094 (the High-Risk AI Developer and Deployer Act) passed the legislature in February 2025 and was vetoed by Gov. Youngkin on March 24, 2025. VITA AI IT Standards plus EO 30 and EO 26 are the operative instruments.
- **North Carolina has a brand-new EO 24** (Gov. Stein, September 2, 2025), built on the NCDIT Responsible Use framework (August 2024). Tier discipline is lighter than MD or TN but governance principles are formal.
- **West Virginia and South Carolina are task-force / strategy only.** WV has HB 5690 (2024) and HB 3187 (2025) standing up an AI Task Force; SC has the Department of Administration's three-pillar strategy ("Protect, Promote, Pursue") and a Center of Excellence. Neither has binding procurement rules yet.

---

## State-by-State Reference

### Virginia

- **Executive Order 30 (Jan 18, 2024)** — "Establishing Additional Safeguards for the Use of Artificial Intelligence in the Commonwealth." Comprehensive state AI standards. Often mis-cited as Executive Directive 1 — the operative instrument is EO 30.
- **Executive Order 26 (Feb 11, 2025)** — Bans DeepSeek AI on Commonwealth devices and networks. AG Miyares joined a 21-state coalition urging a federal PRC-AI ban.
- **VITA EA-225 / VITA AI IT Standards** — The enterprise AI standard. All Commonwealth agencies and suppliers must follow VITA-published AI standards in procurement and use. NIST AI RMF is the explicit reference methodology.
- **HB 2094** — Passed February 2025, **vetoed March 24, 2025**. Would have added impact-assessment and anti-discrimination duties for "high-risk" AI. **Not in force.**
- **AI Task Force** — Convened October 2024 under EO 30.

**How 12th House AIMS maps:** GOVERN — VITA-aligned AI use policy template and inventory cadence. MAP — agency use-case intake and risk screening (aligned to VITA risk-based approach). MEASURE — bias / privacy / security testing artifacts tied to EO 30 §3 directives. MANAGE — incident response and human-in-the-loop documentation for consequential decisions. Foreign-AI provenance attestation included by default in every deliverable.

### Maryland

- **Executive Order 01.01.2024.02 (Jan 8, 2024)** — Gov. Wes Moore's directive "Catalyzing the Responsible and Productive Use of Artificial Intelligence in Maryland State Government."
- **SB 818 — Artificial Intelligence Governance Act of 2024** (signed May 2024) — Codifies inventory and assessment duties. Each state unit must inventory systems using high-risk AI. **Agencies must require contractors to comply with the State's Responsible AI Policy as a contract term** — this is the flow-down.
- **Maryland Responsible AI Policy (DoIT)** — Operational implementation, updated 2025. Risk tiers (high-risk = AI affecting safety, civil liberties, equal opportunity, access to essential services, or privacy) map directly to NIST AI RMF. Vendors must disclose intended use, data sources, training-data provenance, performance metrics, and known limitations at procurement intake. Bias testing required for high-risk uses.

**How 12th House AIMS maps:** GOVERN — written Responsible AI policy template that mirrors DoIT structure, contractor flow-down language for sub-tier vendors. MAP — high-risk classification screening that mirrors SB 818 categories. MEASURE — bias-testing protocol and training-data provenance log. MANAGE — continuous-monitoring cadence aligned to MD conditional-approval pattern (PoC → monitored production). NIST AI RMF function tags on every artifact.

### North Carolina

- **Executive Order 24 (Sept 2, 2025)** — "Advancing Trustworthy Artificial Intelligence That Benefits All North Carolinians," signed by Gov. Josh Stein. Supersedes informal guidance.
- **NCDIT Responsible Use of Artificial Intelligence Framework** (August 2024) — Still operative as governance baseline. Coordinates strategy, standards, security, and procurement practices across executive agencies.
- **AI Accelerator (within NCDIT)** — Sets vendor evaluation criteria. AI Oversight Teams in each agency review vendor AI before deployment. Higher scrutiny for AI affecting benefits / eligibility decisions.
- **PRC-origin AI ban (administrative)** — NCDIT banned DeepSeek on state devices, early 2025.
- **Public records exposure warning** — NCDIT treats data sent to public generative AI tools as "released to the public" and subject to public records law — an implicit disclosure obligation.

**How 12th House AIMS maps:** GOVERN — agency-level AI use policy template plus the NCDIT public-records risk advisory baked into vendor SOPs. MAP — use-case intake with benefits / eligibility scrutiny flag. MEASURE — fairness / accountability / transparency / security / privacy / civil-liberties test battery (EO 24 named principles). MANAGE — human-in-the-loop documentation for consequential decisions, foreign-AI provenance attestation.

### Tennessee

- **STS 200-POL-007 Enterprise AI Policy** (Strategic Technology Solutions, TN Dept. of Finance & Admin.) plus the Enterprise Generative AI Policy.
- **TN AI Advisory Council Action Plan (Nov 17, 2025)** — Statutorily-required annual report; first published Nov 24, 2025.
- **STS AI Review Committee** — All AI procurements and vendor partnerships must clear this committee before contract.
- **Standards Products List** — Vendor LLM / NLP / LAM tools must appear on the list or pass the Standard Product List Exception Process. Vendors must allow state data governance over data their models consume.
- **PRC-origin AI ban** — Gov. Lee banned DeepSeek and Manus on the state network, March 6, 2025.
- **ELVIS Act (effective July 1, 2024)** — Likeness / voice / image protection against generative AI; not procurement-focused but creates liability exposure for vendors deploying voice/image models in TN.
- **Tennessee Information Protection Act (effective 2025)** — Overlays privacy duties.

**How 12th House AIMS maps:** GOVERN — written AI policy that satisfies STS AI Review Committee intake; Standards Products List exception narrative template. MAP — use-case screen with safety / security / accountability pillar mapping (Action Plan language). MEASURE — vendor disclosure pack (model behavior, data flows, limitations) tuned to STS review format. MANAGE — citizen-facing AI labeling protocol per Generative AI Policy, human-in-the-loop on consequential decisions, ELVIS Act voice / image safeguards.

### West Virginia

- **HB 5690 (2024)** — Created the WV AI Task Force, housed within Office of Technology.
- **HB 3187 (2025)** — Amended §5A-6-9 of WV Code; signed by Gov. Patrick Morrisey April 25, 2025, effective July 9, 2025. Moved the Task Force into the Governor's Office, added an economic-opportunity mandate, requires annual reports. First report due July 1, 2025.
- **No binding procurement rules at the state level as of this writing.** Vendors should expect informal due diligence from the Office of Technology, not a codified intake form.
- **No statewide foreign-AI ban yet.** Vendors should still avoid PRC-origin components given federal trickle-down to federally-funded WV programs.

**How 12th House AIMS maps:** Because WV has no binding state procurement rules yet, the AIMS deliverable here defaults to the NIST AI RMF baseline plus Task-Force-aspirational alignment (data privacy, individual rights, model inventory). Vendors selling into WV state agencies are best served by being ready to demonstrate NIST AI RMF maturity in advance of any forthcoming binding rule — the Task Force's annual reporting cadence makes new rules likely.

### South Carolina

- **South Carolina State Agencies Artificial Intelligence Strategy** (Department of Administration, 2024). No formal AI executive order has been issued by the Governor as of this writing — the strategy serves in lieu of an EO.
- **Center of Excellence + AI Advisory Group** — First COE meeting February 2025. SC Division of Information Security (DIS) is building the AI risk management strategy.
- **SC Supreme Court Interim Policy on Generative AI (March 25, 2025)** — Judicial branch only.
- **"Protect, Promote, Pursue" three-pillar strategy** — Calls for statewide acceptable-use policy, AI procurement standards, and sensitive-data protection. Largely aspirational rather than codified procurement rules.
- **No explicit statewide foreign-AI ban identified.**

**How 12th House AIMS maps:** Same posture as WV — NIST AI RMF baseline, with strategy-pillar alignment language ("Protect, Promote, Pursue") in capability statements. Vendors selling into SC state agencies should be ready for Center of Excellence ad hoc evaluation rather than a published intake form.

---

## Why ISO 42001 Still Matters (Even Though States Don't Name It)

State AI policies tell you **what** to govern: model lineage, risk tiers, bias testing, human-in-the-loop on consequential decisions, vendor disclosures, foreign-AI provenance, inventory cadence. They do not tell you **how** to operationalize those duties as an organization. That is the gap ISO 42001:2023 fills as an implementation framework. ISO 42001 provides the AI management system (AIMS) scaffolding — policies, roles, controls, audit trails, continuous-improvement cycles — that turns NIST AI RMF function descriptions into running operational artifacts.

12th House AI uses ISO 42001 as the framework that organizes the work. We are **not pursuing ISO 42001 certification** and we do not make certified claims. The framework gives clients a coherent way to demonstrate to state procurement officers that NIST AI RMF GOVERN / MAP / MEASURE / MANAGE are not aspirational language in a capability statement — they are operational artifacts with named owners, review cadence, and evidence trails. State policy and ISO 42001 are complementary, not competing.

---

## What 12th House AI Brings

- **Veteran-Owned** (U.S. Navy, 20 years) — Virginia Beach, Virginia. SWaM application in process (Virginia DSBSD #845183).
- **AI governance + workflow automation** for state and local government and nonprofits operating under federal / state regulatory exposure across the mid-Atlantic and Southeast.
- **NIST AI RMF 1.0 as the universal frame** — GOVERN / MAP / MEASURE / MANAGE alignment in every deliverable, every assessment, and every AIMS artifact.
- **State-policy overlays** — VA EO 30 + EO 26 + VITA EA-225, MD SB 818 + EO 01.01.2024.02, NC EO 24 + NCDIT framework, TN STS 200-POL-007 + Action Plan, WV HB 5690 / HB 3187, SC strategy.
- **Vertical compliance bridges where applicable** — HUD HMIS, Title IV-E, USDA TEFAP, DOJ OJJDP, VAWA, FERPA, COPPA, VCDPA. We map AIMS controls into the regulatory regimes our nonprofit and state-agency clients already live under.
- **No PRC-origin AI components** in any deliverable. Foreign-AI provenance attestation included by default.
- **Human-in-the-loop on every output.** No autonomous-decision claims for benefits, eligibility, rights-affecting, or safety-relevant AI uses.

---

## Disclaimers

- This document is a **consultative readiness reference**, not a formal state compliance opinion.
- **12th House AI, LLC is Veteran-Owned but not SDVOSB / VOSB certified.** Virginia SWaM application (#845183) is in process — not certified.
- 12th House AI is **not pursuing ISO 42001 certification**. The "ISO 42001-aligned" / "framework implementation" language used here means we use ISO 42001 as the AIMS scaffolding — not that we hold or pursue certification.
- 12th House AI makes no CMMC, FedRAMP, 8(a), HUBZone certified claims.
- State AI regimes are evolving rapidly through 2026. Citations reflect published policy as of the dates noted in the source-material section below. New EOs, statutes, and agency rules are expected.
- No claim is made that 12th House AI makes autonomous decisions on behalf of clients. All AI-assisted outputs require human review and approval before client or agency delivery.

---

## Primary-Source Links

**Virginia**
- EO 30: https://www.governor.virginia.gov/media/governorvirginiagov/governor-of-virginia/pdf/eo/EO-30.pdf
- VITA Artificial Intelligence: https://www.vita.virginia.gov/policy--governance/governance/artificial-intelligence/
- Woods Rogers EO 30 overview: https://www.woodsrogers.com/insights/publications/overview-of-virginias-ai-executive-order
- National Law Review on HB 2094 veto: https://natlawreview.com/article/virginia-governor-vetoes-artificial-intelligence-bill-hb-2094-what-veto-means

**Maryland**
- EO 01.01.2024.02: https://governor.maryland.gov/Lists/ExecutiveOrders/Attachments/31/EO%2001.01.2024.02%20Catalyzing%20the%20Responsible%20and%20Productive%20Use%20of%20Artificial%20Intelligence%20in%20Maryland%20State%20Government_Accessible.pdf
- Maryland Responsible AI Policy (DoIT): https://doit.maryland.gov/policies/ai/Pages/maryland-responsible-ai-policy.aspx
- SB 818 (2024 session): https://mgaleg.maryland.gov/mgawebsite/Legislation/Details/SB0818?ys=2024rs
- Maryland AI legislation portal: https://ai.maryland.gov/ai-maryland/legislation

**North Carolina**
- EO 24: https://governor.nc.gov/executive-order-no-24-advancing-trustworthy-artificial-intelligence-benefits-all-north-carolinians
- Press release on EO 24: https://governor.nc.gov/news/press-releases/2025/09/02/governor-stein-announces-executive-order-ai
- NCDIT 2025 year-in-review: https://it.nc.gov/news/press-releases/2026/01/12/2025-landmark-year-ncdit-ai-innovation-connectivity-and-security-advancements
- StateScoop coverage: https://statescoop.com/north-carolina-joins-growing-number-of-states-establishing-ai-frameworks/

**Tennessee**
- STS 200-POL-007 Enterprise AI Policy: https://www.tn.gov/content/dam/tn/finance/artificial-intelligence/200-POL-007%20Enterprise%20Artificial%20Intelligence%20Policy.pdf
- TN AI Advisory Council Action Plan (Nov 2025): https://www.tn.gov/content/dam/tn/finance/aicouncil/documents/TN%20AI%20Advisory%20Council%20Action%20Plan%20-%20November%202025.pdf
- TN Enterprise Generative AI Policy: https://www.tn.gov/content/dam/tn/finance/aicouncil/documents/TN%20Enterprise%20Generative%20AI%20Policy.pdf
- DeepSeek + Manus ban announcement: https://www.tn.gov/governor/news/2025/3/6/gov--lee-bans-manus--deepseek-ai-platforms-on-tennessee-state-network.html

**West Virginia**
- WV AI Task Force (Office of Technology): https://technology.wv.gov/policy-governance/artificial-intelligence/ai-task-force
- HB 3187 (2025 enrolled): https://www.wvlegislature.gov/Bill_Text_HTML/2025_SESSIONS/RS/bills/hb3187%20enr.pdf
- WV Code §5A-6-9: https://code.wvlegislature.gov/5A-6-9/

**South Carolina**
- Final SC AI Strategy (Dept. of Administration): https://admin.sc.gov/sites/admin/files/Documents/OED/Final%20SC%20AI%20Strategy.pdf
- SC AI Strategy landing page: https://admin.sc.gov/SCAIStrategy
- GovTech coverage: https://www.govtech.com/artificial-intelligence/south-carolinas-blueprint-reveals-how-it-will-leverage-ai
- Pivit Strategy 2026 SC AI laws overview: https://pivitstrategy.com/south-carolina-ai-laws-you-should-know-2026/

*Source material compiled 2026-05-16. Verify primary sources before relying on citations for formal procurement responses.*
