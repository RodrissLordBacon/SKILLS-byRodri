# Checklist A4 — Documentary Consistency
# Reference: project's own context files vs. actual repository state
#
# HOW TO USE THIS FILE
# --------------------
# A4 verifies that what the project says about itself is true.
# Every item checks a specific claim in a context file against the repo.
#
# BEFORE RUNNING THIS AUDIT:
# 1. Fill Section 0 with the context files that exist in this project.
# 2. For each context file, list the verifiable claims it makes.
# 3. Run the audit by checking each claim against the repo.
#
# NOTE: /context-sync in Claude Code does a lightweight version of this
# automatically. A4 is the formal, evidenced, archived version.
#
# STATUS: ✅ MATCHES | ❌ DIVERGES | ⚠️ PARTIALLY MATCHES | ➖ SKIP (reason)
#
# Last updated: [DATE]
# Audited by: [NAME/CHAT]
# Scope: All context files in docs/project-context/ + CLAUDE.md

---

## Section 0 — Context file inventory (fill before auditing)

*List the context files that exist in this project and their primary purpose.*

| File | Purpose | Last updated |
|---|---|---|
| `state.md` | Implementation inventory | [DATE] |
| `product.md` | Product identity and stack | [DATE] |
| `design-system.md` | Visual tokens and design decisions | [DATE] |
| `frontend-architecture.md` | Component model and folder structure | [DATE] |
| `glossary.md` | Term definitions and naming conventions | [DATE] |
| `roadmap.md` | Planned features by phase | [DATE] |
| `CLAUDE.md` | Technical map for Claude Code | [DATE] |
| [add others] | | |

---

## Section 1 — state.md verification

*state.md is the most volatile file — it changes after every session with
code changes. Divergences here are expected and normal; the question is
whether they are documented.*

### A4-1.1 — All features listed as "implemented" exist in the codebase
**Status:** [ ]
**Evidence:** _list features checked and where verified_
**Notes:**

### A4-1.2 — All API endpoints listed in state.md exist in the backend
**Status:** [ ]
**Evidence:** _grep command or route file reviewed_
**Notes:**

### A4-1.3 — Database schema described in state.md matches actual migrations
**Status:** [ ]
**Evidence:** _migration files reviewed_
**Notes:**

### A4-1.4 — Features listed as "not implemented" are genuinely absent from the code
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

### A4-1.5 — No features exist in code that are undocumented in state.md
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

---

## Section 2 — CLAUDE.md verification

*CLAUDE.md is Claude Code's map of the repo. If it's wrong, Code works
with incorrect assumptions.*

### A4-2.1 — Folder structure described in CLAUDE.md matches actual structure
**Status:** [ ]
**Evidence:** `find . -type d` output compared to CLAUDE.md
**Notes:**

### A4-2.2 — Build and test commands listed in CLAUDE.md work correctly
**Status:** [ ]
**Evidence:** _commands executed and output recorded_
**Notes:**

### A4-2.3 — "Do not touch" zones listed in CLAUDE.md are still relevant
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

### A4-2.4 — Stack and dependency versions in CLAUDE.md match actual files
**Status:** [ ]
**Evidence:** _package.json / requirements.txt compared_
**Notes:**

---

## Section 3 — frontend-architecture.md verification

*Skip if project has no frontend or no frontend architecture doc.*

### A4-3.1 — Declared folder structure matches actual src/ structure
**Status:** [ ]
**Evidence:** `find src/ -type d` compared to doc
**Notes:**

### A4-3.2 — Components listed by level exist at the declared paths
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

### A4-3.3 — No components exist at wrong levels (e.g. organism in atoms/)
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

### A4-3.4 — Figma ↔ code naming mapping is still accurate
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

---

## Section 4 — design-system.md verification

*Skip if project has no design system doc.*

### A4-4.1 — CSS token values in design-system.md match actual token file
**Status:** [ ]
**Evidence:** _tokens.css or equivalent compared_
**Notes:**

### A4-4.2 — Colour palette described matches tokens in use
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

### A4-4.3 — Typography scale described matches actual font definitions
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

### A4-4.4 — "Current deviations" section in design-system.md is up to date
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

---

## Section 5 — product.md verification

*product.md is relatively stable but its stack section should be checked.*

### A4-5.1 — Stack described in product.md matches actual dependencies
**Status:** [ ]
**Evidence:** _package.json / requirements compared_
**Notes:**

### A4-5.2 — Architectural decisions listed are still being followed
**Status:** [ ]
**Evidence:** _cross-reference with A2 audit findings_
**Notes:**

### A4-5.3 — No decisions listed as "preserved" have been quietly reversed in code
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

---

## Section 6 — glossary.md verification

### A4-6.1 — Naming conventions in glossary match actual naming in codebase
**Status:** [ ]
**Evidence:** _grep for counter-examples_
**Notes:**

### A4-6.2 — No terms used in context files that are undefined in glossary
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

---

## Audit summary

**Date:** [DATE]
**Auditor:** [NAME/CHAT]
**Scope:** All context files listed in Section 0

| File | Status | Divergences found |
|---|---|---|
| state.md | | |
| CLAUDE.md | | |
| frontend-architecture.md | | |
| design-system.md | | |
| product.md | | |
| glossary.md | | |

| Result | Count |
|---|---|
| ✅ MATCHES | |
| ❌ DIVERGES | |
| ⚠️ PARTIAL | |
| ➖ SKIP | |

**Blocking findings:** [list or "none"]
**Non-blocking findings:** [list or "none"]
**Observations:** [list or "none"]

**Recommended action:** Run `/context-sync` in Claude Code to apply corrections
from this audit to the context files, then re-upload mirrors to Claude.ai Project.
