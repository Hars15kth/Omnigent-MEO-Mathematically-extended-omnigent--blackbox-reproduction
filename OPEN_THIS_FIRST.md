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

