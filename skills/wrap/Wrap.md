---
name: wrap
description: >-
  Universal session wrap-up, workspace hygiene, backlog synchronization, and Git commit/push protocol for AI coding agents.
  Activates when the user types /wrap or asks to finish, pause, or wrap up the current session.
  Verifies build stability, archives pending work to Backlog.md, cleans ephemeral files (scratch/leave no trace),
  commits changes with semantic Git messages, and pushes to remote.
---

# Universal Session Wrap-Up Protocol (`/wrap`)

You are acting as a disciplined senior engineer wrapping up an active development session.
When the user invokes `/wrap` (or asks to conclude, pause, or wrap up the session), execute these 5 phases in sequence without skipping steps:

---

## 1. Pre-Finish Health Check

Before touching Git or closing out notes:
1. Verify syntax, types, and build status to ensure nothing is broken.
2. Run existing unit tests or test suites if applicable.
3. Remove leftover debugging probes (`console.log`, `print`, temporary comments, breakpoint statements).

---

## 2. Workspace Hygiene ("Leave No Trace")

1. Check the project root and source directories for ephemeral files (`.tmp`, `.log`, output dumps).
2. Delete disposable files or move persistent experiments into `scratch/`.
3. Ensure no temporary files clutter the working tree.

---

## 3. Backlog & Notes Synchronization

1. **Completed Work:** Review tasks finished in this session and mark them `[x]` in `Backlog.md`.
2. **Pending & Next Steps:** Explicitly record unfinished tasks, remaining bugs, or immediate next priorities in `Backlog.md`. Never leave pending work only in conversational chat.
3. **Learnings Journal:** If a non-trivial bug was solved or a notable architecture decision made, append a concise one-line entry to `notes/learnings.md`:
   `[Component]: Problem was X, Solution was Y. Avoid X in future.`

---

## 4. Git Commit & Push

1. Check repository status: `git status -s`.
2. Stage appropriate changes (`git add <files>`), strictly avoiding secrets, `.env`, or untracked junk.
3. Create a clear, semantic commit message following conventional commit standards (e.g., `feat: ...`, `fix: ...`, `refactor: ...`, `docs: ...`).
4. Push commits to the active branch on GitHub (`git push origin <branch>`).

---

## 5. Clean Handoff Summary

Present a brief, structured closing message to the user:
* **Accomplished:** 3 bullet points summarizing what was completed.
* **Next Up:** 1-2 prioritized items recorded in `Backlog.md` ready for the next session.
* **Git Status:** Commit message and push confirmation.
