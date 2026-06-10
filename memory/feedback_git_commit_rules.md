---
name: feedback_git_commit_rules
description: Git commit rules — use correct account per project context; never add Claude/AI co-author attribution
metadata:
  type: feedback
---

Always use the correct git identity for the project context (work vs personal).

Never add "Co-Authored-By: Claude..." or any AI collaborator attribution to commits, PR bodies, or anywhere in the project.

**Why:** Work and personal projects use different identities. AI attribution is not wanted in project history.

**How to apply:** Before every `git commit`, confirm the correct `user.email` and `user.name` are set for the context. Strip all "Co-Authored-By" lines from commit messages. Never mention Claude/AI as a contributor in README, CHANGELOG, PR descriptions, or any project file.
