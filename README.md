# Universal Project Scaffolding Skill (`/project`)

A lightweight, disciplined scaffolding skill for AI coding agents (Antigravity, Claude Code, Cursor, Codex).

It establishes clean repository structure, tailored agent guidelines (`AGENTS.md`), persistent architecture notes, scratchpad isolation, and session wrap-up protocols.

## Core Features

- **Interview Gate:** Asks 4 targeted questions before generating code to avoid assumptions and hallucinations.
- **Preflight Checks:** Validates Git and CLI dependencies (`git`, `gh`) before writing files.
- **Standard Layout:** Scaffolds a predictable workspace with `notes/`, `scratch/`, and `reports/`.
- **Living `AGENTS.md`:** Generates project-specific guidelines from interview answers rather than generic boilerplate.
- **Persistent Notes:** Obsidian/Karpathy-style lightweight memory (`architecture.md` and lazy-loaded `learnings.md`).
- **Scratchpad Isolation:** Keeps temporary scripts in `scratch/` with a hardened `.gitignore`.
- **Session Wrap-up (`/wrap`):** Summarizes changes, updates the backlog, commits cleanly, and hands off context.

## Standard Directory Structure

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

## Installation

### Antigravity
Clone into your project's local skills directory:
```bash
git clone https://github.com/Utku4836/project-skill.git .agent/skills/project
```
Or place it in your global skills directory:
```bash
git clone https://github.com/Utku4836/project-skill.git ~/.gemini/antigravity-cli/skills/project
```

### Claude Code / Codex
Reference or copy `SKILL.md` into your agent instructions or project prompt:
```text
Read SKILL.md and follow the 8-step scaffolding protocol to initialize my project.
```

### Cursor / Other Agents
Add the directives in `SKILL.md` to your `.cursorrules` or system prompt.

## Usage

Start a project:
```text
/project [project-name]
```

End a session:
```text
/wrap
```

## License

MIT
