# Checklist A2 — Code and Architecture
# Reference: project's own curated principles (context files + CLAUDE.md)
#
# HOW TO USE THIS FILE
# --------------------
# This checklist is BUILT FROM YOUR PROJECT'S OWN DECISIONS, not from an
# external standard. Before running an A2 audit, populate Section 0 with
# the architectural decisions declared in the project's context files.
# The audit then verifies reality matches those declarations.
#
# 1. Fill Section 0 with the project's declared decisions.
# 2. For each item in Sections 1-5, set STATUS:
#    ✅ PASS | ❌ FAIL | ⚠️ PARTIAL | ➖ N/A (with reason)
# 3. Fill EVIDENCE with the file read or command run that supports it.
# 4. Derive findings per audit-system §5.
#
# Last updated: [DATE]
# Audited by: [NAME/CHAT]
# Scope: [DESCRIBE WHAT WAS INCLUDED AND EXCLUDED]

---

## Section 0 — Project declarations (fill before auditing)

*Copy the relevant decisions from the project's context files here.
This section defines what the audit is checking against.*

**Stack:**
```
Frontend: [e.g. React + TypeScript]
Backend: [e.g. Python + FastAPI]
Database: [e.g. SQLite → PostgreSQL]
Auth: [e.g. OAuth 2.0 + Google]
```

**Architectural decisions to verify:**
```
[List the non-negotiable decisions from product.md / CLAUDE.md]
1.
2.
3.
```

**UI component model:**
```
[e.g. Atomic Design — atoms/molecules/organisms/templates/pages]
```

**Backend layer structure:**
```
[e.g. routes → services → models, no business logic in routes]
```

**Naming conventions:**
```
[Copy from glossary.md or CLAUDE.md]
```

---

## Section 1 — Layer separation and architecture

### A2-1.1 — Business logic does not live in route/controller layer
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

### A2-1.2 — Data access does not bypass the model/ORM layer
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

### A2-1.3 — Frontend does not contain backend logic or direct DB access
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

### A2-1.4 — Credentials and tokens exist only in the declared secure layer
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

### A2-1.5 — Declared architectural decisions (Section 0) reflected in code
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

---

## Section 2 — UI component architecture

*Skip if project has no UI. Fill from the declared model in Section 0.*

### A2-2.1 — Component folder structure matches declared model
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

### A2-2.2 — Import direction rule respected (no upward imports)
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

### A2-2.3 — Atoms contain no business logic, API calls, or global state access
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

### A2-2.4 — Data fetching at declared level only (organisms or pages)
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

### A2-2.5 — No components in undeclared locations (dumping grounds)
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

---

## Section 3 — Code conventions

### A2-3.1 — File and folder naming follows declared conventions
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

### A2-3.2 — No hardcoded values that should be constants or tokens
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

### A2-3.3 — No commented-out code blocks left in production paths
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

### A2-3.4 — No TODOs/FIXMEs without associated task in Asana
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

---

## Section 4 — Technical debt and duplication

### A2-4.1 — No significant logic duplication across modules
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

### A2-4.2 — No unused imports, dependencies, or dead code paths
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

### A2-4.3 — No known broken patterns documented in previous audits still present
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

### A2-4.4 — Database migrations are versioned and have both upgrade and downgrade
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

---

## Section 5 — Engineering standards compliance

*These items check against the `engineering-standards` skill, which is the
project's code quality baseline.*

### A2-5.1 — No patches or temporary fixes without documented activation condition
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

### A2-5.2 — No custom solutions where an established standard exists (undocumented)
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

### A2-5.3 — New code since last audit follows declared conventions
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

---

## Audit summary

**Date:** [DATE]
**Auditor:** [NAME/CHAT]
**Scope:** [WHAT WAS INCLUDED/EXCLUDED]
**Reference:** Project context files + CLAUDE.md + engineering-standards skill

| Result | Count |
|---|---|
| ✅ PASS | |
| ❌ FAIL | |
| ⚠️ PARTIAL | |
| ➖ N/A | |
| **Total active items** | |

**Blocking findings:** [list or "none"]
**Non-blocking findings:** [list or "none"]
**Observations:** [list or "none"]
