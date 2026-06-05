Before any work in this repo, read `.claude/maps/architecture.md` and `.claude/maps/product.md`, observe the rules in `.claude/rules/`, then load the on-demand skill whose description matches the task. Delegate work that fits a specialist agent's trigger to that agent via the Task tool before writing code yourself.

This repository is a minimal test/scaffold repo used to exercise the day-io atlas workflow. No application source, framework manifests, route trees, or business logic have been committed yet. Documentation will grow as code lands; run `day-io-atlas:atlas-router` with Update mode to refresh any section.

## Always-loaded rules

| File | Topic | Grounded in |
| --- | --- | --- |
| [git-workflow](.claude/rules/git-workflow.md) | git-workflow | `.gitignore`, `.claude/atlas/state.md`, `.claude/atlas/queue.md` |
| [configuration](.claude/rules/configuration.md) | configuration | `.claude/settings.local.json` |

## Available specialist agents

Spawn one of these agents via the Task tool when the task description matches the cue.

| Agent | Use when… | Model |
| --- | --- | --- |
| [backend-developer](.claude/agents/backend-developer.md) | The work touches server-side code — API handlers, data access, background jobs, server-side validation. | sonnet |

## Development commands

No build, test, or lint commands are defined yet. This table will be populated once a package manifest or Makefile is committed.

| Command | What it does |
| --- | --- |
| — | — |

## Code conventions

No formatter or linter configuration detected. Conventions will be documented once tooling is committed.

## Platform constraints

No runtime version pins or OS-specific constraints detected.

## Environment variables

No `.env.example` or equivalent found. This table will be populated once one is committed.

| Variable | Purpose |
| --- | --- |
| — | — |

## Common pitfalls

- No application code exists yet. Directories shown by `git status` are atlas scaffold files, not application source.
- The `test-file` at the repo root is a scratch file from initial commits; it is not application source.

## External resources

No canonical external resources cited in READMEs or ADRs yet.

## Documentation freshness

Before every commit, verify the atlas documentation still matches the code.

0. If your change modifies tooling that a rule file is grounded in (test framework swap, lint config change, DB driver swap, security tooling change, CI config change, dependency-policy change), open the affected `.claude/rules/<topic>.md` and confirm every numbered imperative still holds. When any no longer does, run an Update on that rule via the `day-io-atlas:atlas-router` skill.
0.5. If your change adds, removes, or substantially shifts the responsibility of a project-scope sub-agent under `.claude/agents/`, open the affected agent file and confirm its `description`, `Process`, and `Cannot-Do` sections still hold. When any no longer does, run an Update on that agent via the `day-io-atlas:atlas-router` skill (the router routes `agent:<name>` to `atlas-agent-author`, which dispatches `day-io-core:agents-toolkit`).
1. If your change adds, removes, or renames a directory that the architecture map (`/.claude/maps/architecture.md`) does not yet describe, run an Update on the affected domain via the `day-io-atlas:atlas-router` skill.
2. If your change adds or removes a user-facing flow that the product map (`/.claude/maps/product.md`) does not yet describe, run an Update on the affected use case via the same router.
3. If your change modifies code inside a directory that a domain skill already describes, open that skill and confirm its "Entry points", "Data flow", and "Integrations" sections still hold. When any of them no longer holds, run an Update on that domain.
4. If your change alters the visible flow of a use case, open the corresponding use-case skill and confirm its "Main flow" and "Error paths" still match what the actor experiences. When any of them no longer holds, run an Update on that use case.
5. Whenever you cannot tell whether the documentation still matches the code, run an Audit via the router; the report will tell you which skills and rules warrant an Update.

The `day-io-atlas` pre-commit hook will surface a one-line warning when staged code lives in an area whose matching skill was not also staged. The warning is advisory — your commit is never blocked — but the warning is the cheapest moment to address drift. Rules-tier drift is not detected by the pre-commit hook; it is detected by the Audit workflow.
