# CHANGELOG

All notable changes to this template are documented here.
Format follows [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).
Versioning follows [Semantic Versioning](https://semver.org/).

---

## [2.0.0] — 2026-02

### Added
- **Agentic Workflow** section: core principles, task decomposition protocol, subagent usage rules
- **MCP Tools Usage** section: per-tool-type discipline (filesystem, web, code execution, database), tool guardrails table
- **Context Preservation** section: within-session hygiene, cross-session session summary format, `CONTEXT.md` workflow
- **Token Optimization** section: Claude responsibilities and developer prompting guidance
- **Claude Response Format Quick Reference** table
- `CONTEXT.md` — live session state scaffold
- `DECISIONS.md` — ADR log with template and first entry (ADR-0001)
- `templates/CLAUDE.override.md` — project-level override template
- `.gitignore` and `.env.example` scaffolds
- `CHANGELOG.md` (this file)
- `README.md` with usage instructions and repo setup guide

### Changed
- Collaboration principles: added explicit "acknowledge uncertainty" rule
- Project structure: added `CONTEXT.md` to root layout

---

## [1.0.0] — 2026-02

### Added
- Initial `CLAUDE.md` with: developer profile, collaboration principles, architecture & design, coding standards, testing strategy, security baseline, performance mindset, project structure, Git/CI-CD workflow, tech stack defaults, SaaS checklist

---

<!-- Add new entries at the top, oldest at the bottom -->