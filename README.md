# Agent Vibe Coding Skills

Skills for teaching Agent Vibe Coding with Codex, Claude Code, or other AI coding agents.

This repository contains two skills and one demo prompt:

- `pi-coding-agent`: patterns for tool registration, provider abstraction, JSONL sessions, RPC mode, skills, prompts, and package-style agent extensions.
- `craft-agent-template`: patterns extracted from Craft Agents-style apps, including Bun workspaces, Electron / React, Jotai session isolation, WebSocket RPC, MCP integration, and AppShell structure.
- `prompts/finance-agent-web-coding-demo-prompt.md`: a three-part prompt for building a teaching-grade Finance Agent Web Coding demo with Spec-first, TDD, worktrees, tool calling, evaluation, and browser verification.

Use them together when you want an AI coding agent to build a Web / Electron Agent project with real engineering discipline: Spec-first, TDD, worktrees, tool calling, context engineering, evaluation, and browser verification.

## Install

Clone this repository:

```bash
git clone https://github.com/helsome/agent-vibe-coding-skills.git
cd agent-vibe-coding-skills
```

### Codex

Copy the skills into your Codex skills directory:

```bash
mkdir -p ~/.codex/skills
cp -R skills/pi-coding-agent ~/.codex/skills/
cp -R skills/craft-agent-template ~/.codex/skills/
```

On Windows, use PowerShell:

```powershell
$skillsDir = Join-Path $HOME ".codex\skills"
New-Item -ItemType Directory -Path $skillsDir -Force | Out-Null
Copy-Item -Path "skills\pi-coding-agent" -Destination $skillsDir -Recurse -Force
Copy-Item -Path "skills\craft-agent-template" -Destination $skillsDir -Recurse -Force
```

Restart Codex after copying.

### Claude Code or other skill-compatible agents

Copy the two folders under `skills/` into the skill directory used by your agent runtime.

The important part is that each skill folder keeps its `SKILL.md` file at the folder root:

```text
skills/
  pi-coding-agent/
    SKILL.md
  craft-agent-template/
    SKILL.md
    references/
```

## Recommended Companion Plugin

Install the Superpowers plugin separately if your AI coding environment supports it.

For the Finance Agent Web Coding demo, the prompt expects these Superpowers skills to be available:

- `writing-plans`
- `using-git-worktrees`
- `test-driven-development`
- `subagent-driven-development`
- `verification-before-completion`

## Usage

Use the demo prompt directly:

```bash
cat prompts/finance-agent-web-coding-demo-prompt.md
```

Paste it into Codex, Claude Code, or another AI coding agent after installing the two skills and Superpowers.

In your own coding agent prompt, tell the agent to use:

- `pi-coding-agent` for Agent harness patterns.
- `craft-agent-template` for Web / Electron app architecture patterns.
- Superpowers for planning, TDD, worktree isolation, subagent execution, and final verification.

These skills are references and process guides. They do not provide financial APIs or live market data by themselves. For demos, start with local mock tools, then swap the tool implementation to a real data source later.
