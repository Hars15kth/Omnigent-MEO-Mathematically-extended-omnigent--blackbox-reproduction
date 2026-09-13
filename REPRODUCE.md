# MEO Black-Box Reproduction Package

This package provides explicit inspection and reproduction scaffolding for the packaged MEO-vs-Omnigent evidence while keeping MEO itself black-box.

## What This Verifies

This handoff supports two separate reviewer workflows:

1. Archived evidence verification.
   Reviewers can verify that the historical MEO-vs-M0 evidence exists, is packaged coherently, has hashes/audits/claim maps, and supports the reported claims without making provider calls.

2. Operational MEO treatment inspection.
   Reviewers can inspect archived M1/MEO outputs, treatment evidence, audit artifacts, raw artifact indexes, claim maps, score derivations, and reference outputs to see how MEO-treated arms differed from comparator arms.

3. Independent Omnigent-side replication.
   Reviewers can use the portable 24-arm A/B contract to rerun treatment A and treatment B inside their own trusted Omnigent execution environment.

4. Black-box boundary preservation.
   The package exposes task contracts, prompts/tasks, schemas, outputs, audits, score derivations, and replication materials. It does not expose MEO source code, private internals, private internal deliberation, provider credentials, or local launcher secrets.

## Run

There are two workflows.

### Archived Evidence Verification

Download `ARCHIVED_EVIDENCE_VERIFICATION_KIT.zip` from the GitHub release assets.

Inside the extracted package, start with:

```powershell
.\VERIFY_EVIDENCE.ps1
