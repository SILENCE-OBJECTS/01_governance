# 01_governance

Public governance tooling for [SILENCE-OBJECTS](https://github.com/SILENCE-OBJECTS).

```
Status: PUBLIC
Scope: governance signals and tooling only
Not included: scoring, individual profiling, raw telemetry, enterprise logic (03_ee)
```

## Purpose

This repository holds the **public** layer of the SILENCE-OBJECTS governance system:
machine-readable signals and helper tooling that other repositories in the organisation
can consume without access to any private surface.

Records (submissions, correspondence, decisions, evidence) live in
[silence-governance-records](https://github.com/SILENCE-OBJECTS/silence-governance-records).
Open-core contracts and gates live in
[silence-longevity-modules](https://github.com/SILENCE-OBJECTS/silence-longevity-modules).

## Layout

| Path | Role |
| --- | --- |
| `signals/` | Versioned governance signals. One file per signal, filename = `<name>.v<N>`, content = version marker. |
| `signals/continuity.v1` | Continuity signal — the governance chain is unbroken. |
| `signals/idle.v1` | Idle signal — no pending governance action. |

Signals are immutable once published. A change in semantics produces a new file
(`<name>.v<N+1>`), never an edit of the existing one.

## Rules

- Public by design. Nothing in this repository may reference private repositories,
  enterprise logic, scoring, or raw data streams.
- No personal data. Records with parties, names or contact details belong in the
  records repository under its publication gate.
- SSoT is the versioned file in this repository, not any external dashboard.

## Related

- [.github](https://github.com/SILENCE-OBJECTS/.github) — organisation profile and canonical surface
- [silence-engine](https://github.com/SILENCE-OBJECTS/silence-engine) — deterministic scheduler
- [patternlens-legal](https://github.com/SILENCE-OBJECTS/patternlens-legal) — public legal surface

## License

MIT — see [LICENSE](LICENSE).
