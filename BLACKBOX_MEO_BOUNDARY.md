# Black-Box MEO Boundary

This handoff treats MEO as an explicitly black-box intervention.

## What Is Exposed

The package exposes observable evidence:

- task inputs;
- prompts and policies where packaged;
- schemas and tool/workspace materials;
- M0 outputs;
- M1/MEO outputs;
- treatment markers where archived;
- manipulation/proof records where archived;
- scanner/evidence artifacts where archived;
- trace-like files and logs where archived;
- final-state changes;
- score/audit derivation files;
- claim-to-artifact mappings;
- deterministic verification hashes;
- selected independent replication plans.

These are sufficient for an Omnigent/Databricks reviewer to inspect how MEO changed behavior operationally.

## What Is Not Exposed

The package does not expose private private internal deliberation, proprietary internal implementation details, or private internal deliberation.

Reviewers should evaluate MEO as a black-box control-layer treatment through:

```text
same task contract
same M0/M1 treatment distinction
observable outputs
observable treatment/proof/audit artifacts
score/audit derivation
fresh replication in an Omnigent-controlled runtime
Correct Interpretation

A reviewer can ask:

Did M1/MEO produce different and better final artifacts?
Did M1/MEO recover where M0 failed?
Did M1/MEO preserve evidence, trace, policy, or finalization constraints better?
Did M1/MEO produce auditable final-state improvements?
Does the advantage persist when Omnigent/Databricks reruns the selected contract in its own runtime?

A reviewer should not need access to MEO private internals to answer these questions.

Live Replication Boundary

Fresh live replication should be performed by Omnigent/Databricks using its own trusted runtime, provider/model route, credentials, and instrumentation.

The package does not require reproducing Harsh's historical local launcher, WSL setup, Fireworks key, opencode route, or loopback gateway.

Fresh numerical deltas may vary with runtime/model/provider conditions. The replication target is persistence of the M0-vs-MEO behavioral advantage under the same experimental contract.

