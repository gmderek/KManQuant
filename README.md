# Quant Project Starter

Starting-point repo for running a quant/trading project with Claude Code (cloud + local) and a paired Claude.ai Project for architecture/planning.

## What's in here

- `CLAUDE.md` — read by Claude Code at the start of every session. Onboarding, conventions, working style. Fill in the placeholders as your setup solidifies.
- `docs/project_plan.mermaid` — a living project-plan diagram (milestones, dependencies, open questions). Renders automatically on GitHub, and Claude can read/update it each session.
- `docs/latest-session-summary.md` — overwritten (not appended) at the end of every session so the next session — cloud or local — can catch up in seconds.
- `docs/cloud-local-cheatsheet.html` — open in a browser. Explains what a cloud Claude Code session can and can't reach vs. a local one, and how to split work between them.

## First-time setup

1. Clone this repo.
2. Create a matching Claude.ai Project (Pro plan or above) for architecture/planning chat — separate from Code itself.
3. Upload `CLAUDE.md`, `docs/project_plan.mermaid`, and any facts/conventions docs you build up to that Project's knowledge.
4. Fill in the placeholders in `CLAUDE.md` (tools, stack, repo path).
5. Connect the Google Drive MCP connector in both your cloud and local Claude Code setups if you want session summaries or facts docs shared automatically (see the cheat sheet for why this matters and how to set it up).
6. Start building — Project chat for planning, Code for implementation.
