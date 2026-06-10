---
name: project_claude_setup_2026
description: Claude Code global setup restructured June 2026 — CLAUDE.md split into global/project template, new plugins, settings additions
metadata:
  type: project
---

Restructured global Claude Code setup on 2026-06-10.

**Why:** Global CLAUDE.md had TypeScript/React-specific rules hardcoded — broke mental model when working on non-TS projects. Principle: global = about you, project = about the code.

**Changes made:**

1. `~/.claude/CLAUDE.md` — rewritten as generic: Core Principles, identity, model rules, session workflow, universal rules, skill triggers, key commands, token hygiene, debugging. Zero stack-specific content.

2. `~/.claude/templates/ts-react-project.md` — new file. Drop into any TS/React repo as `.claude/CLAUDE.md`. Contains: stack table, pnpm rules, TypeScript/Zod rules, code style, anti-patterns, Phase 0 checklist.
   - Usage: `mkdir -p .claude && cp ~/.claude/templates/ts-react-project.md .claude/CLAUDE.md`

3. `settings.json` additions:
   - `fallbackModel: ["claude-opus-4-7", "claude-sonnet-4-6"]` — auto-fallback on Opus overload
   - `worktree.bgIsolation: "worktree"` — background sessions isolated from main checkout
   - `env.SECURITY_REVIEW_MODEL: "claude-haiku-4-5-20251001"` — security plugin uses Haiku
   - `env.SG_AGENTIC_MODEL: "claude-haiku-4-5-20251001"` — agentic commit reviewer uses Haiku

4. `security-guidance` plugin installed (user scope). Three layers: regex warnings on Edit/Write, LLM diff review on Stop, agentic review on git commit.

**How to apply:** When starting new TS/React repo, copy template as step in Phase 0.
