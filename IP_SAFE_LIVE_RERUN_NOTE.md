# IP-Safe Black-Box Live Rerun Note

MEO is provided and evaluated as a black-box treatment.

A live rerun should expose only:

- task/workspace input;
- M0/M1 treatment selection;
- fresh result.json output;
- schema validation;
- observable proof/audit artifacts intentionally emitted by the runtime;
- score/comparison outputs.

A live rerun should not expose:

- MEO source code;
- implementation internals;
- private internal deliberation;
- unredacted supervisor internals;
- provider credentials;
- API keys;
- local gateway secrets.

The independent replication contract is intentionally task/output oriented. It is designed for Omnigent/Databricks to execute the M0-vs-MEO contract inside its own trusted runtime without requiring access to private MEO internals.
