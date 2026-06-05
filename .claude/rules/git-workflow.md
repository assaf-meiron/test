---
name: rule-git-workflow
topic: git-workflow
evidence:
  - .gitignore
  - .claude/atlas/state.md
  - .claude/atlas/queue.md
version: 1.0.0
tags: [atlas, rule, git-workflow]
---

This rule governs branch management and commit hygiene for this repository. The day-io toolchain owns the git lifecycle; follow it rather than improvising git commands.

### R-git-workflow-1

Never commit directly to `main` — always cut a feature branch first using `/day-io-core:day-io-branch`.

Evidence: `.claude/atlas/state.md` (run branch is `docs/atlas-scaffold`, base is `main`; all scaffold work lands on the feature branch).

### R-git-workflow-2

Follow the day-io git lifecycle order: branch → commit → push → open PR. Do not skip or reorder steps.

Evidence: `.claude/atlas/queue.md` (`closing-commit` → `closing-push` → `closing-pr` → `closing-return-to-base` defines the canonical sequence).

### R-git-workflow-3

Never stage or commit files matching `*.local.*` patterns under `.claude/` — the gitignore policy excludes them from tracking.

Evidence: `.gitignore` (`.claude/*.local.*` and `.claude/**/*.local.*` are day-io-core managed exclusions).

### R-git-workflow-4

Never stage or commit files inside hidden subdirectories under `.claude/` (paths matching `.claude/.*/` or `.claude/**/.*/`) — the gitignore policy excludes them.

Evidence: `.gitignore` (`.claude/.*/` and `.claude/**/.*/` are day-io-core managed exclusions).
