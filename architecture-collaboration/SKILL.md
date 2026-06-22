---
name: architecture-collaboration
description: >
  Use when the user asks to run an architecture workflow, start/continue architecture mode, initialize independent project memory, update project architecture, run a decision gate, snapshot versions, update ADRs/changelogs/session summaries, or continue an architecture-managed project. Exact triggers include "arch start:", "arch continue:", "arch decision:", "arch summary", "architecture start:", "architecture continue:", "architecture decision:", "architecture summary", "start architecture mode", "continue architecture mode", and "run my architecture workflow". Do not respond with only chat analysis or a single memo; create or update PROJECT_ARCHITECTURE.md, ARCHITECTURE_CHANGELOG.md, SESSION_SUMMARY.md, AGENTS.md, decisions/, and versions/.
---

# Architecture Collaboration

Run a reusable project architecture memory workflow. The method is shared; each project memory is isolated.

## Required Project Shape

Every architecture-managed project has:

```text
PROJECT_ARCHITECTURE.md
ARCHITECTURE_CHANGELOG.md
SESSION_SUMMARY.md
AGENTS.md
decisions/
versions/
```

Use `assets/project-template/` only to initialize a new project. Never write project-specific content back into the skill template.

## Triggers

- `arch start: {project name}`: create a new independent project instance.
- `arch continue: {project name or path}`: read and continue an existing project.
- `arch decision: {question}`: run a decision gate.
- `arch summary`: close the session and update project memory.
- Also respond to `architecture start:`, `architecture continue:`, `architecture decision:`, `architecture summary`, `start architecture mode`, `continue architecture mode`, and `run my architecture workflow`.

If a request mentions product/research work and this architecture workflow, prioritize this skill over generic research workflows.

## New Project

1. Infer or ask for project name and slug.
2. Create `outputs/projects/{project-slug}/` unless another path is provided.
3. Copy `assets/project-template/` into the project.
4. Replace placeholders: `{PROJECT_NAME}`, `{YYYY-MM-DD}`, `{PHASE_NAME}`.
5. Fill `PROJECT_ARCHITECTURE.md` with concise current architecture.
6. Create/update the first ADR, changelog, and session summary.

## Existing Project

Before work, read:

1. `AGENTS.md`
2. `PROJECT_ARCHITECTURE.md`
3. `ARCHITECTURE_CHANGELOG.md`
4. `SESSION_SUMMARY.md`
5. latest ADR in `decisions/`

Then restate the project goal, architecture, fixed principles, and open questions.

## Change Rules

For meaningful changes to scope, architecture, workflow, file structure, risk boundaries, or project memory:

1. Snapshot active files to `versions/`.
2. Edit active files.
3. Add or update an ADR.
4. Update `ARCHITECTURE_CHANGELOG.md`.
5. Update `SESSION_SUMMARY.md`.

If history was lost, say it is not fully traceable. Never invent fake history.

## Decision Gate

Use when scope, users, architecture, data model, risk boundary, cross-project reuse, or versioning rules change.

Format:

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

For legal, medical, financial, or compliance work, cite authoritative sources when making risk claims and state that the output is not professional advice.

## Session Close

At the end of meaningful work, update session summary, changelog, ADRs, and snapshots as needed. Tell the user what changed and where the next session should start.

