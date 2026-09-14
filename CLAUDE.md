# CLAUDE.md — Project Onboarding

This file is read by Claude Code at the start of every session in this repo. Keep it current — it's the fastest way to get a fresh session (cloud or local) working correctly without re-explaining everything.

## What this project is

<!-- Replace with a 2-3 sentence description: what you're building, what broker/data feed/platform, current phase. -->

## Claude Code vs. Project chat

- **Claude Code** (this repo, cloud or local) is for implementation — writing and editing code, running it, committing.
- **Project chat** (the Claude.ai Project this repo is paired with) is for architecture, planning, and building out prompts before you paste them into Code.
- When Code produces something structurally significant (a new pattern, a schema decision, a deviation from these conventions), bring a short summary back to Project chat so the facts/conventions docs stay current.

## Every Code prompt should include

- Explicit merge/hold authorization up front (should Code merge to main on its own, or wait for review?)
- If the task spans both environments, give **two clearly labeled prompts** in the same message — `CLOUD:` and `LOCAL:` — rather than one prompt with an environment note in prose. A cloud session ran a local-only task once because the instruction was buried in text instead of the prompt's own label.
- If a session needs to check "does X already exist," have it run `git fetch --all` first — a cloud session and a local session can each be ahead of the other.

## Cloud vs. Local — when to use which

| | Cloud session | Local session |
|---|---|---|
| Runs where | Anthropic's sandbox | Your own machine |
| Can reach | GitHub, web, this repo | Everything cloud can, **plus** anything only your machine can see: broker terminals (IBKR TWS/Gateway, etc.), local files outside the repo, local databases, hardware |
| Best for | Scaffolding, docs, UI, config, anything that doesn't need your desktop | Broker/order-placement code, anything touching local-only services, final testing against real local state |
| gh CLI / GitHub tooling | Usually available | May not be — plain `git` (checkout main, merge branch, push) works fine for low-risk changes |

See `docs/cloud-local-cheatsheet.html` for the full version of this table with more detail — open it in a browser.

## Chunk sizing

- **Low-risk work** (UI, scaffolding, dependency/config plumbing, docs, read-only data wiring): ask for larger, more comprehensive prompts — move fast.
- **Order-placement / broker-execution-adjacent code**: smaller, carefully-scoped chunks, held for review before merge. This is about correctness risk, not ceremony — get it right before it touches money.
- Paper trading (not chunk size) is the real safety mechanism for anything that places orders. The one hard checkpoint is the future one-time decision to point anything at a live account instead of paper.

## Review and response style

- Reviewable code in stages, with pauses for review on anything non-trivial.
- Plain-English git orchestration (tell me what you're about to merge/push, in words).
- Accuracy over speed — confirm direction before locking in decisions.
- Concise responses: no preamble, no restating the question, direct answer first.
- Don't suggest "good stopping points" — just report results and give the next prompt or ask what's next.

## Git and merge conventions

- Local sessions without `gh` CLI access can still do low-risk merges with plain git: `checkout main`, `merge <branch>`, `push`.
- Default: non-order-placement/pipeline changes can auto-merge. Order-placement and pipeline changes should be held for explicit review — confirm this split still holds as the project grows.

## Tools and resources

<!-- Fill in as you set these up -->
- Broker/execution:
- Backtesting:
- Market data:
- Database:
- Backend:
- Frontend:
- Repo: (private) — canonical local path:
- Cross-session sharing: Google Drive MCP connector (see `docs/cloud-local-cheatsheet.html`) — same Google account connected in both cloud and local sessions
- Key shared files: `docs/latest-session-summary.md` on `main` (overwritten after every session, not appended) — the fastest way for a new session to catch up without you re-explaining
