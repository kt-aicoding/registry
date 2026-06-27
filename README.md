<p align="center">
  <img src="https://raw.githubusercontent.com/kt-aicoding/.github/main/assets/logo.svg" alt="KT AI Coding logo" width="120" />
</p>

# KT AI Coding Registry

Canonical index for KT AI Coding projects: skills, MCP servers, CLI tools, and agent workflow templates.

中文说明见 [README.zh-CN.md](README.zh-CN.md)。

## Categories

| Category | Purpose | Catalog |
| --- | --- | --- |
| Skills | Reusable instructions and workflows for AI coding agents | [kt-aicoding/skills](https://github.com/kt-aicoding/skills), [catalog/skills.md](catalog/skills.md) |
| MCP Servers | Model Context Protocol servers for coding workflows | [kt-aicoding/mcp-servers](https://github.com/kt-aicoding/mcp-servers), [catalog/mcp-servers.md](catalog/mcp-servers.md) |
| CLI Tools | Command-line utilities for AI coding environments | [kt-aicoding/cli-tools](https://github.com/kt-aicoding/cli-tools), [catalog/cli-tools.md](catalog/cli-tools.md) |
| Agent Workflows | Multi-agent and automation templates | [kt-aicoding/agent-workflows](https://github.com/kt-aicoding/agent-workflows), [catalog/agent-workflows.md](catalog/agent-workflows.md) |

## Initial Migration Candidates

| Project | Current Location | Suggested Destination | Notes |
| --- | --- | --- | --- |
| ccuse | `kevinten-ai/ccuse` | `kt-aicoding/ccuse` | Profile switcher for Claude Code CLI; strong fit as an AI coding CLI tool. |
| ai-coding-mcp | `kevinten-ai/ai-coding-mcp` | `kt-aicoding/ai-coding-mcp` | Directly aligned with the org scope. |
| agent-harness-guide | `kevinten-ai/agent-harness-guide` | evaluate | Move if it is primarily about coding-agent harnesses. |
| mcp-http-proxy | `kevinten-ai/mcp-http-proxy` | evaluate | Move if positioned as MCP/coding-agent network tooling. |

## Created Projects

| Project | Category | Notes |
| --- | --- | --- |
| [cc-codex-config](https://github.com/kt-aicoding/cc-codex-config) | CLI Tools | Claude Code and Codex CLI configuration kit: preferences, status line, installer, and skill. |

## Repository Guidelines

- Keep this org focused on AI coding infrastructure.
- Prefer a monorepo for small skills and templates.
- Promote mature MCP servers and CLIs into standalone repositories.
- Keep broader AI apps, creative projects, and general experiments in `kevinten-ai`.
