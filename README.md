# MEO vs Omnigent Black-Box Reproduction Handoff

This repository-facing handoff supports two review paths:

1. **Archived Evidence Verification**  
   Deterministically verify the historical MEO-vs-M0 evidence from packaged artifacts.

2. **Independent Omnigent Replication Contract**  
   Run a portable 24-arm M0-vs-MEO replication contract inside an Omnigent/Databricks-controlled runtime.

## Start Here

Read:

`OPEN_THIS_FIRST.md`

Then inspect:

`BLACKBOX_REPRODUCTION_STATUS.md`

## Release Assets

### Archived Evidence Verification

`release-assets/ARCHIVED_EVIDENCE_VERIFICATION_KIT.zip`

Purpose:

- verify archived MEO-vs-M0 evidence;
- verify hashes and package integrity;
- inspect audits, claim maps, cost checks, selected arms, and reference outputs;
- perform file-only dry verification with no provider/model calls.

### Independent Omnigent Replication Contract

`release-assets/INDEPENDENT_OMNIGENT_REPLICATION_CONTRACT_24ARM.zip`

Purpose:

- provide 12 selected scenarios;
- provide 24 planned arms: M0 baseline and M1/MEO treatment for each scenario;
- provide package-relative task workspaces, schemas, and reference outputs;
- enable Omnigent/Databricks builders to rerun the contract in their own trusted Omnigent runtime.

## Archived M1 Observability

The global M1 audit inventory is included at:

`audits/global-m1-audit-inventory/`

It records historical M1/MEO outputs, treatment/proof/manipulation artifacts, scanner/evidence artifacts, trace-like files, and score/audit derivation files across the broader evidence set.

## Reviewer Positioning

This handoff does not ask reviewers to resurrect a historical local launcher. The important question is whether the archived evidence verifies cleanly and whether Omnigent builders can take the same experimental contract and run M0 vs MEO in their own environment.
rn## Additional Reviewer Documentsrnrn- RAW_ARTIFACT_INDEX.md maps large raw bundles to experiment families.rn- BLACKBOX_MEO_BOUNDARY.md defines what is exposed while keeping MEO explicitly black-box.rn
