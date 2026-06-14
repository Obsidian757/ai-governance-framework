# Open-Source Model Governance

## Overview

Open-weight and community models (Llama, Mistral, Qwen, Gemma, DeepSeek, Phi, etc.) offer organizations full control over data residency, inference infrastructure, and model customization. They also shift responsibilities that commercial API providers absorb — safety evaluation, security patching, infrastructure operations, and legal risk — entirely to the deploying organization.

This document defines governance standards for evaluating, deploying, and maintaining open-source models. It complements the [third-party model risk assessment](../compliance/third-party-model-risk.md) (which covers commercial API providers) and [fine-tuning governance](fine-tuning-governance.md) (which covers additional considerations when fine-tuning any model).

---

## Evaluation Requirements Before Deployment

Before any open-source model enters production, complete these evaluations.

| Evaluation Area | Requirement | T1 | T2 | T3 | T4 |
|----------------|-------------|:---:|:---:|:---:|:---:|
| Safety benchmarks | Run standard safety evals (ToxiGen, BBQ, TruthfulQA or equivalent) | Required | Required | Required | Recommended |
| Domain-specific evaluation | Run your domain eval suite (same standard as commercial model evaluation) | 200+ cases | 100+ cases | 50+ cases | 20+ cases |
| Commercial comparison | Benchmark against leading commercial API for your use case | Required | Required | Recommended | Optional |
| Adversarial testing | Red-team testing per [red-teaming protocol](../ai-security/red-teaming-protocol.md) | Full red-team | Internal red-team | Automated scan | Automated scan |
| Infrastructure validation | Confirm hosting capability: GPU requirements, latency, throughput, scaling | Required | Required | Required | Required |
| Licensing review | Legal review of license terms and obligations | Required | Required | Required | Required |
| Total cost of ownership | Compare TCO against commercial API (include infrastructure, operations, security) | Required | Required | Recommended | Optional |

### Evaluation Decision Gate

Do not proceed to deployment if:
- Safety benchmark scores are materially below leading commercial models without documented risk acceptance
- Domain evaluation performance does not meet minimum thresholds defined for the use case
- Licensing terms are incompatible with intended use
- Infrastructure cannot meet latency and throughput requirements
- Total cost of ownership exceeds commercial API without compensating benefits (data residency, control, etc.)

---

## Licensing Risk

### License Compatibility Matrix

| License | Commercial Use | Derivative Works | Key Restrictions | Risk Level | Legal Review Required |
|---------|:---:|:---:|-------------|:---:|:---:|
| Apache 2.0 | Yes | Yes | Attribution; patent grant | Low | Routine |
| MIT | Yes | Yes | Attribution | Low | Routine |
| BSD 2/3-Clause | Yes | Yes | Attribution; no endorsement | Low | Routine |
| **Meta Llama 3.x Community License** | Yes | Yes | Acceptable use policy; if outputs used to train a competing LLM, restrictions apply; no MAU cap | Low–Medium | Yes |
| **Meta Llama 2 Community License** | Yes (MAU-gated) | Yes | >700M MAU triggers additional commercial terms from Meta; acceptable use policy | Medium | Yes |
| Gemma Terms of Use | Yes | Yes | Acceptable use restrictions; no building competing models | Medium | Yes |
| Qwen (Apache 2.0) | Yes | Yes | Apache 2.0 terms — but **PRC national origin risk applies independently of license**; see National Origin Risk note below | Low (license) / **High (origin)** | Yes |
| DeepSeek License | Conditional | Yes | Varies by model; some commercial restrictions — **PRC national origin risk; prohibited for federal/Virginia state use** | Medium (license) / **Prohibited (origin)** | Required |
| CC BY-NC | No | Yes | Non-commercial only | High | Required |
| Research-only licenses | No | Limited | Research/academic only | High | Required |

**National Origin Risk Note:** An open-source or Apache 2.0 license does not remove national origin risk. DeepSeek and Qwen are PRC-origin models — prohibited for use on Virginia state agency infrastructure (EO 26) and flagged under federal supply chain risk guidance regardless of their license terms. Always assess license risk AND origin risk independently. See [supply-chain-security.md](../ai-security/supply-chain-security.md) for the full geopolitical risk framework.

For T1/T2 systems: only deploy models with Low or Medium **combined** license and origin risk. High risk on either dimension requires CRO sign-off and documented risk acceptance. PRC-origin models with active federal/state prohibitions require legal sign-off before any use.

### Ongoing License Obligations

- Attribution: maintain attribution as required by license in model card and documentation
- Use restrictions: implement technical controls to enforce acceptable use policy restrictions
- Derivative work obligations: if fine-tuning and distributing weights, comply with derivative work terms
- Monitor for license changes: community models occasionally change license terms in new releases

---

## Training Data Risk

| Risk | Description | Assessment Approach |
|------|-------------|-------------------|
| Copyright exposure | Model trained on copyrighted content; deployer may face liability | Review provider's training data disclosure; assess pending litigation; monitor regulatory guidance |
| Opt-out non-compliance | Training data may include content from individuals/organizations that opted out | Review provider's opt-out compliance policy; assess GDPR right-to-erasure implications |
| Data provenance gaps | Training data composition is unknown or insufficiently disclosed | Assess model card transparency; factor uncertainty into risk assessment |
| PII in training data | Model may have memorized PII from training data | Run PII extraction tests; deploy output PII filters |
| Bias in training data | Training data composition may introduce demographic, cultural, or linguistic bias | Run bias evaluations; conduct counterfactual testing per [bias-detection-llm.md](../responsible-ai/bias-detection-llm.md) |

### Copyright Litigation Monitor

Maintain awareness of AI training data copyright cases and settled precedent:
- **Settled/resolved cases:** Some early cases (e.g., Getty Images v. Stability AI) moved toward settlement or judgment in 2024–2025 — review outcomes with legal to understand what liability exposure is now better-defined vs. what remains uncertain
- Track active cases by model family (Llama, Stable Diffusion derivatives, etc.)
- Assess potential impact on your deployments if rulings restrict use or require royalties
- Document risk acceptance for models with active litigation exposure
- Review with legal quarterly — the landscape evolves faster than annual review cycles can track

---

## Ongoing Maintenance

When you self-host a model, you own its operational lifecycle.

| Activity | Frequency | Owner | Notes |
|----------|-----------|-------|-------|
| CVE monitoring (model, inference framework, dependencies) | Weekly (automated) | Security | Subscribe to advisories for vLLM, TGI, PyTorch, CUDA |
| Community health check | Quarterly | AI Operations | Contributors, commit frequency, issue resolution, fork activity |
| Security patch application | Within SLA per severity | AI Operations | Critical: 48 hours; High: 1 week; Medium: 1 month |
| Safety re-evaluation | Semi-annually | AI Risk | Re-run safety benchmarks; compare against previous results |
| Performance re-evaluation | Quarterly | AI Operations | Re-run domain eval suite; detect degradation |
| License review | Quarterly | Legal | Check for license changes in new releases |
| Infrastructure capacity review | Quarterly | AI Operations | GPU utilization, scaling headroom, cost efficiency |

### Model Update Decision Framework

When a new version of an open-source model is released:

| Question | Decision |
|----------|----------|
| Does the new version fix security vulnerabilities? | Prioritize upgrade per security patch SLA |
| Does the new version improve capabilities relevant to our use case? | Evaluate; upgrade if material improvement and testing passes |
| Does the license change? | Legal review before any action |
| Does the new version change safety behavior? | Re-run full safety evaluation; do not upgrade without passing |
| Is the upgrade backward-compatible for our prompts? | Test prompt compatibility; re-validate eval suite |

---

## Fine-Tuning Governance (Open-Source Specific)

When fine-tuning open-source models, follow all standards in [fine-tuning governance](fine-tuning-governance.md) plus:

| Additional Requirement | Description |
|----------------------|-------------|
| Training data licensing | Training data must be compatible with the base model's license terms |
| Weight distribution | If distributing fine-tuned weights, comply with base model's derivative work obligations |
| Safety alignment preservation | Verify fine-tuning has not degraded base model safety alignment (re-run safety evals) |
| Provenance documentation | Document base model version, fine-tuning data, training configuration in AI-BOM |

---

## Decision Framework: Open-Source vs. Commercial API

| Factor | Choose Open-Source When | Choose Commercial API When |
|--------|------------------------|---------------------------|
| Data residency | Strict residency requirements; MNPI; data cannot leave your infrastructure | Vendor offers acceptable regional endpoints with contractual guarantees |
| Cost at scale | >$10K/month API spend; infrastructure team available | Low-to-moderate volume; infrastructure team unavailable |
| Control | Need to inspect model behavior, modify safety filters, customize inference | Standard API behavior is sufficient |
| Capability | Open-source model meets performance requirements | Frontier model capability is required (state-of-the-art reasoning, etc.) |
| Support requirements | Have internal ML engineering team; can manage operations | Need vendor SLA, support, and managed operations |
| Time to deployment | Have inference infrastructure ready; team experienced with deployment | Need to move fast; infrastructure not available |
| Compliance | Need full audit access; self-attested controls acceptable | Vendor certifications (SOC 2, ISO 27001) sufficient for your regulators |

Document the decision rationale in the risk assessment. For T1 systems, this decision requires AI Risk Committee review.
