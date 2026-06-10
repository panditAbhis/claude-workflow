---
name: user_state_management
description: State management ladder — useState → Zustand → TanStack Query; never put server state in Zustand
metadata:
  type: user
---

Decision ladder:
1. `useState` — local UI state, single component
2. Zustand — client-only shared state (UI flags, modal state, user preferences)
3. TanStack Query — anything from a server (fetch, cache, refetch, mutations)

**Hard rule:** Never put server/async state in Zustand. Zustand is for client state only. Server state lives in TanStack Query with proper cache keys.

**How to apply:** When asked about state, recommend the lowest rung that fits. When adding a new store, confirm it's not duplicating server state that belongs in Query.
