# claude-dev-template

> A battle-tested collaboration template for AI-assisted software development with Claude.
> Designed for senior engineers building enterprise software, SaaS products, and personal tools.

---

## What's in This Repo

| File | Purpose |
|------|---------|
| [`CLAUDE.md`](./CLAUDE.md) | Core collaboration contract — coding standards, agentic rules, MCP tool guardrails, token optimization |
| [`CONTEXT.md`](./CONTEXT.md) | Live project state — read by Claude at session start, updated at session end |
| [`DECISIONS.md`](./DECISIONS.md) | Architecture Decision Records (ADRs) — persistent log of significant technical choices |
| [`templates/CLAUDE.override.md`](./templates/CLAUDE.override.md) | Minimal project-level override template — drop into any repo to extend the global config |
| [`.env.example`](./.env.example) | Documented environment variable scaffold |

---

## How to Use

### Option 1 — Global Template (Recommended for Claude Code)

Set this repo as your global Claude context so every project inherits these standards automatically:

```bash
# Clone the repo
git clone https://github.com/<your-username>/claude-dev-template.git ~/.claude-template

# Symlink or copy CLAUDE.md to Claude's global config location
mkdir -p ~/.claude
cp ~/.claude-template/CLAUDE.md ~/.claude/CLAUDE.md
```

### Option 2 — Per-Project Usage

Drop the relevant files into any project root:

```bash
# From your project root
curl -O https://raw.githubusercontent.com/<your-username>/claude-dev-template/main/CLAUDE.md
curl -O https://raw.githubusercontent.com/<your-username>/claude-dev-template/main/CONTEXT.md
curl -O https://raw.githubusercontent.com/<your-username>/claude-dev-template/main/DECISIONS.md
```

Then create a project-level override to customize the stack and any project-specific rules:

```bash
cp ~/.claude-template/templates/CLAUDE.override.md ./CLAUDE.project.md
```

### Option 3 — Use as a GitHub Template Repo

1. Go to this repo on GitHub → **Settings** → check **Template repository**
2. When starting a new project: **Use this template** → creates a new repo with all files pre-populated

---

## Recommended Project File Structure

```
your-project/
├── CLAUDE.md               # Symlinked or copied from this template (global rules)
├── CLAUDE.project.md       # Project-specific overrides (stack, constraints, context)
├── CONTEXT.md              # Live session state — updated by Claude each session
├── DECISIONS.md            # ADRs — updated as architectural decisions are made
├── README.md
├── .env.example
└── src/
```

> **Tip**: In Claude Code, you can instruct Claude to always load `CLAUDE.md`, `CONTEXT.md`, and `DECISIONS.md` at the start of every session by referencing them in your first message or pinning them as project context.

---

## Workflow

### Starting a Session

Tell Claude:
> *"Read CLAUDE.md, CONTEXT.md, and DECISIONS.md before we begin. Today's task is: [task]."*

### Ending a Session

Tell Claude:
> *"Generate a session summary and update CONTEXT.md."*

Claude will produce a structured summary (completed work, decisions, current state, next steps, open questions) ready to paste into `CONTEXT.md`.

---

## Versioning

This template follows [Semantic Versioning](https://semver.org/):

- **Major**: Breaking changes to collaboration contract or structure
- **Minor**: New sections, guardrails, or workflow additions
- **Patch**: Clarifications, corrections, wording improvements

Check [CHANGELOG.md](./CHANGELOG.md) for version history.

---

## Contributing

This is a personal standards template. Fork it and make it yours. If you find a pattern that works better, an ADR is a great place to document why.

---

*Maintained by: [Your Name] | Last updated: 2026-02*