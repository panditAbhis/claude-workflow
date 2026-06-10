---
name: feedback-unwanted-mcp
description: Skip removed MCP tools silently — if a tool is removed by the user, don't suggest or reference it
metadata:
  type: feedback
---

Never add, suggest, or mention an MCP tool the user has removed. Skip it silently without breaking the rest of the implementation flow.

**Why:** User prefers free/no-key alternatives or nothing at all for certain tools.

**How to apply:** If any prompt references a removed tool, skip it silently. Do not ask about it or flag its absence.
