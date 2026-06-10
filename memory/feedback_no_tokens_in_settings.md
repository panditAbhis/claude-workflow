---
name: feedback-no-tokens-in-settings
description: Never store API tokens or secrets in Claude Code settings.json files
metadata:
  type: feedback
---

Never write API tokens, passwords, or other secrets into settings.json (or any Claude config file). These files are plaintext and expose credentials.

**Why:** Config files are often committed to version control or readable by other processes — storing secrets there is a security risk.

**How to apply:** When asked to "set" env vars that are tokens/secrets, do NOT write the values into settings.json `env` block. Instead, advise using shell profile (.zshrc, .bashrc), a secrets manager, or a wrapper script.
