# Claude Code — Global

## Who I Am

Senior full-stack engineer. macOS. Read code first. Verify external API/library behavior with context7 — training data may be stale.

---

## Core Principles

1. Think before coding — state assumptions, ask when confused, never silently pick an interpretation
2. Simplicity first — minimum code that solves the problem, nothing speculative
3. Surgical changes — touch only what the task requires, never improve unrelated code
4. Goal-driven — define verifiable success criteria, loop until they pass

---

## Model Rules

- Main thread: `claude-sonnet-4-6` — never change unless asked
- Sub-agents: `claude-haiku-4-5-20251001` — pass `model: "haiku"` on every Agent call
- Opus: only when I explicitly ask
- Fallback chain (overload): configured in settings.json as `["claude-opus-4-7", "claude-sonnet-4-6"]`

---

## Session Workflow

1. `/status` → confirm model + effort
2. `/cost` → baseline token count
3. `/plan` → always first, never skip
4. Code the solution
5. `pnpm test` → BLOCKING. Must exit 0 before proceeding. Fix failures before step 6.
6. `/cost` → delta check (BEFORE expensive code-review)
7. `/code-review` → before every PR, no exceptions
8. `/simplify` → cleanup pass only (not a bug review)
9. `/code-review --comment` → post inline to PR when ready

---

## Universal Rules

- Never commit `.env` — maintain `.env.example` with all keys, no values
- Conventional commits: `feat|fix|chore|docs|test|refactor`
- WCAG 2.1 AA on all interactive UI — always
- Never upgrade model or change effort without being asked
- Never touch code outside the current task scope
- When uncertain: stop, name the confusion, ask

---

## Skill Triggers

Mandatory invocations, not suggestions.

| When | Invoke |
|------|--------|
| "build X" / new feature | `/brainstorming` → `/adr` → `/writing-plans` → wait |
| Starting any feature work | `/superpowers:using-git-worktrees` |
| Implementing an approved plan | `/superpowers:executing-plans` |
| 2+ independent tasks | `/superpowers:dispatching-parallel-agents` |
| Any bug or unexpected behavior | `/superpowers:systematic-debugging` |
| Architecture or library decision | `/adr` + `/software-architecture` |
| UI change affecting layout, interaction, or new component | `/frontend-design` → a11y audit → LCP check |
| Adding a new dependency | `pnpm audit --audit-level=moderate` required before commit |
| Receiving code review feedback | `/superpowers:receiving-code-review` |
| Before claiming anything done | `/superpowers:verification-before-completion` |
| Branch complete | `/superpowers:finishing-a-development-branch` |
| Code feels messy | `/simplify` |
| Memory leak suspected | `/chrome-devtools-mcp:memory-leak-debugging` |
| AI / Python agent work | `/ai:building-pydantic-ai-agents` + TDD |
| New repo | Copy `~/.claude/templates/ts-react-project.md` → `.claude/CLAUDE.md` |

---

## Key Commands

```
/status                  → model + effort (run at session start)
/cost                    → token spend (before/after big tasks)
/plan                    → always first
/code-review             → before every PR
/code-review --fix       → auto-apply findings
/code-review --comment   → post inline PR comments
/simplify                → cleanup + auto-fix, not a bug review
/effort xhigh            → hard architectural tasks only, explicit
/compact                 → context bloat control mid-session
/agents                  → all running background sessions
/cd <path>               → switch dir, preserve prompt cache
/reload-skills           → re-scan skill dirs mid-session
--safe-mode              → strips everything, clean baseline (debugging only)
```

---

## Token Hygiene

- Targeted file reads — never full-codebase scans
- Haiku for sub-agents: search, lint, single-file edits
- Never re-read a file just edited
- `/compact` mid-session when context grows large
- `/cost` before and after every agentic run

`.claudeignore` belongs in every project root:

```
node_modules/
dist/
.git/
*.log
coverage/
.next/
build/
```

---

## Debugging

```bash
claude --safe-mode        # strips CLAUDE.md, plugins, skills, hooks, MCPs
/status                   # confirm correct model
/plugin list              # confirm plugins loaded
/plugin list --disabled   # see installed but inactive plugins
```
