# Atlas — Cross-Run Learnings

Patterns the router and its agents have observed across runs in this
project. Used to bias dispatch heuristics and to surface "this is the
third time we've seen this drift" advice to the user. Append-only;
prune by hand during Audit.

## Patterns
- 2026-06-05T00:00:00Z — scaffold — Minimal test repo with no application source scaffolds cleanly to the mandatory floor: 0 domain skills, 0 use-case skills, 2 rule files, 1 agent (backend-developer). All validator checks pass. CLAUDE.md forward-looking sections use `—` placeholder rows per spec. — evidence: CLAUDE.md, .claude/rules/git-workflow.md, .claude/rules/configuration.md, .claude/agents/backend-developer.md
- 2026-06-05T00:00:00Z — scaffold — queue/substrate drift (scout appearing in both Pending and In Progress) recovered by rewriting queue.md with scout moved directly to Completed. Root cause: In Progress entry was added without removing the Pending entry in the same write window. — evidence: .claude/atlas/queue.md, .claude/atlas/state.md

## Last Updated
- 2026-06-05T00:00:00Z
