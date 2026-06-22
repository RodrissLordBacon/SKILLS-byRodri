# Skills · by Rodri

> Professional-grade Claude skills built without shortcuts.
> Each one encodes a real standard, a real methodology, or a real workflow —
> not a list of buzzwords dressed up as instructions.

---

## What's in here

Five skills for developers working with Claude. They cover how code is
written, how it's reviewed, how projects are structured, and how the work
itself is organized. They're designed to work together, but each one
stands on its own.

---

## The skills

### `working-system`
**The methodology layer.** Defines how to work with Claude across a full
project lifecycle — the three actors (Claude.ai, Claude Code, you), the
task system, departments, session management, and the handoff protocol
that keeps Claude Code on task without improvising.

Built for: any software project. Scales from a solo side project to
a complex multi-month build.

→ [`working-system/`](./working-system/)

---

### `engineering-standards`
**The quality layer.** The non-negotiable bar for all code produced.
Clean Architecture and DDD-flavored, language-agnostic at its core,
with stack-specific references for Python, TypeScript/React, Dart/Flutter,
C#/.NET, and SQL.

The prime directive: solidness over speed. A patch that works today
but breaks tomorrow was never a solution.

Built for: any codebase, any stack. Drop it in and Claude Code
applies the same quality standard across every language.

→ [`engineering-standards/`](./engineering-standards/)

---

### `audit-system`
**The verification layer.** A formal audit system based on OWASP ASVS 5.0
and OpenSSF Scorecard. Four active families (security, architecture,
dependencies, documentary consistency), three dormant families with written
activation criteria, a fixed seven-step execution cycle, and a three-phase
automation layer.

Includes skeleton checklists for all four active families — ready to
adapt to your stack.

Built for: any project that handles real data or will eventually
ship to real users.

→ [`audit-system/`](./audit-system/)

---

### `github-workflow`
**The git layer.** GitHub Flow + Conventional Commits + GitHub CLI.
Two paths: direct to `main` for atomic changes, feature branch + PR
for anything with risk or scope. Deterministic branch naming, commit
messages that mean something, and a clean session close that doesn't
leave uncommitted work behind.

No snapshots. No `sesion/2026-04-23`. No WIP commits.

Built for: any project on GitHub with `gh` installed.

→ [`github-workflow/`](./github-workflow/)

---

### `code-reports`
**The communication layer.** A fixed taxonomy for internal reports between
Claude Code and Claude.ai: `audit`, `diagnostic`, `extract`, `snapshot`.
Deterministic file naming. Mandatory field structure per type. Explicit
archiving rules. No more ad-hoc filenames or variable report structures.

Built for: any project where Code needs to deliver structured findings
to a department chat.

→ [`code-reports/`](./code-reports/)

---

## How they fit together

```
working-system      ←  the methodology that governs everything
     │
     ├── engineering-standards   ←  what "done correctly" looks like
     ├── github-workflow         ←  how changes are saved and shipped
     ├── code-reports            ←  how Code communicates findings
     └── audit-system            ←  how the project verifies its own health
```

You can use any of them independently. They're most powerful together.

---

## Installation

### Claude.ai Projects (RAG)

Copy the folder of any skill into your Claude Project's files.
The `SKILL.md` is what Claude reads. The `references/` folder
contains supporting material that Claude pulls in as needed.

### Claude Code (personal skills)

```bash
# macOS / Linux
cp -r <skill-folder> ~/.claude/skills/

# Windows (PowerShell)
Copy-Item -Recurse <skill-folder> "$env:USERPROFILE\.claude\skills\"
```

After copying, start a new Claude Code session. The skill is available
as `/<skill-name>`.

---

## Design principles

Every skill here follows the same rules:

**Real standards, not invented ones.** When a standard exists
(OWASP ASVS, OpenSSF Scorecard, Conventional Commits, GitHub Flow,
Brad Frost's Atomic Design), the skill encodes that standard. No
home-grown alternatives without documented reason.

**Actionable, not aspirational.** "Write clean code" is not
a skill. A skill tells Claude exactly what to check, exactly what
format to use, exactly what to do when something is wrong.

**Completeness over brevity.** A skill that covers 80% of cases
creates the 20% where Claude improvises. These skills are dense
by design.

**No placeholders.** Every script reference in these skills points
to something that exists. Every checklist item has a verification
method. If it's not there yet, it's marked explicitly as pending
— not silently omitted.

---

## License

MIT — see [`LICENSE`](./LICENSE).

Use them, fork them, adapt them. If you improve one, the improvement
is probably useful to someone else.
