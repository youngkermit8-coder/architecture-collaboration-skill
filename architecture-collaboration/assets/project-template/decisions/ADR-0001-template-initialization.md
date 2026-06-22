# ADR-0001: Initialize Architecture Collaboration Project

Status: template placeholder  
Date: {YYYY-MM-DD}  
Supersedes: none  
Superseded by: none

## Context

{Explain why this project needs architecture collaboration mode.}

## Decision

Initialize an independent architecture collaboration project instance for `{PROJECT_NAME}`.

The project instance includes:

- `PROJECT_ARCHITECTURE.md`
- `ARCHITECTURE_CHANGELOG.md`
- `SESSION_SUMMARY.md`
- `AGENTS.md`
- `decisions/`
- `versions/`

## Rationale

- {Reason 1}
- {Reason 2}
- {Reason 3}

## Consequences

- This project has independent project memory.
- This project's ADRs, snapshots, and session summaries must not be mixed with other projects.
- Meaningful future changes must be snapshotted before active files are updated.

