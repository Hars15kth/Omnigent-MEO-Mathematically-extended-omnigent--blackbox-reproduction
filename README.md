# Mathematically Extended Omnigent reproduction

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

# What MEO Is and What It Changes in Omnigent

**Mathematically Extended Omnigent (MEO)** is a mathematical intelligence layer operating inside Omnigent's meta-orchestration and supervisor boundary.

Its design is built off of frameworks from **algebraic geometry, category theory, sheaf theory, cohomology, representation theory, stochastic control, tensor networks, and commutative reconciliation**.

Databricks defines Omnigent as a meta-harness for composing, controlling, and sharing agents across heterogeneous harnesses and models while maintaining common tools, policies, sessions, sandboxing, collaboration, and execution control.

**MEO intervenes at this same meta-harness altitude.**

It does not replace the underlying model or agent harness. It changes how the Omnigent supervisor represents and reasons about its own evolving execution.

Under MEO, **memory, routing, delegation, policy, evidence, recovery, collaboration, conflict resolution, and completion are treated as connected views of one persistent supervisory state**.

This allows Omnigent to reason explicitly about questions such as:

- What obligations remain unresolved?
- What evidence supports the current state?
- Which state is authoritative when sessions, traces, or artifacts conflict?
- Which actions remain admissible under policy, cost, risk, and capability constraints?
- What state must survive when execution crosses agents, harnesses, tools, or sessions?
- When a direct route fails, what governed fallback preserves the objective?
- After interruption, what must survive for execution to resume correctly?
- Has the task merely been reasoned about, or has the complete execution contract actually been satisfied?
- Is there sufficient evidence to stop and emit the authoritative result?

The intervention therefore operates at the level of **supervisor intelligence**, rather than answer generation.

## What Changes Operationally

MEO gives the supervisor structured control over difficult execution states.

When a tool or action path fails, MEO can preserve the unresolved objective, select a governed fallback, and carry remaining obligations forward.

When execution is interrupted, MEO can preserve the state required for managed resume.

When sessions, traces, or artifacts disagree, MEO can represent the conflict, determine authoritative state, and carry the repaired state forward.

When several execution routes are available, MEO can reason across policy, cost, risk, evidence, and execution constraints.

When evidence remains incomplete, MEO preserves the outstanding obligation rather than allowing it to disappear as execution continues.

When an agent appears to have solved a task, MEO distinguishes successful reasoning from successful **execution finalization**: the evidence, policy state, outstanding obligations, and required machine-valid artifact must actually close.

This is why MEO's strongest effects appear on exactly the difficult surfaces of a meta-harness: **routing, recovery, state transport, managed resume, conflict reconciliation, policy handling, evidence binding, audit finalization, governed fallback, and artifact materialization.**

## Experimental Signal

MEO has been evaluated against baseline Omnigent across multiple controlled regimes, including clean validation studies, hard full-contract studies, meta-harness stress tasks, scanner/tool failure modes, component ablations, and the **public τ² Telecom benchmark**.

The broader Omnigent-native experiments show the other half of the capability change: difficult supervisor behaviors including **governed tool-failure recovery, managed workflow resume, shared-session conflict reconciliation, budgeted escalation, policy/cost route selection, and audit-trace finalization** become substantially stronger under MEO.

Component ablations provide additional causal evidence. Removing specific MEO controls causes large degradation on corresponding hard orchestration tasks, showing that specific supervisory mechanisms are actively carrying the observed capability.

The experimental picture is aimed at the rigorous validation of **multi-regime capability change at Omnigent's supervisor layer**.

## What Reviewers Can Inspect

This repository exposes substantially more than aggregate result tables while keeping MEO's internal mathematical implementation strictly black-boxed.

Across the experimental evidence, reviewers can inspect materials including:

- task definitions, prompts, policies, workflow materials, tool contracts, schemas, and workspace templates;
- raw M0 and M1 result artifacts;
- execution logs and trace-like artifacts;
- MEO treatment/activation markers and manipulation proofs;
- scanner/tool and evidence/provenance artifacts where retained;
- final-state and failure artifacts;
- scoring and score-derivation files;
- grading and verification materials;
- claim-to-artifact maps and cost checks;
- experiment and selected-arm manifests;
- package inventories and integrity audits;
- SHA-256 manifests;
- archived reference outputs.

The broader historical M1 inventory currently identifies **655 M1 outputs, 612 with manipulation-proof evidence, 655 with trace-like files, 182 with explicit MEO markers, 50 with retained scanner artifacts, and 155 score-derivation files**.

## The Capability Change

Baseline Omnigent provides the substrate for heterogeneous agent execution: agents, harnesses, models, tools, policies, sessions, collaboration, sandboxing, and meta-harness control.

MEO adds structured intelligence over the evolving state of that substrate.

It gives the supervisor a coherent way to preserve obligations, bind evidence, arbitrate conflicting state, recover from failed paths, select governed routes, transport state across execution boundaries, and determine when the complete execution contract has actually been satisfied.

**MEO makes Omnigent substantially more capable at being a supervisor.**

The black-box reproduction handoff allows anyone to evaluate that statement directly:

1. understand the intervention;
2. inspect MEO's archived operational treatment evidence;
3. deterministically verify the historical experimental evidence;
4. keep MEO's internal mechanism black-boxed; and
5. run the portable 24-arm A/B replication contract inside an Omnigent environment they control.

**Understand the intervention → inspect the treatment behavior → verify the evidence → independently replicate it in Omnigent.**




