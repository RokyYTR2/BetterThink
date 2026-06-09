<p align="center">
  <img src="https://em-content.zobj.net/source/apple/391/brain_1f9e0.png" width="120" />
</p>

<h1 align="center">BetterThink</h1>

<p align="center">
  <strong>stop coding. think first. finish one thing. then next thing.</strong>
</p>

<p align="center">
  <a href="https://github.com/RokyYTR2/BetterThink/stargazers"><img src="https://img.shields.io/github/stars/RokyYTR2/BetterThink?style=flat&color=blue" alt="Stars"></a>
  <a href="https://github.com/RokyYTR2/BetterThink/commits/main"><img src="https://img.shields.io/github/last-commit/RokyYTR2/BetterThink?style=flat" alt="Last Commit"></a>
  <a href="LICENSE"><img src="https://img.shields.io/github/license/RokyYTR2/BetterThink?style=flat" alt="License"></a>
</p>

<p align="center">
  <a href="#the-problem">The Problem</a> •
  <a href="#what-it-does">What It Does</a> •
  <a href="#install">Install</a> •
  <a href="#supported-agents">Supported Agents</a>
</p>

---

A skill for [Claude Code](https://docs.anthropic.com/en/docs/claude-code), Codex, and Gemini CLI that fixes the most common way AI agents fail — not wrong answers, but wrong habits. Asking after coding. Moving on before done. Bloating memory files. Shipping desktop-only UI.

## The Problem

AI coding agents are capable. They're just undisciplined.

<table>
<tr>
<td width="50%">

### ❌ Default agent behavior

> Starts coding immediately. Assumes scope. Moves to the next task before the current one is verified. Updates `AGENTS.md` after every tiny change. Ships UI without checking mobile.

</td>
<td width="50%">

### ✅ BetterThink behavior

> Asks until 95% confident. One task at a time, verified before moving on. `AGENTS.md` updated only on meaningful changes. Three viewports checked every time.

</td>
</tr>
</table>

**Same agent. Better habits.**

```
┌──────────────────────────────────────────┐
│  ASSUMPTIONS BEFORE CODING     ████ none │
│  TASKS FINISHED BEFORE NEXT    ████ 100% │
│  MEMORY FILE BLOAT             ████ none │
│  UI VIEWPORT COVERAGE          ████  3/3 │
└──────────────────────────────────────────┘
```

## What It Does

Six rules. Applied before every coding task.

| Rule | What it fixes |
|------|---------------|
| **Clarify before coding** | Agent asks until 95% confident — no silent assumptions on scope, stack, or edge cases |
| **One slice at a time** | Current task verified (diff read, test run, behavior checked) before the next begins |
| **Delegate mechanical work** | File search, linting, screenshots → Haiku subagent. Architecture decisions stay on the main model |
| **Keep memory files lean** | Update `AGENTS.md` / `GEMINI.md` / `CLAUDE.md` only on meaningful changes — new dep, new script, new folder |
| **Screenshot-verify UI** | Three viewports (375px / 768px / 1440px), every time, until all three look right |
| **Supplementary docs on demand** | Deep docs written freely, loaded only when the current task needs them |

## Install

### Claude Code

```bash
mkdir -p ~/.claude/skills/betterthink
cp claude/SKILL.md ~/.claude/skills/betterthink/SKILL.md
```

### Codex

```bash
mkdir -p ~/.codex/skills/betterthink
cp codex/SKILL.md ~/.codex/skills/betterthink/SKILL.md
```

### Gemini CLI

```bash
mkdir -p ~/.gemini/skills/betterthink
cp gemini/SKILL.md ~/.gemini/skills/betterthink/SKILL.md
```

### Cursor

```bash
mkdir -p .cursor/rules
cp cursor/SKILL.md .cursor/rules/betterthink.mdc
```

### GitHub Copilot

```bash
mkdir -p .github
cp copilot/SKILL.md .github/copilot-instructions.md
```

The skill activates automatically when the agent detects a coding task. No extra configuration needed.

## Supported Agents

| Agent | Folder | Memory file |
|-------|--------|-------------|
| Claude Code | `claude/` | `CLAUDE.md` / `AGENTS.md` |
| OpenAI Codex | `codex/` | `AGENTS.md` |
| Gemini CLI | `gemini/` | `GEMINI.md` / `AGENT.md` |
| Cursor | `cursor/` | `.cursor/rules/*.mdc` / `.cursorrules` |
| GitHub Copilot | `copilot/` | `.github/copilot-instructions.md` |

## Why

Most AI coding failures aren't a capability problem. They're a discipline problem.

The agent knew how to fix the bug — it just moved on before checking if it worked. It knew you wanted a mobile-friendly layout — it just never opened DevTools at 375px. It knew `AGENTS.md` was supposed to stay lean — it just logged every minor refactor anyway.

BetterThink is a set of explicit guardrails written directly into the skill prompt. The agent reads them before every task and can't pretend it didn't.

## License

MIT
