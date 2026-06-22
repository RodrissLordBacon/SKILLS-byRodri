# Checklist A3 — Dependencies
# Reference: OpenSSF Scorecard checks + automated Dependabot/CI
#
# HOW TO USE THIS FILE
# --------------------
# A3 has two components:
#
# AUTOMATED (continuous) — runs in CI without human intervention:
#   - Dependabot: weekly PRs for outdated dependencies
#   - CI workflows: block merges on high/critical CVEs
#   These do not require this checklist — they run automatically.
#
# HUMAN (this checklist) — runs at roadmap phase close:
#   - OpenSSF Scorecard applied to direct dependencies only
#   - Catches risks CVE severity does not capture
#   - Do NOT run on the full dependency tree — direct deps only
#
# ITEM FORMAT
# -----------
# STATUS: ✅ PASS | ❌ FAIL | ⚠️ PARTIAL | ➖ N/A (with reason)
#
# HOW TO RUN OPENSFF SCORECARD ON A DEPENDENCY
# ---------------------------------------------
# scorecard --repo=github.com/OWNER/REPO
# Or check pre-computed scores at: https://securityscorecards.dev
#
# Last updated: [DATE]
# Audited by: [NAME/CHAT]
# Scope: Direct dependencies only. List them in Section 0.

---

## Section 0 — Direct dependency inventory (fill before auditing)

*List every direct dependency that will be evaluated. Do not include
transitive dependencies. Use the manifest file as source of truth.*

**Backend dependencies** (from requirements.in / pyproject.toml / package.json / pubspec.yaml / *.csproj):
```
[list dependencies here]
```

**Frontend dependencies** (from package.json / pubspec.yaml):
```
[list dependencies here]
```

**Total direct dependencies to evaluate:** [N]

---

## Section 1 — Automated component status

*Verify the automated layer is active before running the human audit.
If these are not active, fix them before continuing.*

### A3-1.1 — Dependabot is configured and raising PRs
**Status:** [ ]
**Evidence:** `.github/dependabot.yml` exists and is correctly configured
**Notes:**

### A3-1.2 — CI workflow blocks merges on high/critical CVEs
**Status:** [ ]
**Evidence:** `.github/workflows/audit-dependencies.yml` (or equivalent) exists and is active
**Notes:**

### A3-1.3 — Secret scanning CI workflow active
**Status:** [ ]
**Evidence:** `.github/workflows/audit-secrets.yml` (or equivalent) exists and is active
**Notes:**

---

## Section 2 — OpenSSF Scorecard per direct dependency

*For each direct dependency in Section 0, run Scorecard and record results.
Focus on checks that CVE scanners miss: maintenance health, supply chain risks.*

### Key Scorecard checks to evaluate per dependency

| Check | What it catches | Threshold |
|---|---|---|
| **Maintained** | Project activity in last 90 days | Score ≥ 5/10 |
| **Code-Review** | PRs reviewed before merge | Score ≥ 5/10 |
| **Branch-Protection** | Main branch protected | Score ≥ 3/10 |
| **Signed-Releases** | Release artifacts signed | Any score |
| **Security-Policy** | SECURITY.md present | Any score |
| **Vulnerabilities** | Known unfixed CVEs | Score = 10/10 |
| **Dangerous-Workflow** | Untrusted code execution in CI | Score = 10/10 |
| **Pinned-Dependencies** | Dependencies pinned in CI | Score ≥ 5/10 |

---

### Dependency evaluations

*Copy this block for each direct dependency:*

```
#### [package-name] vX.Y.Z
**Repo:** github.com/OWNER/REPO
**Scorecard URL:** https://securityscorecards.dev/#github.com/OWNER/REPO
**Overall score:** [N/10]

| Check | Score | Notes |
|---|---|---|
| Maintained | /10 | |
| Code-Review | /10 | |
| Branch-Protection | /10 | |
| Signed-Releases | /10 | |
| Security-Policy | /10 | |
| Vulnerabilities | /10 | |
| Dangerous-Workflow | /10 | |

**Finding:** ✅ Acceptable | ⚠️ Monitor | ❌ Risk — [describe]
```

---

## Section 3 — Manual risk flags

*These are risk patterns that Scorecard checks do not fully cover.*

### A3-3.1 — No direct dependency has a single maintainer with no succession plan for critical packages
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

### A3-3.2 — No direct dependency is unmaintained (last release > 18 months ago) without documented justification
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

### A3-3.3 — No direct dependency has been recently transferred to an unknown owner
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

### A3-3.4 — License of each direct dependency is compatible with the project's distribution model
**Status:** [ ]
**Evidence:** _fill during audit_
**Notes:**

---

## Audit summary

**Date:** [DATE]
**Auditor:** [NAME/CHAT]
**Scope:** Direct dependencies only (listed in Section 0)
**Reference:** OpenSSF Scorecard + manual risk flags

**Automated layer status:** ✅ Active | ❌ Not active (fix before next audit)

| Result | Count |
|---|---|
| ✅ PASS | |
| ❌ FAIL | |
| ⚠️ PARTIAL/MONITOR | |
| ➖ N/A | |

**Blocking findings:** [list or "none"]
**Non-blocking findings:** [list or "none"]
**Observations:** [list or "none"]
