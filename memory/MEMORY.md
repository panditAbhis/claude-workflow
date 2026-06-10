# Memory Index

- [Skip unwanted MCP tools](feedback_brave_search.md) — remove MCPs cleanly; silently ignore future references without breaking other work
- [No tokens in settings.json](feedback_no_tokens_in_settings.md) — never write API tokens/secrets into Claude config files; they're plaintext
- [Git commit rules](feedback_git_commit_rules.md) — use correct account per context; never add Claude/AI co-author attribution anywhere in the project
- [CLAUDE.md structure rule](feedback_claudemd_structure.md) — global CLAUDE.md must be generic; stack-specific rules (pnpm, Zod, React) go in project-level .claude/CLAUDE.md
- [Claude Code setup June 2026](project_claude_setup_2026.md) — CLAUDE.md restructured, ts-react template created, security-guidance installed, settings.json updated
- [Testing philosophy](user_testing_philosophy.md) — unit=pure logic, integration=real DB, E2E=critical paths only; no internal DB mocks
- [State management ladder](user_state_management.md) — useState→Zustand→TanStack Query; never server state in Zustand
- [Architecture preferences](user_architecture_preferences.md) — feature-based folders, shared primitives in /components/ui/, no barrel exports on large modules
- [Dependency protocol](feedback_dependency_protocol.md) — bundlephobia + pnpm audit + activity check before any new dep; reject if stale >1yr
- [Error handling](feedback_error_handling.md) — surface via toast/error boundary; never swallow; console.error minimum always
- [No memoization by default](feedback_no_memoization_by_default.md) — no useCallback/useMemo unless React.memo child + Profiler confirms re-render issue
- [PR workflow gate](feedback_pr_workflow.md) — tests exit 0 → /cost → /code-review → /simplify → /code-review --comment; no skipping
- [TS/React template location](reference_template_location.md) — ~/.claude/templates/ts-react-project.md; copy to .claude/CLAUDE.md at repo init
- [GitHub accounts](feedback_github_accounts.md) — keep work and personal GitHub accounts separate; always match account to project context
