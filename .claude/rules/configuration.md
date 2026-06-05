---
name: rule-configuration
topic: configuration
evidence:
  - .claude/settings.local.json
version: 1.0.0
tags: [atlas, rule, configuration]
---

Claude Code project settings for this repository. No application source exists yet; application-configuration conventions (env vars, feature flags, secrets management) will be documented here once source is present.

### R-configuration-1
Store all Claude Code project-scope permission grants and hooks in `.claude/settings.local.json`, never inline in `CLAUDE.md` or any other file.
Evidence: `.claude/settings.local.json` (sole location for project-scoped Claude Code settings).

### R-configuration-2
When adding a new MCP tool permission, place it in the `permissions.allow` array of `.claude/settings.local.json` using the exact string format `mcp__<server>__<tool>` or `Bash(<command> *)`.
Evidence: `.claude/settings.local.json` (`permissions.allow` already contains three entries following this exact format).

### R-configuration-3
Never add application secrets, credentials, or environment variable values to `.claude/settings.local.json`; that file is version-controlled and governs only Claude Code permissions and hooks.
Evidence: `.claude/settings.local.json` (contains only `permissions` block — no secrets).
