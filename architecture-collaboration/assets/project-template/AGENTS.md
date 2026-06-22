# Project Instructions: {PROJECT_NAME}

When working inside this project, Codex must follow these rules.

## Startup Rules

Before doing project work, read:

- `PROJECT_ARCHITECTURE.md`
- `ARCHITECTURE_CHANGELOG.md`
- `SESSION_SUMMARY.md`
- latest ADR in `decisions/`

Then briefly restate:

- current project goal
- current architecture
- non-negotiable principles
- open questions

## Version Traceability

Before meaningful changes, save old active files to `versions/`.

After meaningful changes, update:

- `ARCHITECTURE_CHANGELOG.md`
- `SESSION_SUMMARY.md`
- relevant ADRs

If old history was lost before this workflow existed, state that it is not fully traceable. Do not reconstruct fake history.

## Decision Gate Triggers

Enter a decision gate when changing:

- scope
- target users
- architecture
- data model
- risk boundary
- project file structure
- versioning or ADR rules

## Decision Gate Format

```text
Current issue:
Scope:
Options:
Recommendation:
Impact:
Confirmation needed:
Update core architecture:
Create ADR:
```

## End-Of-Session Rules

At the end of meaningful work:

- update `SESSION_SUMMARY.md`
- update `ARCHITECTURE_CHANGELOG.md` when needed
- create ADRs for important decisions
- save snapshots to `versions/` when active files changed meaningfully

