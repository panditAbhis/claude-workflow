---
name: feedback_no_memoization_by_default
description: No useCallback/useMemo by default — only when React.memo child + React DevTools Profiler confirms re-render issue
metadata:
  type: feedback
---

Rule: do NOT wrap handlers or computed values in `useCallback`/`useMemo` by default.

Only valid when BOTH conditions are true:
1. The receiving child is wrapped in `React.memo`
2. React DevTools Profiler shows a measurable re-render problem

**Why:** Premature memoization adds reference overhead, makes code harder to read, and rarely helps since most re-renders are cheap. Profiler-first is the correct discipline.

**How to apply:** When writing or reviewing React components, strip default `useCallback`/`useMemo` wrappers. Only add them when the above two conditions are explicitly satisfied.
