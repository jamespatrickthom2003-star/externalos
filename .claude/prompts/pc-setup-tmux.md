# PC SETUP PROMPT — Paste this into Claude Code on your PC

Copy everything below the line and paste it into Claude Code on your always-on PC.

---

You are Claude Code on James's always-on Windows PC. This is a setup session. Do the following in order:

## 1. Pull the shared consciousness system

```
git pull origin claude/remote-mobile-coding-AU3P9
```

Read CLAUDE.md, then read .claude/shared-state.md and .claude/devices/pc.md. Announce yourself as patched in.

## 2. Set up tmux for persistent sessions

This is the critical piece. James needs to SSH into this PC from his phone and attach to Claude Code sessions that survive disconnects.

- Check if this is Windows (it is — always-on PC runs Windows)
- For Windows: install tmux via WSL (Windows Subsystem for Linux). Steps:
  1. Check if WSL is installed: `wsl --list`
  2. If not installed: `wsl --install` (this installs Ubuntu by default)
  3. Inside WSL: `sudo apt update && sudo apt install -y tmux openssh-server`
  4. Configure SSH in WSL: `sudo systemctl enable ssh && sudo systemctl start ssh`
  5. Create a tmux config for persistence:

```bash
cat > ~/.tmux.conf << 'TMUXCONF'
# Keep sessions alive
set -g history-limit 50000
set -g default-terminal "screen-256color"

# Easy attach
set -g mouse on

# Status bar shows session info
set -g status-style 'bg=#1a1a1a fg=#c8f135'
set -g status-left '[ExternalOS] '
set -g status-right '%H:%M %d-%b'

# Don't kill session on detach
set -g detach-on-destroy off
TMUXCONF
```

  6. Create a named session for Claude Code: `tmux new-session -d -s claude-code`
  7. Test: `tmux list-sessions` should show "claude-code"

- ALTERNATIVE if WSL is problematic: Check if Git Bash has tmux, or install via MSYS2/Chocolatey

## 3. Set up Tailscale for zero-config VPN

- Download and install Tailscale: `winget install Tailscale.Tailscale`
- Or if winget doesn't have it, tell James to download from https://tailscale.com/download/windows
- Once installed, James needs to sign in (this is manual — tell him to do it)
- After sign-in, note the Tailscale IP of this machine — James needs it for phone SSH

## 4. Test SSH access

- From WSL, check SSH is running: `sudo systemctl status ssh`
- Note the local IP: `hostname -I`
- Note the WSL port forwarding if needed (Windows → WSL port 22)
- If Windows firewall blocks port 22, add a rule: `netsh advfirewall firewall add rule name="SSH" dir=in action=allow protocol=TCP localport=22`

## 5. Execute the Notion handover

- Read `.claude/last-handover.md` from the repo
- You have Cowork with Notion MCP — execute ALL updates listed in that file into Notion
- This includes: EM header, Claude Ecosystem table, Claude Code section, Session Log, Active Work, Command Centre, Vision
- After completing, mark the handover as done

## 6. Create a startup script

Create a script that auto-starts tmux + Claude Code session on boot:

```bash
# Save to D:/TOOLS/start-claude-session.bat
wsl -e bash -c "tmux has-session -t claude-code 2>/dev/null || tmux new-session -d -s claude-code; echo 'Claude Code session ready'"
```

## 7. Final check

- Confirm tmux is running with a named session
- Confirm SSH is accessible
- Confirm Tailscale is installed (sign-in may be manual)
- Confirm Notion EM is updated from handover
- Update .claude/shared-state.md with new PC status
- Commit and push

Report back everything you did and any manual steps James needs to complete (like Tailscale sign-in or WSL install approval).
