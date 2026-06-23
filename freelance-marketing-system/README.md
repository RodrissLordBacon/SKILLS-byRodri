# marketing — Claude Skill

A marketing and sales skill for freelance creative professionals.
Built to work as a real thinking partner, not a list of generic tips.

---

## What it does

Gives Claude a structured system for marketing and sales tasks specific
to creative freelancers: copy auditing and writing, LinkedIn content,
portfolio case studies, competitive analysis, and positioning.

Includes two specialized agents for focused tasks:

- **copy-studio-agent** — audits and rewrites website copy section by
  section, with diagnosis before proposal and explicit reasoning for
  every change.
- **linkedin-content-agent** — creates and reviews LinkedIn posts with
  a focus on shifting the audience from professional peers toward
  actual clients (the ICP).

---

## What makes it different from generic marketing advice

Two hard rules built into every mode:

**No data, no recommendations.** The skill always asks what data is
available before proposing anything. Analytics, behavioral data,
existing copy — it works from what is real. When data is missing, it
declares hypotheses explicitly rather than presenting assumptions as facts.

**No generic copy.** Every text output is evaluated against a voice
filter. If the output could have been written by any other professional
in the same field, it is not ready. The skill is designed to be
loaded alongside a `voice-guide.md` that captures the specific voice
of the professional.

---

## File structure

```
marketing/
├── SKILL.md                          — Core skill, modes of operation
├── README.md                         — This file
├── agents/
│   ├── copy-studio-agent.md          — Website copy agent
│   └── linkedin-content-agent.md     — LinkedIn content agent
└── references/
    ├── copy-structures.md            — Copy structures by format and channel
    └── linkedin-patterns.md          — LinkedIn patterns for B2B creative services
```

---

## How to install

Download `marketing.skill` and install it from the Claude.ai Skills
settings, or drop it into your `~/.claude/skills/` folder if using
Claude Code.

---

## How to use

The skill activates automatically when the task involves marketing,
copy, content, or client acquisition. You can also load it explicitly
by mentioning the mode you want:

- "Audit the copy of my landing page" → `copy-audit` mode
- "Write a LinkedIn post about this project" → `linkedin` mode
- "Turn this project into a case study" → `case-study` mode
- "Help me figure out my positioning" → `positioning` mode

For website copy tasks, Claude will load the `copy-studio-agent`.
For LinkedIn tasks, Claude will load the `linkedin-content-agent`.

---

## Context files that make it work better

This skill works well on its own, but it works significantly better
with two context files that you provide:

**`marketing-context.md`** — Your ICP, differentiators, objections,
channel state, and short-term objectives. Without this, the skill
works with generic marketing logic. With it, it works with your
specific business reality.

**`voice-guide.md`** — Your writing voice: patterns, contrasts,
what you never say. Without this, copy outputs default to professional
but generic. With it, outputs sound like you.

Add these files to your Claude Project for the skill to pick them
up automatically.

---

## Built by

Rodrigo Jiménez — [rodrigojimenez.es](https://www.rodrigojimenez.es)

Part of [SKILLS-byRodri](https://github.com/RodrissLordBacon/SKILLS-byRodri),
a collection of Claude skills built for real professional use.
