# Universal Project Scaffolding & Session Discipline (`/project` & `/wrap`)

A pair of lightweight, disciplined workflow skills for AI coding agents (Antigravity, Claude Code, Cursor, Codex).

This package provides two dedicated commands:
* **`/project` (`project.md`):** Scaffolds clean, disciplined project architecture, enforces interview preflight checks, and generates living `AGENTS.md` guidelines.
* **`/wrap` (`wrap.md`):** Closes development sessions cleanly by verifying builds, synchronizing the backlog, cleaning temporary files, and committing/pushing to Git.

---

## What Is Included

| Skill / Command | File | Primary Responsibility |
| :--- | :--- | :--- |
| **`/project`** | `project.md` | Zero-hallucination interview, environment preflight check, directory structure, project-tailored `AGENTS.md`, persistent notes, and scratchpad isolation. |
| **`/wrap`** | `wrap.md` | Pre-finish health verification, workspace cleanup ("Leave No Trace"), `Backlog.md` updates, semantic Git commit & push, and handoff summary. |

---

## Standard Scaffolding Architecture

When `/project` is triggered, it establishes this standardized layout:

```text
project-root/
├── AGENTS.md           # Living agent constitution and context map
├── Backlog.md          # Pending tasks and milestone roadmap
├── constants.md        # Shared constants (ports, URLs, configs)
├── notes/
│   ├── architecture.md # Architectural decisions and data flow
│   └── learnings.md    # Single-line bug lessons (lazy loaded)
├── scratch/            # Ignored scratchpad for throwaway test scripts
├── reports/            # Deep-dive research and analysis reports
└── .gitignore          # Baseline security and cleanup filter
```

---

## Installation

### 1. Antigravity CLI & Desktop
To have both `/project` and `/wrap` available in your `/` command menu:

Clone into your workspace skills directory:
```bash
git clone https://github.com/Utku4836/project-skill.git .agent/skills/project-suite
```
Or install globally for all projects:
```bash
git clone https://github.com/Utku4836/project-skill.git ~/.gemini/antigravity-cli/skills/project-suite
```

*(Antigravity automatically discovers both `skills/project/SKILL.md` and `skills/wrap/SKILL.md` inside this repo).*

### 2. Claude Code & Codex
Provide `project.md` or `wrap.md` in your prompts or include them in your instructions:
```text
Read project.md to initialize my new project.
```
```text
Read wrap.md and perform the session wrap-up protocol.
```

### 3. Cursor & Other AI Editors
Copy the contents of `project.md` and `wrap.md` into your `.cursorrules` or system prompt.

---

## Usage

### Start a Project
```text
/project [project-name]
```

### Wrap Up a Session
```text
/wrap
```

---

## License

MIT
