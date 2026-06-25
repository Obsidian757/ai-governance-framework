# AI Supply Chain Security

## Overview

Every AI system depends on components the organization did not build: foundation models, inference frameworks, embedding models, vector databases, and evaluation tools. A vulnerability in any of these components compromises the systems built on top of them.

AI supply chain security extends traditional software supply chain practices to cover model provenance, training data risk, geopolitical origin risk, and the unique legal and safety considerations of AI components.

**Framework alignment:** OWASP LLM Top 10 2025 — LLM03 (Supply Chain). See [mcp-tool-security.md](mcp-tool-security.md) for MCP server and agentic tool supply chain controls.

---

## Model Provenance

Before deploying any model — commercial, open-source, or community-contributed — verify its provenance.

| Check | Description | Tier Requirement |
|-------|-------------|:---:|
| Weight verification | Verify model weights match published checksums (SHA-256) from the official source | T1/T2 |
| Source authentication | Download only from official channels (vendor API, official Hugging Face org, signed releases) | All |
| Training data attestation | Review provider's training data disclosure; assess data sourcing practices | T1/T2 |
| Model card review | Verify model card exists, is complete, and matches observed behavior | All |
| Safety evaluation verification | Reproduce key safety benchmarks; compare against provider's claimed scores | T1 |
| Licensing review | Legal review of model license terms, restrictions, and obligations | All |
| Known vulnerability check | Check for disclosed vulnerabilities or security advisories | All |
| **National origin / supply chain risk** | **Verify model provider is not subject to federal or state supply chain risk designations** | **All** |

### Model Card Credibility Assessment

Model cards are self-reported. Treat them as claims, not facts:
1. Are safety evaluation results reproducible with your own test data?
2. Do observed capabilities match documented capabilities?
3. Are limitations honestly disclosed, or is the card marketing material?
4. Is training data composition described with enough specificity to assess bias risk?
5. Is the card regularly updated, or was it published once and abandoned?

---

## Geopolitical and National Origin Risk

This is a supply chain risk category with no equivalent in traditional software — the nation of origin of a model provider may create legal, security, or procurement barriers independent of the model's technical properties.

### PRC-Origin Model Risk

Models developed by companies headquartered in or controlled by the People's Republic of China carry specific risks for US federal, state, and regulated-sector deployments.

| Provider | Origin | Federal Risk | Virginia (EO 46) | Notes |
|----------|--------|:------------:|:-----------------:|-------|
| DeepSeek (DeepSeek AI) | PRC | **Prohibited** for federal use per multiple DoD/agency directives | **Prohibited** per EO 46 | Multiple US states have also enacted independent bans |
| Qwen (Alibaba Cloud) | PRC | **High risk**; review against applicable procurement rules | **Prohibited** per EO 46 | Qwen 2.5 Apache 2.0 license does not remove national origin risk |
| Kimi / Moonshot AI | PRC | **High risk** | **Prohibited** per EO 46 | |
| Baidu ERNIE | PRC | **Prohibited** for federal use | **Prohibited** per EO 46 | |
| ByteDance / Doubao | PRC | **Prohibited** for federal use | **Prohibited** per EO 46 | TikTok parent company |

**Controls for PRC-origin model risk:**

- Verify country of incorporation, beneficial ownership, and board composition for all model providers — open licensing (Apache 2.0, MIT) does not remove national origin risk
- Add PRC-origin check to AI-BOM and pre-deployment checklist
- For Virginia state agency deployments: EO 46 (2025) prohibits use of PRC-origin technology on Commonwealth infrastructure; verify all models, embedding models, and inference infrastructure are non-PRC-origin
- For federal deployments: check against current DoD supply chain risk management (SCRM) designations; Anthropic is separately designated as supply chain risk by DoD (2026) — use Groq, AWS Bedrock (Llama 3 70B), or Azure OpenAI for federal-facing work
- Monitor for supply chain changes: a model or tool that is clean today may be acquired by or become dependent on a PRC-origin entity

### Other National Origin Considerations

While PRC-origin is the primary active risk category under current US law, apply the same provenance scrutiny to any model provider headquartered in a country subject to US export controls, sanctions, or tech transfer restrictions. Consult legal counsel when in doubt.

---

## Open-Source Model Risk

Open-source models offer control and cost advantages but shift responsibility for safety, security, and maintenance to the deployer.

| Risk Category | Description | Mitigation |
|--------------|-------------|------------|
| Licensing restrictions | Some "open" licenses restrict commercial use, derivatives, or specific use cases | Legal review before deployment; maintain license compliance register |
| Training data copyright | Model may be trained on copyrighted content; deployer may inherit liability | Review provider's copyright policy; assess litigation exposure; monitor case outcomes (NYT v. OpenAI, Getty v. Stability AI) |
| Safety evaluation gaps | Community safety claims may be overstated or untested for your domain | Run your own safety evaluations; do not rely solely on community benchmarks |
| Backdoor risk | Community-uploaded models may contain poisoned weights or hidden behaviors | Download from verified sources only; run behavioral testing before deployment |
| Maintenance risk | Project may become abandoned; no security patches or safety updates | Assess community health (contributors, commit frequency, issue responsiveness); have alternatives identified |
| Supply chain tampering | Model files modified between source and deployment | Verify checksums; use signed releases where available; store models in controlled artifact registry |
| National origin risk | Model developed by entity subject to US export controls or adversarial nation | See Geopolitical and National Origin Risk section above |

### Open-Source License Risk Matrix

**Llama note:** Meta has released multiple model generations with different license terms. Verify the specific license for the exact model version you are deploying — do not assume all Llama models share the same terms.

| License | Commercial Use | Derivative Works | Key Restrictions | Risk Level |
|---------|:---:|:---:|-------------|:---:|
| Apache 2.0 | Yes | Yes | Patent grant; attribution | Low |
| MIT | Yes | Yes | Attribution only | Low |
| **Meta Llama 3.x Community License** | Yes | Yes | Acceptable use policy; if you use Llama outputs to train a competing LLM, additional restrictions apply; no MAU cap | Low–Medium |
| **Meta Llama 2 Community License** | Yes (MAU-gated) | Yes | >700M MAU requires additional Meta license; acceptable use policy | Medium |
| Qwen (Apache 2.0) | Yes | Yes | Apache 2.0 terms only — but PRC national origin risk applies independently of license | Low (license) / High (origin) |
| Mistral (varies by model) | Varies | Varies | Some models Apache 2.0; others have commercial restrictions — check per model version | Medium–High |
| CC BY-NC | No | Yes | Non-commercial only | High |
| Custom community licenses | Varies | Varies | Case-by-case legal review required | Variable |

For T1/T2 systems, only use models with Low or Medium **combined** license and origin risk. High-risk on either dimension requires legal sign-off and documented risk acceptance.

---

## Community Model Governance

Models from Hugging Face, GitHub, or other community platforms require additional due diligence beyond what commercial API providers absorb.

### Pre-Deployment Verification Checklist

- [ ] Model downloaded from verified organization page (not a fork or re-upload)
- [ ] Weight checksums verified against official publication
- [ ] License terms reviewed and approved by legal
- [ ] National origin / supply chain risk assessed (see above)
- [ ] Safety evaluation suite executed (not just provider benchmarks)
- [ ] Domain-specific evaluation suite executed
- [ ] Behavioral testing for known failure modes completed
- [ ] Infrastructure sizing validated (GPU requirements, memory, latency)
- [ ] Ongoing vulnerability monitoring source identified
- [ ] Fallback model identified (if community model fails or is abandoned)
- [ ] Maintenance owner assigned internally

### Ongoing Monitoring

| Activity | Frequency | Owner |
|----------|-----------|-------|
| Community health check (contributor activity, issue resolution) | Quarterly | AI Operations |
| CVE and vulnerability scan (model, framework, dependencies) | Weekly (automated) | Security |
| License change monitoring | Quarterly | Legal |
| Safety benchmark re-evaluation | Semi-annually | AI Risk |
| Performance regression testing | Monthly | AI Operations |
| Supply chain origin re-verification (ownership / acquisition changes) | Quarterly | Legal / Procurement |

---

## Dependency Management

AI systems depend on inference frameworks, libraries, and infrastructure components beyond the model itself.

| Component | Risk | Mitigation |
|-----------|------|------------|
| Inference frameworks (vLLM, TGI, Triton) | CVEs, breaking changes, performance regressions | Pin versions; test upgrades; subscribe to security advisories |
| ML frameworks (PyTorch, TensorFlow, JAX) | CVEs, API changes | Pin major versions; security scan in CI/CD |
| Embedding models | Quality degradation, version changes, licensing, national origin | Pin versions; re-evaluate on updates; apply same origin checks as foundation models |
| Vector databases | Data corruption, access control bypass, performance | Standard database security practices; access auditing |
| Container images | Unpatched OS vulnerabilities, bloated attack surface | Minimal base images; weekly vulnerability scanning; rebuild on critical CVEs |
| Python packages | Dependency confusion, typosquatting, compromised packages | Use verified package sources; pin exact versions; audit new dependencies |
| MCP servers and plugins | Tool poisoning, rug-pull, indirect prompt injection | See [mcp-tool-security.md](mcp-tool-security.md) |

---

## AI Bill of Materials (AI-BOM)

Every AI system should maintain an AI Bill of Materials documenting its supply chain. This extends traditional SBOM concepts to AI-specific components.

### AI-BOM Contents

| Component | Details to Document |
|-----------|-------------------|
| Foundation model | Provider, model name, version/checkpoint, access method (API/self-hosted) |
| Model license | License type, commercial use permitted, derivative restrictions, obligations |
| **National origin** | **Provider country of incorporation; beneficial ownership; any supply chain risk designations** |
| Training data summary | Provider's disclosure; known data sources; opt-out compliance status |
| Safety evaluations | Provider's published evaluations + your own evaluation results |
| Known limitations | Provider-documented + internally discovered limitations |
| Embedding model | Provider, version, embedding dimensions, hosting, national origin |
| Inference framework | Name, version, deployment configuration |
| Key dependencies | Framework versions, critical libraries, container base image |
| Guardrail components | Safety classifiers, content filters, PII detectors — versions and sources |
| MCP servers / plugins | Name, version, source, national origin, last security review date |

### Maintenance

- AI-BOM updated on every model change, framework upgrade, dependency update, or MCP server change
- Reviewed as part of deployment gate process
- Stored alongside model card and risk assessment
- Retained per audit trail requirements

---

## Recommended Tooling

| Tool | Use Case |
|------|----------|
| **[agentseal](https://github.com/getagentseal/agentseal)** | Scan MCP configurations for dangerous skills and tool poisoning; audit live MCP servers; monitor for supply chain attacks on AI agents — run weekly for T1/T2 agentic systems |
| **[Argus](https://github.com/gy15901580825/Argus)** | Automated supply chain and adversarial probe scanning for AI agents; OWASP LLM Top 10 LLM03 coverage; ships as CLI + GitHub Action |

---

## Decision Framework: Open-Source vs. Commercial API

| Factor | Open-Source Advantage | Commercial API Advantage | Decision Guidance |
|--------|----------------------|-------------------------|-------------------|
| Cost at scale | Lower marginal cost after infrastructure investment | Lower upfront cost; pay-per-use | Open-source at >$10K/month API spend |
| Control | Full control over model, data, infrastructure | Limited to API parameters | Open-source when data residency is non-negotiable |
| Data residency | Complete; all processing on your infrastructure | Depends on vendor's regional endpoints | Open-source for MNPI or strict residency |
| Capability | Varies; may lag frontier models | Frontier performance; regular updates | API for state-of-the-art requirements |
| Support | Community only; no SLA | Vendor SLA; dedicated support | API for T1 systems requiring guaranteed uptime |
| Security patching | Self-managed; may lag | Vendor-managed; typically faster | API unless you have dedicated ML security team |
| Compliance | Full audit access; self-attested | Vendor certifications (SOC 2, ISO 27001) | Depends on regulatory expectations |
| **National origin risk** | **Must verify per model; PRC-origin models prohibited in many contexts regardless of license** | **Must verify per vendor; check DoD SCRM designations** | **Never assume open license = no origin risk** |

Use this framework during model selection; document the decision rationale in the risk assessment.
