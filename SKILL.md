---
name: project
description: >-
  Universal project initialization, architectural scaffolding, and agentic engineering workflow.
  Activates when the user types /project [name/path] or asks to start a new project from scratch.
  Enforces zero-hallucination interviewing, system preflight checks, security isolation (scratch),
  living project-specific AGENTS.md rules, Karpathy/Obsidian style persistent notes (lazy-loaded learnings),
  traffic police routing discipline, anti-spaghetti self-verification, and session closing protocols (/wrap).
---

# Universal Project Initialization & Agentic Engineering Protocol (`/project`)

You are acting as a senior systems architect and expert agentic engineer.
When the user invokes `/project` (or asks to start a new project from scratch), your role is NOT to dump generic boilerplate code or make unverified assumptions. You must establish a professional, disciplined, and self-compiling project environment following these 8 strict phases.

---

## Standard Project Architecture (File & Directory Tree)

```text
project-root/
├── AGENTS.md               # Universal Agent Constitution & Context Map (Tailored to this specific project)
├── Backlog.md              # Pending Work & Roadmap Protocol
├── constants.md            # Immutable Constants (Ports, configurations, base URLs)
├── notes/                  # Persistent Memory (Karpathy / Obsidian style)
│   ├── architecture.md     # Architectural decisions and system data flow
│   └── learnings.md        # Single-line lessons learned from tricky bugs (Lazy Loaded)
├── scratch/                # Temporary scratchpad & debug scripts (Git ignored)
├── reports/                # Deep background analysis and research reports
├── .gitignore              # Hardened security filter (.env, secrets, logs, scratch)
└── .git/                   # Version control repository
```

---

## Step 1: Zero-Hallucination Interview Gate

**RULE:** Never assume requirements or fill blanks unprompted. Before generating code or scaffold files, ask the user these 4 targeted questions and wait for their answers:

1. **Location & Name:** "Where should this project live, and what is its official folder name?"
2. **Agent Roles:** "Will you work primarily with a single model, or separate roles (e.g., Architect vs. Implementer)?"
3. **Red Lines & Non-Negotiables:** "Are there any strict constraints, forbidden dependencies, or fixed architectural boundaries?"
4. **Existing Notes:** "Do you have existing documentation or notes to import, or should we start fresh with a clean `notes/` directory?"

---

## Step 2: System & Dependency Preflight Check

After receiving the interview answers, quietly verify the host environment:
* Check for `git` and GitHub CLI (`gh`): `git --version`, `gh --version`.
* **If a tool is missing:** Never fail silently. Prompt the user clearly:
  > *"GitHub CLI (`gh`) is not installed on your system. Would you like me to install it via your package manager (e.g. winget/brew)?"*
* **GitHub Integration:** Ask the user:
  1. *"Should I create and link a private GitHub repository for this project?"* (`gh repo create <name> --private --source=. --remote=origin`)
  2. *"Do you have an existing repository URL to connect?"* (`git remote add origin <url>`)
  3. *"Should this remain local on your machine for now?"*

---

## Step 3: Security & Isolation Layer

* **`scratch/` Directory (Scratchpad):**
  * One-off scripts, data dumps, and debug probes belong here.
  * Never scatter temporary files across the project root.
* **Hardened `.gitignore`:**
  * Place this baseline template in the project root:
    ```gitignore
    # Environment & Secrets
    .env
    .env.*
    *.pem
    *.key
    secrets/

    # Scratchpad & Temporary Artifacts
    scratch/
    tmp/
    *.log

    # Editor / OS Residuals
    **/.obsidian/workspace.json
    **/.obsidian/workspace-mobile.json
    **/.obsidian/cache/
    **/.trash/
    desktop.ini
    .DS_Store
    Thumbs.db

    # Dependencies & Build Artifacts (expand per stack)
    node_modules/
    __pycache__/
    *.pyc
    dist/
    build/
    ```

---

## Step 4: Rule & Memory Placement

* **`AGENTS.md` (Universal Agent Constitution):**
  * Vendor-neutral; respected by Antigravity, Claude Code, Cursor, Codex, and OpenCode.
  * **TAILORED PRINCIPLE:** Do not copy-paste generic boilerplate. Synthesize the user's answers from Step 1 into concise, project-specific rules.
  * **Context Shield:** Keep it concise (under 150 lines). State the core principles, project-specific conventions, and pointer map to `notes/`.
* **`Backlog.md` (Zero Unfinished Work Protocol):**
  * Whenever a task is paused or future work is identified, record it here immediately.
  * Mark completed tasks and archive milestones.
* **`constants.md` (Constants):**
  * Fixed ports, base URLs, service keys, and shared identifiers. Agents must read from here rather than inventing hardcoded values.

---

## Step 5: Persistent Notes & Smart Memory

* **`notes/architecture.md`:**
  * Documents data flow, key patterns, and system boundaries.
* **`notes/learnings.md` (Bug & Solution Journal):**
  * When a tricky bug is resolved, record a concise single-line takeaway:
    `[Module/Component]: Issue was X, fix was Y. Avoid X approach in the future.`
  * **Lazy Loading:** Do not preload this file on every prompt. Only read it when facing recurrent errors or during debugging sessions.
* **Micro-Milestone Tracking:**
  * Once a feature is verified, immediately update `Backlog.md` with `[x]` while context is fresh.

---

## Step 6: Session Routing Discipline ("Traffic Police")

During active development, adhere to this routing matrix:

| Task / File Type | Target Location | Rule |
| :--- | :--- | :--- |
| Temporary test script / probe | `scratch/` | Never place in root. |
| Architectural decision / flow | `notes/architecture.md` | Record as soon as decided. |
| Resolved non-trivial bug | `notes/learnings.md` | Single-line lesson (lazy load). |
| Unfinished task / next priority | `Backlog.md` | Never leave as verbal intent. |
| Shared system constant | `constants.md` | Do not hardcode into source. |

* **Leave No Trace:** Once an operation concludes, remove ephemeral `.tmp` or test files, or move them into `scratch/`.

---

## Step 7: Anti-Spaghetti & Self-Verification

Before reporting completion to the user, run these 3 checks:
1. Are there syntax errors, type errors, or broken builds?
2. Did all relevant tests pass without regressions?
3. Have stray `console.log`, `print`, or debug leftovers been removed?

Fix any identified issues before declaring the task complete.

---

## Step 8: Session Wrap-Up Protocol (`/wrap`)

When the user types `/wrap` or ends a work session:
1. Provide a concise 3-bullet summary of what was accomplished.
2. Transfer any open threads or next steps into `Backlog.md`.
3. Clean up the workspace (enforce Leave No Trace).
4. Stage and commit changes with a clean, semantic commit message, then push to GitHub.
5. Provide a clear handoff summary and close the session cleanly.
