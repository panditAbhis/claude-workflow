---
name: feedback_claudemd_structure
description: Global CLAUDE.md must be generic — stack-specific rules belong in project-level CLAUDE.md, not global
metadata:
  type: feedback
---

Global `~/.claude/CLAUDE.md` must contain only universal rules — nothing stack or language specific.

**Why:** Working across TS/React, Python, and other stacks. Hardcoding pnpm/Zod/React rules globally breaks sessions on non-TS projects.

**How to apply:** If asked to update or add to global CLAUDE.md, reject any stack-specific content (package managers, frameworks, libraries, anti-patterns). Those go in project-level `.claude/CLAUDE.md` instead. Use `~/.claude/templates/ts-react-project.md` as the TS/React project template.
