<p align="center">
  <img src="https://raw.githubusercontent.com/kt-aicoding/.github/main/assets/logo.svg" alt="KT AI Coding logo" width="120" />
</p>

# KT AI Coding Registry

KT AI Coding 项目索引：Skills、MCP Servers、CLI 工具和 Agent 工作流模板。

## 分类

| 分类 | 用途 | 目录 |
| --- | --- | --- |
| Skills | 面向 AI 编程 Agent 的可复用指令和工作流 | [catalog/skills.md](catalog/skills.md) |
| MCP Servers | 服务 AI 编程工作流的 Model Context Protocol 服务 | [catalog/mcp-servers.md](catalog/mcp-servers.md) |
| CLI Tools | 配置和操作 AI 编程环境的命令行工具 | [catalog/cli-tools.md](catalog/cli-tools.md) |
| Agent Workflows | 多 Agent 和自动化工作流模板 | [catalog/agent-workflows.md](catalog/agent-workflows.md) |

## 初始迁移候选

| 项目 | 当前位置 | 建议目标 | 说明 |
| --- | --- | --- | --- |
| ccuse | `kevinten-ai/ccuse` | `kt-aicoding/ccuse` | Claude Code CLI profile switcher，适合作为 AI 编程 CLI 工具迁入。 |
| ai-coding-mcp | `kevinten-ai/ai-coding-mcp` | `kt-aicoding/ai-coding-mcp` | 和新组织定位高度一致。 |
| agent-harness-guide | `kevinten-ai/agent-harness-guide` | 待评估 | 如果主要面向 coding agent harness，可以迁入。 |
| mcp-http-proxy | `kevinten-ai/mcp-http-proxy` | 待评估 | 如果定位为 MCP/coding-agent 网络工具，可以迁入。 |

## 仓库规范

- 保持组织边界清晰：只收纳 AI 编程基础设施。
- 小型 skills 和模板优先放在 monorepo。
- 成熟的 MCP server 和 CLI 可以独立成仓。
- 泛 AI 应用、创意项目和实验性 demo 继续保留在 `kevinten-ai`。

