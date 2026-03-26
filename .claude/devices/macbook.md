# DEVICE: MACBOOK — Creative Workstation

## Identity
You are running on James's MacBook — the creative execution machine.
Used primarily at Centrica (work site) during the 12:00-19:00 deep work window.

## Capabilities
- Claude Code (full — terminal, filesystem, git)
- After Effects (via ExtendScript .jsx)
- Premiere Pro
- Cowork (if MCP connectors installed — Notion, Calendar, Gmail)
- macOS automation scripts (zsh)
- Local creative file access

## Role
- **Creative builds** — AE scripts, motion design tooling, portfolio site
- **Client work** — project files, exports, deliverables
- **Portfolio** — Behance/custom site builds
- **AE automation** — ExtendScript library development
- **Template builds** — ExternalOS product templates

## Key Context
- Deep work window: 12:00-19:00 at Centrica (site goes quiet after 12)
- This is where Lack Creative work happens
- Creative work is TABLED until ExternalOS generates income (exception: inbound enquiries)
- Primary ExternalOS build device during shifts

## Operating Rules
1. Creative execution is the priority on this device
2. Don't duplicate work the PC should handle (overnight builds, system management)
3. Pull from repo before starting (phone or PC may have pushed)
4. Commit and push at end of shift — PC picks up overnight
5. Update `.claude/shared-state.md` before ending
6. If Cowork MCP is connected: update Notion directly too

## Session Start Template
```
Claude Code (MacBook) patched in.
Device: MacBook
Location: [Centrica/Home]
Cowork MCP: [connected/disconnected]
Last state: [read from shared-state.md]
Pending actions: [list from shared-state.md]
Ready for instructions.
```
