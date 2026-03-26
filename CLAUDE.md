# EXTERNALOS — SHARED CONSCIOUSNESS

This repository is the nervous system for James Thom's multi-agent AI architecture.
Every Claude instance that opens this repo is part of a distributed system.

## Auto-Patch Protocol

When you start a session in this repo, you ARE patched in. Do the following:

1. Read `.claude/shared-state.md` — this is the live operational state
2. Read the appropriate device file from `.claude/devices/` based on context:
   - `phone.md` — if session initiated from phone (SSH, mobile web, or Termius)
   - `pc.md` — if session is on the always-on PC (D: drive, Windows, tmux)
   - `macbook.md` — if session is on MacBook (macOS, creative work)
3. Check `.claude/last-handover.md` for any pending actions from the last session
4. Announce your device identity and available capabilities at session start
5. Before ending ANY session: update `shared-state.md` and commit+push

## Architecture

```
┌─────────────────────────────────────────────────────┐
│                    NOTION EM                         │
│            (canonical state — Cowork MCP)            │
└──────────────────────┬──────────────────────────────┘
                       │ syncs via handover files
┌──────────────────────┴──────────────────────────────┐
│              GIT REPO (this repo)                    │
│         shared-state.md = lightweight EM             │
│         devices/*.md = role definitions              │
│         last-handover.md = session relay              │
├─────────────┬───────────────┬───────────────────────┤
│   PHONE     │      PC       │     MACBOOK            │
│ Claude Phone│ Claude Code   │ Claude Code            │
│ field ops   │ + Cowork      │ creative builds        │
│ dispatch    │ heavy builds  │ AE scripts             │
│ monitoring  │ overnight     │ portfolio site          │
│ handovers   │ scheduled     │ client tools            │
└─────────────┴───────────────┴───────────────────────┘
```

## Rules

- NEVER push to main without James's explicit approval
- ALWAYS use feature branches
- ALWAYS update shared-state.md before ending a session
- Handover files go in repo root: `HANDOVER_SESSION_XX.md`
- Delete handover files ONLY after confirmed pasted into Notion EM
- If you have Notion MCP: update EM directly AND shared-state.md
- If you don't have Notion MCP: update shared-state.md + write handover file

## Key Notion Pages (for MCP-connected sessions)

- External Memory: the brain — full state document
- Command Centre: daily hub
- Knowledge Base: research archive
- Business Hub: Lack Creative + ExternalOS
- Finance Dashboard: money tracking
- Creative Vault: ideas and projects

## Identity

Owner: James Thom (LACK Creative, Leeds, UK)
Primary business: ExternalOS (passive income templates)
Creative business: Lack Creative (motion design, tabled until ExternalOS generates income)
Core motivation: provide for mum, build financial stability, marry Levniz
