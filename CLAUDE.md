# Claude Memory — Universal Context

## How to use this repo

### Starting a new chat (any device, any app)
Paste this at the start of every new chat:

> "Fetch and read CLAUDE.md from KreativConsultingServicesAIbuilt/claude-memory
> on GitHub. Follow all instructions in it, and update it at the end of
> our session if anything changed."

### One-time setup on a new machine (Claude Code CLI)
Run this once to make it automatic — Claude Code will then load this
memory at the start of every session without being asked:

```bash
mkdir -p ~/.claude && cat > ~/.claude/CLAUDE.md << 'EOF'
# Global Claude Instructions

At the start of every session, fetch and read:
https://github.com/KreativConsultingServicesAIbuilt/claude-memory/blob/main/CLAUDE.md

This file contains all project context, conventions and preferences.
Do this before any other action.
EOF
```

---

## Who I am
- Name: dialuxdator
- GitHub org: KreativConsultingServicesAIbuilt (all AI-built projects live here)
- Apple Developer account registered
- Distribution: GitHub Actions + TestFlight
- Prefers large text — CX101 touchscreen set to 1280×800

---

## Conventions

### Every repo must have a CLAUDE.md
All GitHub repos get a `CLAUDE.md` in the root containing:
- Project purpose
- Hardware / environment
- Architecture overview
- Current status + what was last worked on
- Known issues / next steps

Update it at the end of every development session before closing out.

### Git workflow
- Always pull before starting work
- Push at the end of every session
- Commit messages explain the *why*, not just the what

### LaunchAgents (macOS)
- Only essential agents — never install duplicates
- Always verify with `launchctl list | grep <label>` after installing

---

## Active projects

### car-dashboard
**Repo:** KreativConsultingServicesAIbuilt/car-dashboard  
**What:** Tesla-style web dashboard for Citroën DS5  
**Stack:** Python (Flask) + vanilla JS/CSS  
**Hardware:** MacBook Pro + CX101 touchscreen (1280×800)  
**Status:** Fully working — hibernate/wake end-to-end confirmed with CX101 touchscreen connected
→ See CLAUDE.md in that repo for full detail

---

## MacBook Pro — persistent pmset settings
Applied once with sudo via car-dashboard/setup.sh:
```
acwake=1, hibernatemode=25, standby=0
proximitywake=0, womp=0, tcpkeepalive=0, ttyskeepawake=0
```
`proximitywake=0` is critical — iPhone proximity was waking Mac after hibernate.

---

## Maintenance instructions for Claude
When ending any session where something changed:
1. Update the relevant project entry above
2. Update "Last updated" below
3. Commit and push: `cd /Users/dialuxdator/claude-memory && git add CLAUDE.md && git commit -m "Update memory: <what changed>" && git push`

## Last updated: 2026-04-20
