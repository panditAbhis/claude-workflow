---
name: user_architecture_preferences
description: Folder structure preferences — feature-based, no barrel exports on large modules, shared primitives in /components/ui/
metadata:
  type: user
---

Folder structure: feature-based. Each feature owns its components, hooks, types, tests.

```
/features/auth/
  AuthForm.tsx
  AuthForm.test.tsx
  useAuth.ts
  auth.types.ts
/components/ui/
  Button.tsx
  Input.tsx
```

Shared primitives (Button, Input, Modal): `/components/ui/` only — never inside a feature folder.

No barrel exports (`index.ts` that re-exports everything) on large modules — they slow TS server and make tree-shaking opaque. Small util packages OK.

**How to apply:** When creating new files, place in feature folder. When suggesting refactors, don't flatten into layer-based structure (components/, hooks/, pages/).
