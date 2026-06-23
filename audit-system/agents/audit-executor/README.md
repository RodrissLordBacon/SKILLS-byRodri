# audit-executor

> The execution arm of the audit-system. Collects evidence. Does not classify, does not fix, does not improvise.

This agent pairs exclusively with the [audit-system skill](https://github.com/RodrissLordBacon/SKILLS-byRodri/tree/main/audit-system). The skill is the plan. This agent is the execution.

---

## How the system works

The audit-system skill runs in Claude.ai. It defines the methodology: four active audit families, a seven-step execution cycle, three finding types, and the rules for deriving findings into your project management system. The Audit chat confirms scope, builds the plan, and generates a Claude Code prompt.

This agent receives that prompt and executes it — reading the codebase, running scans, and producing a structured evidence file. It does not decide what matters. It finds and reports. The Audit chat in Claude.ai reads the output and makes the judgement calls.

That separation is the point. Automated evidence gathering is consistent and exhaustive. Severity assessment and classification require context that only a human (or a Claude.ai chat with full project context) can apply correctly.

---

## What it scans

**A1 — Security** (OWASP ASVS 5.0 Level 2)
- Hardcoded secrets and credentials in source files
- `.env` files committed to the repo
- JWT handling and session configuration
- Password storage patterns (plaintext risk)
- Routes without visible auth middleware
- Input validation coverage (Zod, Joi, class-validator)
- SQL query construction (parameterized vs. concatenation)
- CORS configuration
- Dependency vulnerability scan (`npm audit`, `pip-audit`)

**A2 — Code and Architecture**
- Actual directory structure vs. declared architecture in context files
- Layer boundary violations (DB calls in route handlers, DB calls in UI components)
- Forbidden dumping grounds (`utils`, `helpers`, `common`)
- Naming convention drift vs. what CLAUDE.md declares

**A3 — Dependencies**
- Full vulnerability scan with JSON output
- Direct dependency inventory (the human-review subset)
- Lock file presence verification
- Data for OpenSSF Scorecard manual review (last publish dates, maintainer signals)

**A4 — Documentary Consistency**
- Declared endpoints vs. actual route definitions
- Declared modules/services vs. actual folder structure
- CLAUDE.md build commands vs. actual scripts in `package.json`
- Context file claims vs. repo reality

---

## Output

Every audit produces a structured evidence file at:

```
docs/code-output/audit-<family>-YYYY-MM-DD.md
```

The file contains every command run (with full output), every checklist item (with status `FOUND` / `NOT FOUND` / `NOT APPLICABLE`), and every piece of evidence cited by exact file and line number.

No severity labels. No fix proposals. No unsupported assertions. The Audit chat in Claude.ai reads this file and classifies findings into the three types defined by the audit-system skill: **blocking**, **non-blocking**, or **observation**.

---

## Prerequisites

**The audit-system skill must be installed in Claude.ai.** This agent is not designed to be used standalone. Without the skill providing scope, checklists, and the execution prompt, the agent will ask for scope before proceeding — and you'll need the methodology to answer that question correctly.

**Checklists must exist in the repo.** This agent runs against checklists in `docs/project-context/audits/`. If they don't exist, the agent reports it and stops. Build the checklists first using the Audit chat in Claude.ai.

```
docs/project-context/audits/
├── checklist-a1-security.md
├── checklist-a2-architecture.md
├── checklist-a3-dependencies.md
└── checklist-a4-docs.md
```

---

## Installation

**Global** — available across all your projects:

```bash
mkdir -p ~/.claude/agents
cp audit-executor.md ~/.claude/agents/
```

**Per project** — scoped to a single repository:

```bash
mkdir -p .claude/agents
cp audit-executor.md .claude/agents/
```

Claude Code picks it up automatically.

---

## What this agent will not do

- **Classify findings.** It outputs `FOUND` or `NOT FOUND`. Never `CRITICAL` or `HIGH`. That's the Audit chat's job.
- **Propose fixes.** Evidence only. Correction prompts come from the Audit chat after classification.
- **Expand scope silently.** If scope was not confirmed before execution, it stops and asks.
- **Skip checklist items silently.** Every inactive or skipped item is logged with a reason.
- **Run dynamic analysis.** Static analysis of the repository only — no port scans, no active exploits against running services.
- **Modify source files.** Read-only on the codebase. The only files it writes are the evidence output in `docs/code-output/`.

---

## Part of a larger system

This agent is one piece. The full pre-audit readiness system:

| Piece | Where | Role |
|---|---|---|
| audit-system skill | Claude.ai | Methodology, planning, finding classification |
| audit-executor agent | Claude Code | Evidence gathering, scanning, raw output |
| Checklists | `docs/project-context/audits/` | Per-project operative checklists |
| Reports | `docs/code-reports/` | Archived audit history |

→ [audit-system skill](https://github.com/RodrissLordBacon/SKILLS-byRodri/tree/main/audit-system) — start here if you haven't built your checklists yet.

→ [Full collection](https://github.com/RodrissLordBacon/SKILLS-byRodri)
