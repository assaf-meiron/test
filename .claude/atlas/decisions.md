# Atlas — Evidence Provenance

Cited evidence paths captured by Scout for each artifact produced during the run. Used by Update to detect which area changed (git diff against the paths recorded here) and by Audit to find vanished evidence.

## Scout Inventory Sources
- (Scaffold + Update — repo paths Scout read to build the inventory: README, manifests, ARCHITECTURE.md, ADRs, route definitions, etc.)

## Domain Evidence
- (One row per authored domain: `dom-<slug>` → list of cited paths.)

## Use-Case Evidence
- (One row per authored use case: `uc-<NNN>-<slug>` → list of cited paths.)

## Rule Evidence
- (One row per authored rule: `rule:<topic>` → list of cited paths.)

## Agent Evidence
- (One row per authored agent: `<name>` → list of cited owned-directory paths.)

## Routing Decisions
- (One row per decision the router resolved via `AskUserQuestion`. Format: `- <UTC ISO-8601 timestamp> — <source_step> — "<question verbatim>" — chosen: "<chosen option label>"`. When the user picked the auto-appended "other" escape, the chosen-option column reads `(other) <free text>`. Schema and worked examples in `asking-the-user.md`.)

## Last Updated
- -
