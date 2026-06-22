# working-system skill

Professional working methodology with Claude.ai and Claude Code for software
projects. Defines the actors, operative vocabulary, commands, Asana task
system, task lifecycle, session management, and the Claude Code handoff
protocol.

---

## What this skill does

When installed, Claude.ai knows and applies:

- **§0 Core principle:** the non-negotiable quality standard and the
  decision criterion for every technical proposal.
- **The three actors:** Claude.ai (think and decide), Claude Code (execute),
  the user (coordinate). Each with its role and limits.
- **Operative vocabulary:** exchange, task, session — three words with
  distinct meanings the system uses precisely.
- **Departments:** what they are, when to use them vs. a single generalist
  chat, the ownership rule, the redirection rule with prompt included.
- **Context files as real memory:** why keeping them current is what makes
  the department system work across chat recycles.
- **Commands:** `[SQ]`, `[MQ]`, `recycle chat` — with their exact behaviour
  and when to use them.
- **The Asana task system:** one board per project with SideQuests and
  MainQuests sections; immediate creation via MCP when a task is noted.
- **The task lifecycle:** open → discuss → summary → OK → prompt → Code
  executes → verify → close.
- **Session management in Claude Code:** `/checkpoint`, `/session-close`,
  `/context-sync` — the three commands that handle commits, PRs, and
  mirror updates.
- **The Code handoff protocol:** fixed six-field format, summary before
  the prompt, no improvisation.
- **Internal reports:** flow, file naming, destination when closing the task.
- **Error recovery:** forgotten session, unexpected Code behaviour, blocks,
  outdated chats.

---

## What lives in this skill vs. in project instructions

| Content | Where |
|---|---|
| Core principle and quality standard | **Skill** |
| What a department is, ownership rule, redirection rule | **Skill** |
| Concrete list of departments for the project | **Project instructions** |
| Commands and their behaviour | **Skill** |
| Asana board name and ID | **Project instructions** |
| Session management commands | **Skill** (+ `~/.claude/skills/` in Code) |
| Repo path and MCP connector | **Project instructions** |
| Handoff protocol format | **Skill** |
| Project context files | **Project instructions** |

---

## Relation to other skills

This skill defines the working system. Other skills define how to do the
work within the system:

- `github-workflow` — the git flow that `/session-close` and `/checkpoint`
  follow.
- `atomic-design` — the UI component methodology that Frontend and Design
  departments apply.
- `engineering-standards` — the code standards that Claude Code applies.
- `audit-system` *(in progress)* — the audit system that the Audit
  department runs.
- `code-commands` — the three Claude Code personal skills that implement
  the session management layer (`/session-close`, `/checkpoint`,
  `/context-sync`).

---

## Installation

Save the skill from Claude.ai or package with:

```bash
python -m scripts.package_skill working-system/ /output/path/
```

Install in the Project alongside the project-specific instructions.
The skill covers the system; the instructions cover the project.
