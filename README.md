# claude-workflow

> How I turned Claude into a disciplined senior developer — not just a fast one.

## Resources

| | Link |
|---|---|
| Full series | [dev.to/panditabhis](https://dev.to/panditabhis) |
| Workflow files | [github.com/panditAbhis/claude-workflow](https://github.com/panditAbhis/claude-workflow) |

---

## Read the Series (in order)

| Part | Title | What you will learn |
|------|-------|---------------------|
| 1 | [Overview — the full system](https://dev.to/panditabhis/how-i-turned-claude-into-a-disciplined-senior-developer-not-just-a-fast-one-1a59) | Why discipline matters, how all 7 layers fit together |
| 2 | [Your AIs Employee Handbook: CLAUDE.md](https://dev.to/panditabhis/your-ais-employee-handbook-a-deep-dive-into-claudemd-3obc) | How to write the file Claude reads every session |
| 3 | [Teaching an AI to Never Forget](https://dev.to/panditabhis/teaching-an-ai-to-never-forget-how-the-memory-system-works-40o3) | The memory system — lessons that survive sessions |
| 4 | [Battle Scars as Rules](https://dev.to/panditabhis/battle-scars-as-rules-inside-the-feedback-files-5ejj) | The 8 feedback rules and the stories behind them |
| 5 | [Your Coding DNA](https://dev.to/panditabhis/your-coding-dna-the-three-files-that-shape-every-line-claude-writes-378g) | Architecture, state management, and testing preferences |
| 6 | [Context is King](https://dev.to/panditabhis/context-is-king-how-project-files-and-templates-keep-claude-on-track-433l) | Project context files and the template system |
| 7 | [A Day in the Life](https://dev.to/panditabhis/a-day-in-the-life-complete-claude-code-session-walkthrough-7o9) | Complete 9-step session walkthrough with a real feature |

---

## What is in this repo

```
CLAUDE.md          global Claude Code handbook (loads every session)
memory/
  MEMORY.md        index of all memory files
  feedback_*.md    rules learned from past mistakes
  user_*.md        personal preferences (architecture, state, testing)
  project_*.md     setup context
  reference_*.md   template pointers
```

## Quick Reference

```
/status                  confirm model + effort
/cost                    token spend snapshot
/plan                    design before coding
pnpm test                BLOCKING gate — must exit 0
/code-review             before every PR
/simplify                readability cleanup
/code-review --comment   inline PR comments
```

## The 9-Step Session Workflow

| Step | Command | Purpose |
|------|---------|---------|
| 1 | /status | Confirm correct model loaded |
| 2 | /cost | Baseline token snapshot |
| 3 | /plan | Design before touching code |
| 4 | Code | Actual implementation |
| 5 | pnpm test | Blocking gate — fix failures first |
| 6 | /cost | Delta check before expensive review |
| 7 | /code-review | Bug and design audit |
| 8 | /simplify | Readability cleanup |
| 9 | /code-review --comment | Post inline PR comments |

---

*Personal workflow. Refined over multiple projects. The system evolves — the discipline does not.*
