<p align="center">
  <img src="https://raw.githubusercontent.com/kt-aicoding/.github/main/assets/logo.svg" alt="KT AI Coding logo" width="120" />
</p>

# KT AI Coding Registry

KT AI Coding 的组织级索引，用来维护 Skills、MCP Servers、CLI 工具和 Agent 工作流模板之间的边界、入口和迁移方向。

这个仓库不承载具体实现。它负责回答三个问题：

- 某类 AI Coding 资产应该放在哪个仓库。
- 当前有哪些仓库、目录和操作资料可以作为入口。
- 哪些项目适合迁入 `kt-aicoding`，哪些应该留在其他组织或归档。

## 分类

| 分类 | 用途 | 目录 |
| --- | --- | --- |
| Skills | 面向 AI 编程 Agent 的可复用指令和工作流 | [kt-aicoding/skills](https://github.com/kt-aicoding/skills), [catalog/skills.md](catalog/skills.md) |
| MCP Servers | 服务 AI 编程工作流的 Model Context Protocol 服务 | [kt-aicoding/mcp-servers](https://github.com/kt-aicoding/mcp-servers), [catalog/mcp-servers.md](catalog/mcp-servers.md) |
| CLI Tools | 配置和操作 AI 编程环境的命令行工具 | [kt-aicoding/cli-tools](https://github.com/kt-aicoding/cli-tools), [catalog/cli-tools.md](catalog/cli-tools.md) |
| Agent Workflows | 多 Agent 和自动化工作流模板 | [kt-aicoding/agent-workflows](https://github.com/kt-aicoding/agent-workflows), [catalog/agent-workflows.md](catalog/agent-workflows.md) |

## 快速入口

| 需要做什么 | 去哪里 |
| --- | --- |
| 查 CLI 工具和本地 CLI 体系 | [kt-aicoding/cli-tools](https://github.com/kt-aicoding/cli-tools) |
| 查 MCP server 和 MCP 治理原则 | [kt-aicoding/mcp-servers](https://github.com/kt-aicoding/mcp-servers) |
| 查可复用 Agent skill | [kt-aicoding/skills](https://github.com/kt-aicoding/skills) |
| 查多 Agent / 自动化工作流模板 | [kt-aicoding/agent-workflows](https://github.com/kt-aicoding/agent-workflows) |
| 查 Claude Code / Codex 配置套件 | [kt-aicoding/claudecode-codex-config](https://github.com/kt-aicoding/claudecode-codex-config) |
| 查跨类别索引和迁移候选 | 本仓库 |

## 初始迁移候选

| 项目 | 当前位置 | 建议目标 | 说明 |
| --- | --- | --- | --- |
| ccuse | `kevinten-ai/ccuse` | `kt-aicoding/ccuse` | Claude Code CLI profile switcher，适合作为 AI 编程 CLI 工具迁入。 |
| ai-coding-mcp | `kevinten-ai/ai-coding-mcp` | `kt-aicoding/ai-coding-mcp` | 和新组织定位高度一致。 |
| agent-harness-guide | `kevinten-ai/agent-harness-guide` | 待评估 | 如果主要面向 coding agent harness，可以迁入。 |
| mcp-http-proxy | `kevinten-ai/mcp-http-proxy` | 待评估 | 如果定位为 MCP/coding-agent 网络工具，可以迁入。 |

## 已创建项目

| 项目 | 分类 | 说明 |
| --- | --- | --- |
| [claudecode-codex-config](https://github.com/kt-aicoding/claudecode-codex-config) | CLI Tools | Claude Code 和 Codex CLI 配置套件：偏好、状态栏、安装脚本和 Skill。 |

## 操作资料

| 文档 | 说明 |
| --- | --- |
| [目录索引](catalog/README.zh-CN.md) | Skills、MCP Servers、CLI Tools、Agent Workflows 和操作资料的分类入口。 |
| [本地 CLI/MCP 工具体系索引](catalog/local-cli-mcp-system.md) | 指向 CLI 和 MCP 专属仓库里的详细治理文档。 |

## 仓库规范

- 保持组织边界清晰：只收纳 AI 编程基础设施。
- 小型 skills 和模板优先放在 monorepo。
- 成熟的 MCP server 和 CLI 可以独立成仓。
- 泛 AI 应用、创意项目和实验性 demo 继续保留在 `kevinten-ai`。
- 本仓库只保存公开安全的索引信息，不保存 token、cookie、私有路径或私有业务上下文。
