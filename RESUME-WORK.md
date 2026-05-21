# How to Resume Work on This Repository

Quick guide for continuing development on the ISO 42001-aligned AIMS package.

---

## Quick Resume

```bash
# 1. Check the working tree
cd ~/Desktop/iso-42001-certification
git status
git log --oneline -3

# 2. Re-read the framing
cat docs/GOVERNANCE-FRAMEWORKS.md | less
```

---

## What's In This Repo

| Directory | Purpose | Status |
|---|---|---|
| `docs/` | Core AIMS documentation + framework crosswalks | Maintained |
| `templates/` | Reusable templates | Maintained |
| `marketing/` | Capability statement | Maintained |
| `client-management/` | Multi-client engagement scaffolding (templates only — no live clients) | Maintained |
| `evidence/` | Audit-trail artifacts | Maintained |

---

## Common Tasks

### Add a new client folder

```bash
cp -r client-management/clients/CLIENT-TEMPLATE \
      client-management/clients/[client-name]
```

### Commit and push

```bash
git add -A
git commit -m "Description"
git push
```

### Check client status

Open `client-management/MASTER_TRACKING.md`.

---

## Framing reminders (do not regress)

- ISO 42001 is the **implementation framework**. Not a certification claim. Not pursued.
- Veteran-owned. **Not** SDVOSB / VOSB / 8(a) / HUBZone / CMMC / FedRAMP.
- SWaM #845183 **in process**, not active.
- No name-dropping specific LLM vendors in federally-facing documents. Vendor identities live in the engagement-specific Vendor Management record.
- Human-in-the-loop on every consequential AI-driven recommendation.
- AI provenance disclosure stays in.

---

*Drafted with LLM assistance under human editorial control.*
