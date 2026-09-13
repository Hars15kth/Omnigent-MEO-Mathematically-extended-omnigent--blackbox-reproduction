# Raw Artifact Index

This document maps the large raw evidence bundles to the experiment families and inspection purposes they support.

The GitHub handoff folder contains the clean audit, verification, and replication-control layer. The large raw evidence bundles should be attached as release assets or supplied alongside this handoff.

## Required Raw / Evidence Bundles

### 1. Positive Delta Slim Bundle

Expected folder:

`omnigent-blackbox-positive-delta-SLIM-20260912T053958Z`

Primary use:

- final positive-delta evidence;
- ablation/component experiments;
- tools/scanners experiments;
- stress/four-component experiments;
- scanner hard-clean, scanner artifact-native, scanner latent-forensic, scanner evidence-obligation, scanner opaque-evidence families;
- confirmed M0/M1 pairs used to build the independent replication contract.

Important contents:

- `bundle/FRESH_48ARM_COMPONENT_ABLATION/`
- `bundle/STRESS_72ARM_FOUR_COMPONENTS/`
- `bundle/SCANNER_HARD_CLEAN_24ARM/`
- `bundle/SCANNER_ARTIFACT_NATIVE_BRUTAL_18ARM/`
- `bundle/SCANNER_LATENT_FORENSIC_BLACKOUT_18ARM/`
- `bundle/SCANNER_EVIDENCE_OBLIGATION_OPAQUE_12ARM/`
- `bundle/SCANNER_EVIDENCE_OBLIGATION_NIGHTMARE_12ARM/`
- `bundle/compiled_and_public_summaries/`

Inspection focus:

- M0 vs M1 result outputs;
- MEO treatment/proof/manipulation records where present;
- scanner/evidence artifacts;
- component ablation outcomes;
- final summaries and capability win records.

### 2. Old Raw Imperative Bundle

Expected folder:

`omnigent-blackbox-OLD-RAW-IMPERATIVE-20260912T062257Z`

Primary use:

- older imperative raw experiment material;
- public telecom benchmark runs;
- selected historical M0/M1 arms;
- original raw run trees used in final audit and claim mapping.

Important contents:

- public telecom raw run folders;
- historical M0/M1 arm runs;
- `workspace/result.json` outputs;
- task/prompt/policy/schema files where available.

Inspection focus:

- public benchmark behavior;
- historical M0/M1 final outputs;
- task contract and result materialization;
- comparison against final audit summaries.

### 3. Report Imperative Supplement

Expected folder:

`omnigent-blackbox-REPORT-IMPERATIVE-supplement-20260912T061643Z`

Primary use:

- report-supporting imperative evidence;
- supplemental artifacts referenced by final writeups.

Inspection focus:

- supporting evidence behind report claims;
- auxiliary inspection material.

### 4. Claim-to-Artifact Index

Expected folder:

`omnigent-blackbox-CLAIM-TO-ARTIFACT-INDEX-20260912T063511Z`

Primary use:

- maps claims to evidence locations.

Inspection focus:

- claim traceability;
- evidence lookup.

### 5. 21-Pair Rawready and Final Audit

Expected folder:

`omnigent-blackbox-21PAIR-RAWREADY-and-FINAL-AUDIT-20260912T064909Z`

Primary use:

- 21-pair evidence preparation;
- rawready status;
- final audit support.

Inspection focus:

- pair-level M0/M1 evidence;
- cost/capability cross-check context.

### 6. Final Clean Audit

Expected folder:

`omnigent-blackbox-FINAL-CLEAN-AUDIT-20260912T065634Z`

Primary use:

- final audit pass/fail status;
- inspection readiness.

Inspection focus:

- claim group readiness;
- audit conclusions.

### 7. Writeup Claim Map

Expected folder:

`omnigent-blackbox-WRITEUP-CLAIM-MAP-FAST-20260912T072702Z`

Primary use:

- maps writeup claims to artifact evidence.

Inspection focus:

- claim-to-file traceability;
- report support.

### 8. 21-Pair Cost Claim Check

Expected folder:

`omnigent-blackbox-21PAIR-COST-CLAIM-CHECK-20260912T073204Z`

Primary use:

- resolves 21-pair cost claims and near/exact cost hits.

Inspection focus:

- cost claim derivation;
- rounded/tolerance-based cost validation.

### 9. Explicit Reproducibility Package

Expected folder:

`omnigent-blackbox-EXPLICIT-REPRODUCIBILITY-20260912T073706Z`

Primary use:

- reproducibility instructions;
- package-level inventory;
- deterministic inspection support.

Inspection focus:

- reproduction instructions;
- inventory;
- hash records.

### 10. Builder Verification Kit

Expected folder:

`omnigent-blackbox-BUILDER-VERIFICATION-KIT-20260912T115752Z`

Also included as release asset:

`release-assets/ARCHIVED_EVIDENCE_VERIFICATION_KIT.zip`

Primary use:

- file-only archived evidence verification.

Inspection focus:

- deterministic PASS/REVIEW verification;
- no provider/model calls;
- no WSL/opencode/gateway dependency.

### 11. Independent Omnigent Replication Contract

Expected folder or zip:

`omnigent-blackbox-LAYER3-24ARM-PORTABLE-CLEAN-20260913T042108Z`

Also included as release asset:

`release-assets/INDEPENDENT_OMNIGENT_REPLICATION_CONTRACT_24ARM.zip`

Primary use:

- portable 24-arm independent M0-vs-MEO live-replication contract.

Inspection focus:

- package-relative plan;
- 12 selected scenarios;
- 24 arms;
- schemas and reference outputs;
- dry-run execution plan.

## Recommended Reviewer Flow

1. Read `OPEN_THIS_FIRST.md`.
2. Run Archived Evidence Verification.
3. Inspect `BLACKBOX_REPRODUCTION_STATUS.md`.
4. Inspect `audits/global-m1-audit-inventory/`.
5. Use this raw artifact index to locate deeper raw evidence families.
6. Use the Independent Omnigent Replication Contract for fresh Omnigent-side execution.
