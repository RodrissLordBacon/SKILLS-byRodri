# code-reports skill

Deterministic internal report system for Claude Code → Claude.ai
communication. Fixed taxonomy, deterministic naming, mandatory field
structure, and explicit archiving rules.

---

## The problem this solves

Without this skill, every report Code produces has a different name, a
different structure, and a different archiving fate decided on the spot.
The result is a `docs/code-output/` folder with files like:
- `audit-results.md`
- `BackendReview_June.md`
- `things-i-found.md`
- `diagnostico-auth-2026.md`

None of these are locatable, comparable, or consistently structured.

This skill makes every report predictable: same naming pattern, same
field structure per type, same archiving rules.

---

## Four report types

| Type | When to use |
|---|---|
| `audit` | Systematic review against a checklist or standard |
| `diagnostic` | Root cause investigation of a specific problem |
| `extract` | Factual data extraction, no judgement |
| `snapshot` | Before-state capture ahead of a significant change |

---

## File naming

`<type>-<topic>-<YYYY-MM-DD>.md`

```
audit-security-2026-05-12.md
diagnostic-session-expiry-2026-06-03.md
extract-api-endpoints-2026-04-28.md
snapshot-auth-module-2026-05-01.md
```

---

## Lifecycle

```
Code produces report
       ↓
docs/code-output/          ← temporary, gitignored
       ↓
Department chat reads it
       ↓
Decision: archive | discard | keep in outbox
       ↓
docs/code-reports/         ← permanent, committed (if archived)
```

---

## Relation to other skills

- `working-system` — defines the handoff protocol used to request reports.
- `audit-system` — A1/A2/A3/A4 audits produce `audit` type reports
  following this skill's structure.
- `code-commands` — `/context-sync` produces an implicit `extract` of
  context file drift; it does not produce a formal report file unless
  running a full A4 audit.
