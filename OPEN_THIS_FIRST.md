# Five-Minute Reader Map

This repository is a black-box reproduction handoff for MEO vs Omnigent. It is organized around five distinct reviewer actions:

1. Verify the archived MEO evidence.
   Use `ARCHIVED_EVIDENCE_VERIFICATION_KIT.zip` from the release assets. This is deterministic and file-only: no provider calls, no WSL requirement, no opencode requirement, and no local gateway requirement.

2. Inspect MEO operational treatment evidence.
   Use the archived outputs, audit files, treatment evidence, raw artifact index, claim maps, hashes, and score derivations. These show what MEO produced and how the MEO-treated arms differed operationally from comparator arms.

3. Keep MEO internals black-boxed.
   The handoff exposes task contracts, prompts/tasks, schemas, outputs, traces/audits where archived, treatment markers/proofs where archived, score derivations, and replication materials. It does not expose MEO source code, private internals, private internal deliberation, provider credentials, or local launcher secrets.

4. Run fresh independent replication in an Omnigent-controlled environment.
   Use `INDEPENDENT_OMNIGENT_REPLICATION_CONTRACT_24ARM.zip` from the release assets. It contains the portable 24-arm A/B replication contract: 12 scenarios, 2 treatments per scenario, no dependence on the historical local launcher.

5. Compare fresh A/B outputs using the supplied contracts.
   For each selected scenario, run treatment A and treatment B in the reviewer’s own Omnigent execution environment, then compare outputs using the supplied schemas, reference outputs, task materials, and scoring/verification contract.

In short: archived evidence verification checks what happened historically; independent replication tests the same A/B contract in the reviewer’s own Omnigent runtime; MEO remains black-box throughout.

---
# Open This First

This handoff is organized for Omnigent/Databricks-side inspection of MEO as a black-box control-layer intervention.

There are two intended workflows.

## 1. Archived Evidence Verification

Use this when you want to verify the historical MEO-vs-M0 evidence without running any model/provider calls.

Release asset:

`release-assets/ARCHIVED_EVIDENCE_VERIFICATION_KIT.zip`

This verifies archived outputs, hashes, claim maps, audits, selected reference arms, cost/capability checks, and package integrity. It is intentionally file-only: no WSL, no opencode, no Fireworks, no gateway, no paid provider call.

## 2. Independent Omnigent Replication Contract

Use this when an Omnigent/Databricks builder wants to run the selected M0-vs-MEO experiment inside their own trusted Omnigent runtime.

Release asset:

`release-assets/INDEPENDENT_OMNIGENT_REPLICATION_CONTRACT_24ARM.zip`

This package contains a portable 24-arm plan: 12 scenarios x 2 treatments, with package-relative paths, schemas, task workspaces, and archived reference outputs.

The live replication is expected to be run by Omnigent/Databricks using their own runner, model/provider route, credentials, and instrumentation.

## Important Boundary

MEO remains explicitly black-box. The package exposes observable behavior: task inputs, M0/M1 outputs, treatment records where archived, score/audit derivations, trace-like artifacts, and final-state differences. It does not expose private private internal deliberation or require reconstructing Harsh's historical local launcher.
rn## Black-Box Boundary and Raw ArtifactsrnrnRead BLACKBOX_MEO_BOUNDARY.md for the explicit black-box interpretation of MEO. Read RAW_ARTIFACT_INDEX.md to locate raw artifacts across imperative, ablation, tools/scanner, public benchmark, and audit packages.rn


