# DECISIONS.md — Architecture Decision Records

> A persistent log of significant technical and architectural decisions.
> Each entry captures the context, options considered, the decision made, and the rationale.
> Never delete entries — superseded decisions should be marked as such and linked to the new ADR.
>
> **When to add an entry**: any decision that would take >10 minutes to re-derive, involves a meaningful tradeoff,
> or would be confusing to a future reader (or Claude) without explanation.

---

## ADR Template

```markdown
### ADR-XXXX — [Short Decision Title]

- **Date**: YYYY-MM-DD
- **Status**: `Proposed | Accepted | Superseded by ADR-XXXX | Deprecated`
- **Deciders**: [Who was involved]

**Context**
What situation or problem prompted this decision?

**Options Considered**
1. Option A — brief description + tradeoffs
2. Option B — brief description + tradeoffs
3. Option C — brief description + tradeoffs (if applicable)

**Decision**
What was decided and why.

**Consequences**
What becomes easier, what becomes harder, what constraints does this impose.

**References**
- Links to relevant docs, PRs, issues, or prior art
```

---

## Decision Log

---

### ADR-0001 — Use CLAUDE.md as AI Collaboration Contract

- **Date**: 2026-02
- **Status**: `Accepted`
- **Deciders**: Developer

**Context**
Claude has no persistent memory across sessions. Without a stable, version-controlled context file, every new session requires re-establishing project standards, stack preferences, coding conventions, and collaboration expectations — which is wasteful and error-prone.

**Options Considered**
1. **Re-explain context per session in each prompt** — flexible but verbose, costly in tokens, and inconsistent over time.
2. **Use a system prompt in the Claude API** — works for API usage but not for Claude Code or claude.ai sessions.
3. **Version-controlled `CLAUDE.md` at repo root** — read once per session, consistent, diffable, team-shareable.

**Decision**
Use `CLAUDE.md` as the canonical collaboration contract. Pair it with `CONTEXT.md` for live session state and `DECISIONS.md` for architectural history. Claude is instructed to read all three at session start.

**Consequences**
- Session startup requires one explicit instruction to load context files.
- Standards drift is visible in git history.
- New team members or AI sessions get full context immediately.
- Requires discipline to keep `CONTEXT.md` updated at session end.

**References**
- [Anthropic Claude Code documentation](https://docs.anthropic.com)

---

<!-- Add new ADRs above this line, incrementing the ID -->