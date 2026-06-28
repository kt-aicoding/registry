# Skills

Reusable skills for AI coding agents.

## Repositories

| Repository | Status | Notes |
| --- | --- | --- |
| [`kt-aicoding/skills`](https://github.com/kt-aicoding/skills) | created | Monorepo for Codex, Claude Code, and editor-agent skills. |
| [`kt-aicoding/skill-goal`](https://github.com/kt-aicoding/skill-goal) | created | Standalone `goal-prompt` skill for durable long-running goals and file-backed objectives. |
| [`kt-aicoding/skill-image`](https://github.com/kt-aicoding/skill-image) | created | Skill for selecting README diagram, screenshot, logo, banner, and image generation tooling. |
| [`kt-aicoding/skill-jd`](https://github.com/kt-aicoding/skill-jd) | created | JD shopping browser automation skill with strict no-checkout boundaries. |
| [`kt-aicoding/skill-taobao`](https://github.com/kt-aicoding/skill-taobao) | created | Taobao shopping browser automation skill with strict no-checkout boundaries. |

## Governance Skills

| Skill | Repository path | When to use |
| --- | --- | --- |
| [`cli-tooling-governance`](https://github.com/kt-aicoding/skills/blob/main/skills/codex/cli-tooling-governance/SKILL.md) | `skills/codex/cli-tooling-governance` | Decide CLI/script/MCP/skill boundaries, CLI maturity, verification, and upgrade policy. |
| [`mcp-surface-governance`](https://github.com/kt-aicoding/skills/blob/main/skills/codex/mcp-surface-governance/SKILL.md) | `skills/codex/mcp-surface-governance` | Decide whether a capability should become an MCP server and design small, safe tool surfaces. |
| [`kt-aicoding-registry`](https://github.com/kt-aicoding/skills/blob/main/skills/codex/kt-aicoding-registry/SKILL.md) | `skills/codex/kt-aicoding-registry` | Route AI coding assets to the right repository and keep catalog links consistent. |
| [`goal-prompt-builder`](https://github.com/kt-aicoding/skills/blob/main/skills/codex/goal-prompt-builder/SKILL.md) | `skills/codex/goal-prompt-builder` | Build compact, file-backed long-running goal prompts from broad work requests. |

## Candidate Structure

```text
skills/
  codex/
  claude-code/
  shared/
```
