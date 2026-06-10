# claude-workflow

> How I turned Claude into a disciplined senior developer — not just a fast one.

## Resources

| | Link |
|---|---|
| Full write-up | [dev.to article](https://dev.to/panditabhis/how-i-turned-claude-into-a-disciplined-senior-developer-not-just-a-fast-one-1a59) |
| Workflow files | [github.com/panditAbhis/claude-workflow](https://github.com/panditAbhis/claude-workflow) |

## What's in this repo

```
CLAUDE.md          ← global Claude Code handbook (loads every session)
memory/
  MEMORY.md        ← index of all memory files
  feedback_*.md    ← rules learned from past mistakes
  user_*.md        ← personal preferences (architecture, state, testing)
  project_*.md     ← setup context
  reference_*.md   ← template pointers
```

## Quick Reference

```
/status          confirm model + effort
/cost            token spend snapshot
/plan            design before coding
pnpm test        BLOCKING gate — must exit 0
/code-review     before every PR
/simplify        readability cleanup
/code-review --comment   inline PR comments
```

## The 9-Step Session Workflow

1. `/status` — confirm model loaded
2. `/cost` — baseline token snapshot
3. `/plan` — design before touching code
4. Code the solution
5. `pnpm test` — blocking gate, fix failures first
6. `/cost` — delta check before expensive review
7. `/code-review` — bug + design review
8. `/simplify` — readability cleanup
9. `/code-review --comment` — post inline PR comments

---

*Personal workflow. Refined over multiple projects. The system evolves — the discipline doesn't.*
