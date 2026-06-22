# audit-system skill

Formal audit system for software projects. Defines active and dormant audit
families, triggers, a fixed execution cycle, finding classification, and a
three-phase automation layer. Based on OWASP ASVS 5.0 and OpenSSF Scorecard.

---

## What this skill does

When installed, the Audit department chat knows and applies:

- **Four core principles** that govern all audit decisions: automation
  covers what automation can cover; the user triggers, the chat executes;
  every finding ends somewhere actionable; dormant families have written
  activation criteria.
- **Family catalogue:** A1 Security (OWASP ASVS 5.0 L2), A2 Code and
  Architecture (project's own curated principles), A3 Dependencies (OpenSSF
  Scorecard + automated Dependabot/CI), A4 Documentary Consistency
  (context files vs. repo). Plus three dormant families (D1 Data/Privacy,
  D2 Accessibility, D3 Legal) with written activation triggers.
- **Four trigger types:** roadmap phase close (primary), critical event,
  user request, explicit cadence.
- **Seven-step execution cycle:** scope confirmation → plan → Code prompt
  → Code executes → human reading → classification and derivation →
  close with archiving. Fixed for all families.
- **Three finding types:** blocking (audit stays open until resolved),
  non-blocking (SQ or MQ in Asana), observation (in report only). With
  the edge rule: when in doubt between non-blocking and observation,
  default to observation.
- **A1 quarterly lightweight review:** core subset of highest-criticality
  A1 controls reviewed every quarter regardless of phase close.
- **Three-phase automation layer:** Phase 1 (basic CI scans, any repo),
  Phase 2 (declared vs. real comparison scripts, project-specific),
  Phase 3 (semantic verification, built only if phases 1 and 2 are
  insufficient).
- **`/ultrareview`:** reserved resource for deep parallel agent audit,
  justified only before first external distribution, SaaS transition, or
  critical auth refactor.
- **System boundaries:** what audits do not cover and why.

---

## What this skill does NOT include

- **Executable checklists.** Those live in `docs/project-context/audits/`
  in each project's repo, built per-project from the standards referenced
  in the skill. The skill defines the methodology; the checklists implement
  it for a specific stack.
- **Stack-specific filtering.** ASVS items that do not apply to a given
  stack are marked inactive in the project checklist with activation
  conditions documented. The skill references the full standard; the
  checklist does the filtering.
- **Project-specific inputs.** Which files to read, which manifest files
  to check, which architectural patterns to verify — all defined in the
  project's own checklist and context files.

---

## Standards referenced

| Family | Standard |
|---|---|
| A1 — Security | OWASP ASVS 5.0 Level 2 |
| A2 — Code and Architecture | Project's own curated principles (context files) |
| A3 — Dependencies | OpenSSF Scorecard (human) + Dependabot / pip-audit / npm audit (automated) |
| A4 — Documentary Consistency | Checklist derived from the project's own context files |
| D1 — Data and Privacy | GDPR, OWASP Data Privacy Guidelines |
| D2 — Accessibility | WCAG 2.2 Level AA, platform HIG |
| D3 — Legal Compliance | Jurisdiction-specific |

---

## Relation to other skills

- `working-system` — defines how the Audit department chat operates within
  the overall project methodology (commands, prompts for Code, Asana tasks).
- `engineering-standards` — defines the code quality bar that A2 verifies
  against (alongside the project's own architecture decisions).
- `code-commands` — `/context-sync` in Claude Code is the lightweight
  ongoing complement to A4; it syncs context files but does not produce a
  formal audit report.

---

## Installation

Save the skill from Claude.ai or package with:

```bash
python -m scripts.package_skill audit-system/ /output/path/
```

After installing, create the first checklist for A1 in your project:

```
docs/project-context/audits/
└── checklist-a1-security.md   ← build this first
```

Use the Audit department chat to build it: provide the project stack and
the chat will walk OWASP ASVS 5.0 Level 2, filter by applicability, and
produce the checklist ready for the first audit.
