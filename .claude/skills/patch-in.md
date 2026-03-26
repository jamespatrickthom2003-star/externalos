# SKILL: Patch In

## Trigger phrases
- "patch in"
- "connect"
- "sync up"
- "what's the state"

## Description
Universal patch-in skill. Run this at the start of any session on any device
to sync with the shared consciousness and announce your presence.

## Workflow

### Step 1: Detect device
Identify which device this session is running on:
- Phone: mobile web session, SSH connection, or Termius
- PC: Windows, D: drive present, always-on machine
- MacBook: macOS, creative software available

### Step 2: Pull latest state
```bash
git pull origin <current-branch>
```

### Step 3: Read shared state
Read `.claude/shared-state.md` for current operational status.

### Step 4: Read device profile
Read `.claude/devices/<device>.md` for role and capabilities.

### Step 5: Check for handovers
Read `.claude/last-handover.md` or any `HANDOVER_SESSION_*.md` files
in repo root for pending relay actions.

### Step 6: Announce
Output the session start template from the device profile,
filled in with live data from shared state.

### Step 7: Pending actions
List any pending cross-device actions from shared-state.md
and ask James which to tackle this session.

## End-of-session protocol
Before ending ANY session:
1. Update `.claude/shared-state.md` with what was done
2. Write handover file if Notion updates are needed (and no MCP available)
3. Commit and push all changes
4. Announce: "Session closed. State synced. [Device] signing off."
