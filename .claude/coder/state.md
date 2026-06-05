# day-io-coder — state

The router's first read on every turn. Plain markdown so the file is diff-friendly, commit-friendly, and reviewable by a human. The controller is the only writer.

## Run

idle

<!--
Populated shape (the router writes these key/value lines once a run is active):
  run-id: <workflow>-<UTC-stamp>-<short-random>
  branch: <feature branch cut by /day-io-core:day-io-branch>
  base:   <base branch the feature was cut from, as reported by day-io-branch>
  started: <ISO-8601 UTC>

`base:` is required so finalize can `git checkout <base> && git pull --ff-only`
the local working tree back to the recorded base after the PR opens.
`repo_state.py.trunk` resolves to `main`/`master` only — it cannot substitute
for the recorded base when day-io-branch cut from `dev`/`stage`.
-->


## Workflow

idle

## Phase

idle

## Focus

No active focus.

## Verification

not yet proven

## Blockers

None.

## Settings

- auto_proceed: false
- doc_sync_enabled: true
- remediation_cycle_cap: 2
- verifier_sample_size: 10
- promote_knowledge: true
- hook_posture.pretooluse_state_guard: audit
- hook_posture.posttooluse_record_audit: audit
- hook_posture.sessionstart_rehydrate: audit
- hook_posture.precompact_snapshot: audit
- hook_posture.subagentstop_contract_audit: audit
- hook_posture.stop_persist: audit
- hook_posture.stopfailure_log: audit
- hook_posture.taskcompleted_metadata_audit: audit
- hook_posture.posttooluse_security_patterns: audit
- security_completion_posture: gated
- security_inline_enabled: true
- security_turn_enabled: true
- security_commit_enabled: true
- connector_availability.knowledge_promotion: unknown
