# Architecture Collaboration Skill

A reusable project memory workflow for Codex.

Long projects do not fail only because the idea is weak. They often fail because the architecture drifts, decisions disappear into chat history, and the next session starts by rediscovering what was already clear.

This skill gives Codex a lightweight operating system for long-running work: one concise architecture file, one changelog, one session summary, ADRs for decisions, and snapshots for traceability.

## Why Use It

- Keep the core architecture visible while the project evolves.
- Continue work across sessions without losing the original intent.
- Turn vague planning chats into durable project memory.
- Preserve decision history before changing direction.
- Separate reusable workflow rules from project-specific content.

## Quick Start

```bash
python ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py --repo youngkermit8-coder/architecture-collaboration-skill --path architecture-collaboration
```

Restart Codex, then start with:

```text
arch start: your project name
```

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
python ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py --repo youngkermit8-coder/architecture-collaboration-skill --path architecture-collaboration
```

You can also install from a GitHub tree URL:

```bash
python ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py --url https://github.com/youngkermit8-coder/architecture-collaboration-skill/tree/main/architecture-collaboration
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

Use short English trigger commands for the most reliable behavior:

```text
arch start: {project name}
arch continue: {project name or project path}
arch update: {change}
arch review: {project name or project path}
arch checkpoint
arch decision: {decision question}
arch summary
```

Longer supported alternatives:

```text
architecture start: {project name}
architecture continue: {project name or project path}
architecture update: {change}
architecture review: {project name or project path}
architecture decision: {decision question}
architecture summary
start architecture mode
continue architecture mode
run my architecture workflow
project memory mode
core architecture workflow
```

Natural-language requests should also trigger the skill when they mean:

```text
start a project memory workflow
continue a long-running project with architecture memory
update the core architecture
review architecture consistency
create a project checkpoint
snapshot the current architecture before changing direction
record this as an ADR
summarize this session and preserve decisions
compare the current architecture with an earlier version
recover or inspect project history
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
