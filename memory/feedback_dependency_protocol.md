---
name: feedback_dependency_protocol
description: Before adding any new dependency — bundlephobia size check + pnpm audit + repo activity check; no deps stale >1yr
metadata:
  type: feedback
---

Before adding any dependency, run these checks in order:

1. **bundlephobia** — check bundle size impact
2. `pnpm audit --audit-level=moderate` — catch known vulnerabilities before commit
3. **Repo activity** — last commit within 1 year? If not, find an alternative

**Why:** Dependencies are long-term liabilities. Size bloat is invisible until LCP degrades. Stale repos don't get security patches.

**How to apply:** When suggesting `pnpm add <pkg>`, include the audit command in the suggestion. Reject deps with no activity in the last year unless there's no viable alternative.
