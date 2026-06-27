# Local CLI And MCP System

Last refreshed: 2026-06-27.

This page is the registry-level index for Kevin's local CLI and MCP operating model. Detailed operating docs live in the category-specific repositories.

## Canonical Documents

| Area | Repository | Document |
| --- | --- | --- |
| CLI tools and provider CLI operations | [`kt-aicoding/cli-tools`](https://github.com/kt-aicoding/cli-tools) | [`docs/local-cli-system.md`](https://github.com/kt-aicoding/cli-tools/blob/main/docs/local-cli-system.md) |
| MCP server policy and CLI/MCP boundary | [`kt-aicoding/mcp-servers`](https://github.com/kt-aicoding/mcp-servers) | [`docs/local-mcp-system.md`](https://github.com/kt-aicoding/mcp-servers/blob/main/docs/local-mcp-system.md) |

## Registry Summary

| Area | Default |
| --- | --- |
| Primary agent CLI | `codex` |
| Compatibility agent CLIs | `claude`, `gemini`, `qwen` |
| Source control | `git`, `gh` |
| Cloud platforms | Provider CLIs, not provider MCPs |
| Default MCP servers | `context7`, `playwright` |
| Figma | No default MCP; use exported files unless explicitly requested |

Principle: keep deterministic cloud, database, source-control, and deployment operations on CLIs. Keep global MCP small and reserved for agent-native value such as current documentation retrieval and browser automation.

## Decision Matrix

| Need | Preferred home | Reference |
| --- | --- | --- |
| Deterministic command-line operation | `kt-aicoding/cli-tools` | CLI operating docs |
| Agent-native tool call surface | `kt-aicoding/mcp-servers` | MCP operating docs |
| Behavior rules and task workflows for agents | `kt-aicoding/skills` | Skill catalog |
| Cross-category navigation | `kt-aicoding/registry` | This catalog |
| Product or demo application | Outside this org unless it is AI coding infrastructure | Portfolio-specific repo |

## Repository Placement

| Content | Preferred repository |
| --- | --- |
| Canonical CLI/MCP/skill/workflow index | `kt-aicoding/registry` |
| CLI utilities and CLI operating docs | `kt-aicoding/cli-tools` |
| MCP server staging and MCP operating docs | `kt-aicoding/mcp-servers` |
| Reusable skills | `kt-aicoding/skills` |
| Claude Code and Codex configuration kit | `kt-aicoding/claudecode-codex-config` |
| Agent workflow templates | `kt-aicoding/agent-workflows` |
