# Client Management Scaffolding (ISO 42001-aligned engagements)

> ## ⚡ Scaffolding in place. Ready to deploy.
>
> Folder structure, status-tracking templates, weekly-status template, gap-analysis template, audit-readiness checklist, and master-tracking dashboard are **published and ready**. Onboard a client today by copying the `CLIENT-TEMPLATE` folder and filling in the brackets — the entire engagement runs out of this scaffolding from day one.

**Purpose:** Manage multiple client engagements through ISO 42001-aligned AIMS implementation cycles efficiently. (12th House AI does not provide ISO 42001 certification services; this scaffolding tracks framework-implementation engagements, not certification cycles.)

---

## Directory Structure

```
client-management/
├── README.md                    # This file
├── MASTER_TRACKING.md           # Dashboard for all clients
├── templates/                   # Reusable client templates
│   ├── client-folder-structure.md
│   ├── weekly-status-template.md
│   ├── gap-analysis-template.md
│   └── audit-readiness-checklist.md
├── clients/                     # Individual client folders
│   ├── CLIENT-TEMPLATE/         # Copy this for new clients
│   └── [client-name]/           # Actual client folders
└── reports/                     # Generated reports
    ├── weekly-summary.md
    └── monthly-revenue.md
```

---

## Quick Start

### 1. Adding a New Client

```bash
# Copy the template folder
cp -r clients/CLIENT-TEMPLATE clients/acme-corp

# Update the client info file
# Edit: clients/acme-corp/00-CLIENT-INFO.md
```

### 2. Updating Client Status

Edit `MASTER_TRACKING.md` after each client interaction:
- Update Progress %
- Change Status (🟢🟡🔴⚪)
- Update Next Action

### 3. Weekly Review Process

Run through this checklist every Monday:

1. **Review MASTER_TRACKING.md** - Check all client statuses
2. **Update each client's status.md** - Document weekly progress
3. **Identify blockers** - Flag 🔴 and 🟡 items for action
4. **Generate weekly report** - Summarize for your records

---

## Client Lifecycle Stages

| Stage | Duration | Key Deliverables |
|---|---|---|
| **Discovery** | 2-3 weeks | Assessment, Gap Analysis, Roadmap |
| **Implementation** | 8-12 weeks | Policies, Risk Register, Training |
| **Internal Audit Readiness** | 2-4 weeks | Evidence, Internal Audit |
| **Independent Certification (optional, client-elected)** | Variable | Client engages a certification body directly. 12th House AI does not provide certification services. |
| **Maintenance** | Ongoing | Continuous Improvement, change-log discipline |

---

## File Naming Conventions

| Document | Naming Pattern | Example |
|----------|----------------|---------|
| Client Info | `00-CLIENT-INFO.md` | `00-CLIENT-INFO.md` |
| Contract/SOW | `01-CONTRACT.md` | `01-CONTRACT.md` |
| Gap Analysis | `02-GAP-ANALYSIS.md` | `02-GAP-ANALYSIS.md` |
| Policies | `03-POLICY-*.md` | `03-POLICY-AIMS.md` |
| Procedures | `04-PROC-*.md` | `04-PROC-RISK.md` |
| Evidence | `05-EVID-*.md` | `05-EVID-TRAINING.md` |
| Status | `99-STATUS.md` | `99-STATUS.md` |

---

## Agent CLI Workflows (works with any code-assistant CLI)

### Check All Client Statuses

```bash
# Read master tracking
cat client-management/MASTER_TRACKING.md
```

### Create New Client

```bash
# Copy template
cp -r client-management/clients/CLIENT-TEMPLATE client-management/clients/[new-client-name]

# Update client info (edit the file)
# client-management/clients/[new-client-name]/00-CLIENT-INFO.md
```

### Find All Clients at Risk

```bash
grep -r "🔴" client-management/MASTER_TRACKING.md
```

### List All Evidence Gaps

```bash
grep -r "Missing\|Pending\|Incomplete" client-management/clients/*/99-STATUS.md
```

### Generate Weekly Report

```bash
# Get all status updates
cat client-management/clients/*/99-STATUS.md
```

---

## Client Folder Template

Each client folder contains:

```
clients/[client-name]/
├── 00-CLIENT-INFO.md          # Contact, contract, scope
├── 01-CONTRACT.md             # SOW, pricing, terms
├── 02-GAP-ANALYSIS.md         # Their specific gaps
├── assessment/                # Discovery docs
├── policies/                  # Customized policies
├── procedures/                # Customized procedures
├── evidence/                  # Audit evidence
├── meeting-notes/             # All meeting notes
└── 99-STATUS.md               # Current status
```

---

## Tips for Managing Multiple Clients

1. **Update MASTER_TRACKING.md weekly** - Even if no changes, confirm status
2. **Use status emojis consistently** - 🟢🟡🔴⚪
3. **Set calendar reminders** - For each client's milestone dates
4. **Document everything** - Meeting notes in client's folder
5. **Batch similar work** - Do all risk registers in one session

---

## Integration with Main Package

This client management system works alongside your main ISO 42001-aligned AIMS package:

- **Main package** (`/docs/`, `/templates/`) = Your methodology & tools
- **Client management** (`/client-management/`) = Client-specific work

When implementing for a client, copy templates from the main package and customize in their client folder.

---

*Last Updated: May 21, 2026*
