---
name: feedback_pr_workflow
description: PR gate sequence — tests exit 0 → /cost delta → /code-review → /simplify → /code-review --comment
metadata:
  type: feedback
---

Required sequence before any PR is posted:

1. `pnpm test` exits 0 — blocking, fix failures first
2. `/cost` — delta check before expensive review
3. `/code-review` — no exceptions
4. `/simplify` — cleanup pass (not a bug review)
5. `/code-review --comment` — post inline comments to PR

**Why:** Tests must pass before review wastes time on broken code. `/cost` before `/code-review` avoids expensive token spend on a broken state. Simplify after review so the reviewer sees clean code.

**How to apply:** Never declare work done or create a PR without completing this sequence in order.
