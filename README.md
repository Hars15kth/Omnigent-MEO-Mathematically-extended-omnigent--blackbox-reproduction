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

`ARCHIVED_EVIDENCE_VERIFICATION_KIT.zip` from the GitHub release assets

Purpose:

- verify archived MEO-vs-M0 evidence;
- verify hashes and package integrity;
- inspect audits, claim maps, cost checks, selected arms, and reference outputs;
- perform file-only dry verification with no provider/model calls.

### Independent Omnigent Replication Contract

`INDEPENDENT_OMNIGENT_REPLICATION_CONTRACT_24ARM.zip` from the GitHub release assets

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


## Additional Reviewer Documents

- RAW_ARTIFACT_INDEX.md maps large raw bundles to experiment families.
- BLACKBOX_MEO_BOUNDARY.md defines what is exposed while keeping MEO explicitly black-box.




