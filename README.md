# Project & Wrap Skills

A set of workflow guidelines and skills for AI coding assistants (Antigravity, Claude Code, Cursor, Codex).

Designed to help agents start projects cleanly, maintain a structured workspace, and wrap up development sessions with proper Git commits and backlog tracking.

## Overview

- **`/project` (`skills/project/Project-Skill.md`):** Protocol for scaffolding new projects, setting up architectural notes, living agent guidelines (`AGENTS.md`), and workspace boundaries without hallucinations.
- **`/wrap` (`skills/wrap/Wrap.md`):** Protocol for ending a session, cleaning up temporary files, syncing pending tasks, and pushing clean commits.

## Project Structure

When initialized with `/project`, it establishes this standardized layout:

```text
project-root/
├── AGENTS.md           # Living agent constitution and context map
├── Backlog.md          # Pending tasks and milestone roadmap
├── constants.md        # Shared constants (ports, URLs, configs)
├── notes/
│   ├── architecture.md # Architectural decisions and data flow
│   └── learnings.md    # Single-line bug fixes and lessons (lazy loaded)
├── scratch/            # Ignored scratchpad for temporary test scripts
├── reports/            # Deep-dive research and analysis reports
└── .gitignore          # Baseline security and cleanup filter
```

## Usage

You can use these files directly in your agent environment:

- **Skills / Workflows:** Place this repository or the individual files into your agent's skills folder (e.g. `.agent/skills/` or global config).
- **Custom Instructions:** Reference or copy the skill files into your project rules (`.cursorrules`, `AGENTS.md`, or prompt).

Trigger the protocols when needed:
- `/project` — Initialize a new project
- `/wrap` — Conclude and commit the current session

## License

MIT License. See [LICENSE](LICENSE) for details.
