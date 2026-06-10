---
name: feedback_error_handling
description: Errors must surface via toast or error boundary; never swallow silently; console.error minimum always
metadata:
  type: feedback
---

Rule: never swallow errors silently. Every catch block must do at minimum `console.error(err)`. User-visible errors go to toast or error boundary — not lost.

**Why:** Silent failures are the hardest bugs to diagnose. A swallowed error looks like a missing feature.

**How to apply:** In every catch block, verify there's a `console.error` or re-throw. In UI components, confirm boundary exists at route level. Never write `catch (e) { /* ignore */ }`.
