# Claude Skills — by Rodri

A collection of Claude skills I use in my own development projects.
Free. No strings attached.

---

## What's a Claude skill?

A skill is a file that Claude reads automatically when the task matches.
No commands. No reminders. No "please write clean code" in every session.
You install it once and it works.

---

## engineering-standards

The default quality bar for all code I write with Claude.

Covers five stacks with language-specific rules for each:

- **Python** / FastAPI
- **JavaScript** / TypeScript / React
- **Dart** / Flutter
- **C#** / .NET
- **SQL**

Universal principles across all of them:
- Solidity over speed. No patches, no "fix it later".
- Standards over invention. If it's a solved problem, use the standard.
- Clean Architecture: business logic independent of framework, UI and I/O.
- Explicit error handling. A hidden failure is a patch by another name.
- Domain-specific naming. No `utils`, `helpers` or `common` dumping grounds.

---

## How to install

1. Download the `.skill` file from this repo.
2. Go to [claude.ai](https://claude.ai) → Settings → Skills.
3. Upload the file.

That's it. Claude will use it automatically when you're working on code.

---

## License

MIT — use it, modify it, share it.
If you adapt it to your stack, I'd be curious to know how.
