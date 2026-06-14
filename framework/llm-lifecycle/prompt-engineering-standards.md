# Prompt Engineering Standards

## Overview

Prompts are not code comments or ad hoc strings. In an enterprise LLM deployment, prompts are executable artifacts that directly determine system behavior, output quality, and risk exposure. They must be governed with the same rigor as application code.

This document defines organizational standards for prompt development, review, versioning, and lifecycle management.

---

## Core Principles

1. **Prompts are code.** Version-controlled, peer-reviewed, tested, deployed through CI/CD.
2. **Prompts are auditable.** Every prompt in production must be traceable to an approved version.
3. **Prompts are tested.** Every prompt must pass an evaluation suite before deployment.
4. **Prompts are documented.** Purpose, expected behavior, known limitations, and edge cases.
5. **Prompts are owned.** Every prompt has a designated owner accountable for its behavior.

---

## Prompt Development Standards

### Structure

All production prompts must follow a standard structure:

```
[SYSTEM CONTEXT]
Role definition, behavioral constraints, output format requirements.

[TASK INSTRUCTIONS]
Specific task description with clear success criteria.

[GUARDRAILS]
Explicit constraints: what the model must not do, topics to avoid,
escalation triggers.

[OUTPUT FORMAT]
Expected structure, schema, examples.

[FEW-SHOT EXAMPLES] (when applicable)
Representative input/output pairs demonstrating expected behavior.
```

### Naming Convention

```
{use-case}/{component}/{version}

Example: customer-service/complaint-classification/v2.3
Example: credit-analysis/memo-draft/v1.0
```

### Documentation Requirements

Each prompt must include:

| Field | Description |
|-------|-------------|
| `prompt_id` | Unique identifier |
| `version` | Semantic version (major.minor) |
| `owner` | Team and individual responsible |
| `purpose` | What this prompt does and why |
| `target_model` | Which model(s) this prompt is designed for |
| `input_schema` | Expected input variables and types |
| `output_schema` | Expected output format and constraints |
| `guardrails` | Safety constraints embedded in the prompt |
| `known_limitations` | Edge cases, failure modes, known weaknesses |
| `evaluation_results` | Link to most recent eval report |
| `approval_date` | Date of last review and approval |
| `next_review` | Scheduled review date |

---

## Prompt Review Process

### Review Checklist

Before a prompt enters production, it must pass the following review:

**Functional Review:**
- [ ] Prompt produces correct outputs for representative test cases
- [ ] Edge cases are tested and documented
- [ ] Output format is consistent and parseable (if structured)
- [ ] Prompt handles missing or malformed input gracefully

**Safety Review:**
- [ ] No prompt injection vulnerabilities (tested with standard injection payloads)
- [ ] No PII leakage — prompt does not instruct model to reveal training data or context
- [ ] Guardrails are explicit — not relying on model's default safety behavior
- [ ] Toxicity constraints are defined where applicable
- [ ] Hallucination mitigation is appropriate (e.g., "only answer based on provided context")

**Compliance Review:**
- [ ] Output cannot be mistaken for regulated advice (financial, legal, medical) unless appropriately qualified
- [ ] Disclosure requirements are met (if output is customer-facing)
- [ ] Prompt does not violate model provider's usage policy
- [ ] Data handling in prompt context complies with data classification policy

**Operational Review:**
- [ ] Token usage is within budget (system prompt + expected input + output)
- [ ] Latency is acceptable for the use case
- [ ] Prompt works with the fallback model (if T1/T2)

### Review Authority

| Tier | Reviewer |
|------|----------|
| T1 | Peer review + prompt engineering lead + security review + AI risk sign-off |
| T2 | Peer review + prompt engineering lead |
| T3 | Peer review |
| T4 | Self-review with documentation |

---

## Version Control

### Repository Structure

```
prompts/
├── {use-case}/
│   ├── {component}/
│   │   ├── prompt.yaml          # Current production prompt
│   │   ├── config.yaml          # Model, parameters, guardrail config
│   │   ├── eval/
│   │   │   ├── test_cases.yaml  # Evaluation test cases
│   │   │   └── results/         # Historical eval results
│   │   └── CHANGELOG.md         # Version history with rationale
```

### Versioning Rules

- **Major version (v1 → v2):** Behavioral change — different output characteristics, new guardrails, different model target. Requires full review.
- **Minor version (v1.0 → v1.1):** Refinement — improved phrasing, additional examples, minor guardrail adjustments. Requires peer review.
- **No unversioned changes.** Every prompt change creates a new version.

### Deployment

- Prompts deploy through the same CI/CD pipeline as application code
- Evaluation suite runs automatically on every prompt change (PR gate)
- Canary deployment for T1/T2: new prompt version serves a percentage of traffic, monitored before full rollout
- Rollback procedure: revert to previous version within defined SLA

---

## Prompt Evaluation

### Evaluation Dimensions

| Dimension | Metric | Method |
|-----------|--------|--------|
| Correctness | Accuracy against ground truth | Automated comparison with labeled test set |
| Faithfulness | Output grounded in provided context | LLM-as-judge or human evaluation |
| Consistency | Same input produces consistent outputs | Run N times, measure variance |
| Safety | Resistance to adversarial inputs | Adversarial test suite |
| Format compliance | Output matches expected schema | Automated schema validation |
| Latency | Response time | Automated measurement |
| Cost | Token usage | Automated measurement |

### Minimum Evaluation Suite Size

| Tier | Test Cases | Adversarial Tests |
|------|-----------|-------------------|
| T1 | ≥ 200 | ≥ 50 |
| T2 | ≥ 100 | ≥ 25 |
| T3 | ≥ 50 | ≥ 10 |
| T4 | ≥ 20 | ≥ 5 |

---

## Structured Outputs and Constrained Decoding

When a use case requires machine-readable output (JSON, YAML, function call arguments, classification labels), use structured output enforcement rather than relying on prompt instructions alone. Prompting a model to "respond in JSON" produces inconsistent results; constrained decoding guarantees it.

### Structured Output Modes

| Mode | How It Works | When to Use |
|------|-------------|-------------|
| **JSON mode** (OpenAI, Anthropic, Gemini) | Model constrained to always produce valid JSON | Any use case requiring JSON output; eliminates parse failures |
| **Structured outputs / response schema** (OpenAI `response_format`, Anthropic tool use) | Model constrained to match a specific JSON schema | Use case requires a specific schema; rejects responses that don't match |
| **Tool use / function calling** | Model outputs a structured tool call rather than natural language | Agentic systems; any case where the model must invoke a specific action |
| **Grammar-constrained decoding** (open-source: llama.cpp, vLLM) | Inference engine enforces a formal grammar on output tokens | Self-hosted models; complex constrained outputs (code, structured formats) |

### Governance Requirements for Structured Outputs

| Requirement | Description |
|-------------|-------------|
| Schema versioning | Output schemas are versioned alongside prompts — a schema change is a major version bump requiring full review |
| Schema validation in tests | Evaluation suite validates that outputs match the declared schema on every run |
| Fallback handling | Define behavior when constrained decoding fails or produces an empty response — do not silently pass invalid output downstream |
| Schema in model card | Document the output schema in the model card; downstream systems depend on it |
| Token budget awareness | Structured output modes consume additional tokens for schema enforcement overhead — account for this in cost projections |

---

## Prompt Caching Governance

Major providers (Anthropic, OpenAI) support prompt caching — reusing the KV cache for repeated prompt prefixes to reduce latency and cost. Caching introduces a governance consideration: **stale cached context**.

### How Caching Affects Governance

| Risk | Description | Control |
|------|-------------|---------|
| Stale system prompt | Cached system prompt does not reflect a recent update (policy change, guardrail addition) | Track prompt version in cache key; cache-bust on any system prompt update |
| Stale retrieved context | RAG context cached from a previous request may be outdated by the time a new request uses it | Do not cache retrieved context across requests; only cache static system prompt portions |
| PII in cached context | User-specific context containing PII may be inadvertently cached and reused | Isolate cacheable (static, non-PII) prompt segments from non-cacheable (user-specific, retrieved) segments; only cache the static prefix |
| Cache invalidation on policy change | When safety instructions or guardrails change, stale cache may serve old behavior until the TTL expires | Implement explicit cache invalidation on system prompt updates; do not rely solely on TTL |
| Audit trail | Cached responses may not log the full prompt if the cached prefix is not reconstructed | Ensure audit logging reconstructs the full effective prompt, not just the non-cached suffix |

### Caching Architecture Pattern

```
[Static system prompt — CACHEABLE]
Role, constraints, output format, guardrails (rarely change)

[Dynamic context — NOT CACHED]
Retrieved documents, user history, session context, current date
```

Only the static prefix is cached. Dynamic context is always passed fresh. The cache key includes the prompt version so updates automatically invalidate the cache.

### Operational Review Checklist Addition

Add to the Operational Review in the prompt review checklist:
- [ ] Cacheable vs. non-cacheable prompt segments identified and documented
- [ ] Cache invalidation mechanism defined for system prompt updates
- [ ] PII is not in the cacheable segment
- [ ] Audit logging reconstructs full effective prompt including cached prefix

---

## Anti-Patterns

The following practices are prohibited in production prompt engineering:

1. **Hardcoded secrets in prompts.** Never include API keys, credentials, or internal system details in prompt text.
2. **Implicit safety reliance.** Do not assume the model will behave safely without explicit constraints. Always include guardrails.
3. **Copy-paste prompts.** Do not copy prompts between use cases without independent evaluation. A prompt optimized for one task may behave unpredictably in another context.
4. **Prompt-as-documentation.** Prompts should be supplemented with separate documentation. The prompt text alone is not sufficient documentation.
5. **Unbounded output.** Always constrain output length, format, or scope. Open-ended generation in production creates unpredictable behavior and cost.
6. **Over-prompting.** Excessively long system prompts consume tokens, increase cost, and can degrade model attention. Keep prompts as concise as possible while maintaining safety and quality.
