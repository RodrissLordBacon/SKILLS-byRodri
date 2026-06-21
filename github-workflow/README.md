# github-workflow skill

A [Claude skill](https://www.anthropic.com/claude) that encodes a professional
Git and GitHub workflow for solo developers — based on GitHub Flow, Conventional
Commits, and GitHub CLI.

---

## What this skill does

When installed, this skill instructs Claude Code to:

- Evaluate every change and choose the right path: direct to `main` for
  trivial atomic changes, feature branch + PR for anything with risk or scope
- Name branches using Conventional Branch conventions (`feature/`, `fix/`,
  `refactor/`, `chore/`, `docs/`, `hotfix/`)
- Write commit messages following Conventional Commits (`feat:`, `fix:`,
  `refactor:`, `chore:`, `docs:`, etc.)
- Open and merge pull requests using GitHub CLI (`gh`)
- Run `/code-review` before merging and handle blockers correctly
- Close sessions cleanly with meaningful commits — no snapshots, no WIP commits
- Handle hotfixes on a dedicated branch with a fast-track PR for audit trail

---

## Standards used

| Standard | What it covers |
|---|---|
| [GitHub Flow](https://docs.github.com/en/get-started/using-github/github-flow) | Branching model: short-lived branches, always-deployable main |
| [Conventional Commits](https://conventionalcommits.org) | Commit message format |
| [Conventional Branch](https://conventional-branch.github.io/) | Branch naming format |
| [GitHub CLI](https://cli.github.com) | PR creation, review, and merge |

---

## Prerequisites

- Git installed and configured
- GitHub CLI (`gh`) installed — [cli.github.com](https://cli.github.com)
- `gh auth login` completed for the target repository

---

## The two paths at a glance

```
Change is atomic, reversible, no logic touched?
    └── YES → commit directly to main
    └── NO  → feature branch → PR → /code-review → squash merge
```

---

## Branch naming

```
feature/oauth-multiuser
fix/session-cookie-expiry
refactor/analytics-service
chore/update-dependencies
hotfix/login-crash-on-empty-token
```

---

## Commit message format

```
feat(auth): add Google OAuth multi-account support
fix(session): handle expired refresh token without crashing
refactor(analytics): extract service layer from main handlers
chore(deps): upgrade SQLAlchemy to 2.0.36
```

---

## Installation

### Claude Skills (`.skill` file)

```bash
python -m scripts.package_skill github-workflow/
```

Upload the resulting `.skill` file to your Claude environment.

### Claude.ai Projects (RAG)

Copy `SKILL.md` into your Claude Project's files.

---

## What this skill replaces

The "session snapshot commit" pattern — committing a WIP snapshot before
making changes — is an antipattern. This skill replaces it with:

- Meaningful incremental commits throughout the session
- Proper Conventional Commits messages on every commit
- Branch protection via PR even for hotfixes
- `git revert` for rollback instead of manual snapshot restoration
