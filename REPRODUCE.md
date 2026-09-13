# MEO Black-Box Reproduction Package

This package provides explicit inspection and reproduction scaffolding for the packaged MEO-vs-Omnigent evidence.

## What This Verifies

1. Packaged raw evidence exists.
2. Claim groups have raw result files, score/summary files, inputs or scanner artifacts, and logs/transcripts.
3. Package files can be hashed for integrity.
4. Selected rerun commands can be reconstructed in dry-run form.

## Run

From WSL:

```bash
cd THIS_PACKAGE
python3 scripts/inspect_evidence.py
python3 scripts/recompute_claim_counts.py
python3 scripts/verify_package_hashes.py
bash scripts/rerun_selected_blackbox_arm_dryrun.sh

The rerun script is intentionally dry-run only. It does not call paid providers.
