# fullstack-developer

> A Claude Code agent that reads your codebase before touching it.

Most fullstack agents are technology catalogs. This one has opinions — and knows when to stop and ask.

---

## The problem with most fullstack agents

They assume you're starting from scratch. They list every technology they know, generate code that's technically correct, and produce something that doesn't match how your actual project is structured.

The result: correct code that doesn't fit. You spend the next hour adapting it.

---

## What this agent does differently

**Audits before it builds.** Before writing a single line, it reads your schema, your existing API patterns, your component structure, and your auth implementation. It extends what you have instead of replacing it with what it would have done from scratch.

**Has decision criteria, not just a technology list.** It knows when to use tRPC vs REST, when to reach for SSR vs RSC vs static — and the decision is based on your project's constraints, not abstract preference.

**Surfaces ambiguity instead of improvising.** When the schema doesn't support what you asked for, it stops and proposes the minimal change needed. When your request conflicts with the existing architecture, it gives you the options and waits for a decision. Junior engineers improvise here. This agent doesn't.

**Ships a delivery report.** Every completed feature ends with a structured document: what shipped, whether a migration is needed, any new environment variables, explicit scope boundaries, and — critically — anything fragile it noticed but didn't touch. Those become your decisions, not surprises.

---

## When to use it

Activate this agent when a change in one layer forces changes in the others:

- New feature that requires schema + endpoint + UI built together
- Refactor that changes a contract all layers depend on (rename a field, change the auth model, switch from REST to tRPC)
- Existing code in one layer contradicts what another layer expects
- AI feature that needs embedding pipeline + streaming API + frontend together

**Don't activate it for:**

- Purely frontend work (UI changes with no schema or API impact) → use a UI agent instead
- Purely backend work (query optimization, migration with no contract change) → use a database agent instead
- Code review or architecture recommendations (no execution needed)

---

## Installation

**Global** — available across all your projects:

```bash
mkdir -p ~/.claude/agents
cp fullstack-developer.md ~/.claude/agents/
```

**Per project** — scoped to a single repository:

```bash
mkdir -p .claude/agents
cp fullstack-developer.md .claude/agents/
```

Claude Code picks it up automatically. No restart needed.

---

## What it produces

Every feature delivery includes:

| Section | What it tells you |
|---|---|
| **What shipped** | What the feature does, not how it's built |
| **Migration required** | Whether it's safe on live data, whether it needs downtime |
| **Environment variables** | New vars added, whether they're required, what breaks if missing |
| **Known constraints** | What the implementation explicitly does NOT handle |
| **Fragile areas noticed** | Risks observed during the audit that were out of scope — yours to decide |
| **How to verify** | Concrete steps to confirm it works, not just "run the tests" |

---

## Stack

Optimized for the TypeScript-first modern stack:

- **Frontend**: Next.js 15+ App Router, React Server Components, Tailwind CSS
- **API**: tRPC (internal), Hono (external/REST), OpenAPI 3.1
- **Database**: PostgreSQL + Drizzle ORM, pgvector for AI workloads, Redis
- **Auth**: Session cookies or JWT with refresh tokens, RBAC, RLS
- **Monorepo**: Turborepo + pnpm workspaces
- **AI**: Anthropic SDK, Vercel AI SDK, RAG pipelines, streaming with `useChat`
- **Testing**: Vitest, Playwright, integration tests for every endpoint
- **Deploy**: Vercel, Railway, Fly.io

---

## Hard limits

Things this agent will never do silently:

- Run a destructive migration without flagging it first
- Introduce a new dependency without explaining why the existing stack doesn't cover it
- Refactor code outside the scope of the task (it surfaces it instead)
- Make product decisions (modal vs page, feature scope) — those come back to you
- Deploy anything (prepares code for deployment; deployment is your call)

---

## Part of a larger collection

This agent is one of a set of Claude Code agents and Claude.ai skills built with the same philosophy: explicit criteria over clever defaults, structured output over freeform responses, and scope discipline over doing more than asked.

→ [View the full collection](#)
