# Reference: CLAUDE.md Template

`CLAUDE.md` is the technical map of the repository for Claude Code. It lives
at the repo root and has no mirror in the Claude.ai Project — it is read
exclusively by Claude Code. When Code starts a session in a project, it reads
`CLAUDE.md` first to orient itself without exploring the repo blindly.

This reference provides the canonical template. Fill it when starting a new
project. Keep it updated whenever the structure, commands, or conventions
change. A stale `CLAUDE.md` is worse than a missing one — it gives Code
false confidence.

---

## Template

```markdown
# CLAUDE.md — [Project Name]

Technical map of this repository for Claude Code.
Last updated: [DATE]

---

## Project overview

[One paragraph: what this project is, what it does, who uses it.
Not for Code to understand the product — for Code to understand
the purpose of the codebase it is working in.]

## Stack

- **Frontend:** [e.g. React 18 + TypeScript + Vite]
- **Backend:** [e.g. Python 3.12 + FastAPI]
- **Database:** [e.g. SQLite (dev) → PostgreSQL (production)]
- **Auth:** [e.g. Google OAuth 2.0]
- **Package manager:** [e.g. npm / pip / pub]
- **Runtime:** [e.g. Node 20 / Python 3.12]

## Repository structure

[Paste the actual folder tree here. Keep it current.
Only include directories that Code needs to know about.]

[project-root]/
├── CLAUDE.md                    ← this file
├── docs/
│   ├── project-context/         ← context files (mirrored in Claude.ai Project)
│   └── code-output/             ← Code's outbox (gitignored)
├── [frontend-folder]/
│   └── src/
│       ├── [structure here]
├── [backend-folder]/
│   └── [structure here]
└── .github/
    └── workflows/

## Development commands

[Every command Code might need to run. Be precise — wrong commands waste tokens.]

### Install dependencies
\`\`\`bash
# Frontend
cd [frontend-folder] && npm install

# Backend
cd [backend-folder] && pip install -r requirements.txt
\`\`\`

### Run in development
\`\`\`bash
# Frontend (port XXXX)
cd [frontend-folder] && npm run dev

# Backend (port YYYY)
cd [backend-folder] && uvicorn main:app --reload
\`\`\`

### Run tests
\`\`\`bash
# Frontend
cd [frontend-folder] && npm test

# Backend
cd [backend-folder] && pytest
\`\`\`

### Build for production
\`\`\`bash
cd [frontend-folder] && npm run build
\`\`\`

## Naming conventions

[Copy from glossary.md. Be specific about what goes where.]

- **Backend files:** `snake_case.py`
- **Frontend components:** `PascalCase.tsx`
- **Frontend hooks:** `camelCase.ts` with `use` prefix
- **CSS/tokens:** [convention]
- **Database tables:** `snake_case`
- **API routes:** [convention — e.g. no /api prefix, grouped by resource]

## Architectural decisions to preserve

[These are non-negotiable. Code must not propose changes that violate them.]

1. [e.g. Frontend never accesses DB or credentials directly — all via backend API]
2. [e.g. Backend is the only layer with access to OAuth tokens]
3. [e.g. No business logic in route handlers — service layer only]
4. [add project-specific decisions]

## Untouchable zones

[Files or folders Code must not modify unless the prompt explicitly says so.]

- `[path]` — [reason]
- `[path]` — [reason]

## Context files location

Project context files (mirrored in Claude.ai Project) live in:
`docs/project-context/`

Files: [list the ones this project has]

## Code output outbox

Code writes reports, drafts, and block files to:
`docs/code-output/`

This folder is in `.gitignore`. Files here are temporary.

## Known gotchas

[Anything that would trip up Claude Code without warning.
Add entries as they are discovered.]

- [e.g. The frontend dev server must be running for OAuth redirects to work locally]
- [e.g. Database migrations must be applied before running the backend]
- [add project-specific gotchas]
```

---

## Rules for keeping CLAUDE.md current

- Update the structure section whenever a folder is added, moved, or deleted.
- Update commands whenever the build or run process changes.
- Update naming conventions whenever they are revised.
- Update architectural decisions whenever a new non-negotiable is established.
- Add a gotcha whenever Code trips over something unexpected.

`CLAUDE.md` is updated by Claude Code via prompt — the user does not edit it
manually. When a context update is needed, the relevant department chat
generates a prompt that includes updating `CLAUDE.md` as part of the changes.
