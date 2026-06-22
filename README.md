# Architecture Collaboration Skill

Reusable project memory workflow for Codex. It keeps long-running projects traceable with a concise architecture file, changelog, session summary, ADRs, and version snapshots.

## What This Skill Does

- Starts an independent project memory folder.
- Maintains `PROJECT_ARCHITECTURE.md` as the concise source of truth.
- Records meaningful changes in `ARCHITECTURE_CHANGELOG.md`.
- Stores session handoff notes in `SESSION_SUMMARY.md`.
- Captures decisions in `decisions/` as ADR files.
- Preserves historical snapshots in `versions/`.

## Repository Layout

```text
architecture-collaboration-skill/
├── README.md
└── architecture-collaboration/
    ├── SKILL.md
    ├── agents/
    │   └── openai.yaml
    └── assets/
        └── project-template/
```

Only `architecture-collaboration/` is the actual Codex Skill folder. The repository-level `README.md` is documentation for GitHub users.

## Install

### Install From GitHub

After uploading this repository to GitHub, install the skill by pointing Codex's skill installer at the skill subdirectory:

```bash
python ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py --repo <owner>/<repo> --path architecture-collaboration
```

You can also install from a GitHub tree URL:

```bash
python ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py --url https://github.com/<owner>/<repo>/tree/main/architecture-collaboration
```

Restart Codex after installation so the new skill list is refreshed.

### Manual Install

Copy the `architecture-collaboration/` folder into your Codex skills directory:

```text
~/.codex/skills/architecture-collaboration
```

On Windows, the equivalent path is usually:

```text
C:\Users\<USER>\.codex\skills\architecture-collaboration
```

Restart Codex after manual installation too.

## Recommended Triggers

Use short English trigger commands:

```text
arch start: {project name}
arch continue: {project name or project path}
arch decision: {decision question}
arch summary
```

Longer supported alternatives:

```text
architecture start: {project name}
architecture continue: {project name or project path}
architecture decision: {decision question}
architecture summary
start architecture mode
continue architecture mode
run my architecture workflow
```

## Expected Project Output

Each architecture-managed project should contain:

```text
PROJECT_ARCHITECTURE.md
ARCHITECTURE_CHANGELOG.md
SESSION_SUMMARY.md
AGENTS.md
decisions/
versions/
```

## Validation

Validate the skill with Codex's skill creator script:

```bash
python ~/.codex/skills/.system/skill-creator/scripts/quick_validate.py ~/.codex/skills/architecture-collaboration
```

The expected result is:

```text
Skill is valid!
```

## Notes

- The skill package itself is English-only.
- Project content can be written in any language after the skill starts.
- If the skill does not trigger in an already-open session, restart or reload Codex and use one of the exact trigger commands above.
- Keep project-specific content inside project folders. Do not write project-specific content back into `architecture-collaboration/assets/project-template/`.
