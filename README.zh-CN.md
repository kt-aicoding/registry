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
| Operations | AI coding agent 运行、迁移、cron 和本地服务运维实践 | [catalog/operations.md](catalog/operations.md) |
| Supporting Resources | 组织 profile、视觉资产和配图资料 | [catalog/supporting-resources.md](catalog/supporting-resources.md) |

## 快速入口

| 需要做什么 | 去哪里 |
| --- | --- |
| 查 CLI 工具和本地 CLI 体系 | [kt-aicoding/cli-tools](https://github.com/kt-aicoding/cli-tools) |
| 查 MCP server 和 MCP 治理原则 | [kt-aicoding/mcp-servers](https://github.com/kt-aicoding/mcp-servers) |
| 查可复用 Agent skill | [kt-aicoding/skills](https://github.com/kt-aicoding/skills) |
| 查多 Agent / 自动化工作流模板 | [kt-aicoding/agent-workflows](https://github.com/kt-aicoding/agent-workflows) |
| 查 Claude Code / Codex 配置套件 | [kt-aicoding/claudecode-codex-config](https://github.com/kt-aicoding/claudecode-codex-config) |
| 查 agent 指令实践 | [kt-aicoding/agents](https://github.com/kt-aicoding/agents) |
| 查 OpenClaw / Hermes 运维实践 | [catalog/operations.md](catalog/operations.md) |
| 查 README 配图和视觉资产资料 | [kt-aicoding/images](https://github.com/kt-aicoding/images) |
| 查跨类别索引和迁移候选 | 本仓库 |

## 判断方法

当一个新资产准备进入 `kt-aicoding` 时，先按下面的规则判断归属：

| 资产形态 | 首选位置 | 说明 |
| --- | --- | --- |
| 可复用 Agent 指令、流程、检查清单 | `skills` | 价值主要是行为约束和判断 |
| 命令行工具、安装器、迁移脚本 | `cli-tools` | 价值主要是可执行命令和确定性操作 |
| Agent 可调用的外部工具面 | `mcp-servers` | 价值主要是推理循环中的工具调用 |
| 多 Agent 编排、评审、发布流程 | `agent-workflows` | 价值主要是跨 Agent 或跨阶段协作 |
| 跨类别索引、迁移候选、组织边界 | `registry` | 价值主要是导航和治理 |
| 成熟单品 | 独立仓库 | 有独立用户、版本节奏和维护边界 |

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
| [claudecode-codex-switch](https://github.com/kt-aicoding/claudecode-codex-switch) | CLI Tools | Claude Code 与 Codex CLI 的 provider/profile 切换工具。 |
| [skill-goal](https://github.com/kt-aicoding/skill-goal) | Skills | `goal-prompt` 独立 skill，用于长期目标提示词和 file-backed goal。 |
| [skill-image](https://github.com/kt-aicoding/skill-image) | Skills | 选择 README 图示、截图、logo、banner 和视觉资产工具的 skill。 |
| [skill-jd](https://github.com/kt-aicoding/skill-jd) | Skills | 京东低频、可监督浏览器自动化购物辅助 skill。 |
| [skill-taobao](https://github.com/kt-aicoding/skill-taobao) | Skills | 淘宝低频、可监督浏览器自动化购物辅助 skill。 |
| [agents](https://github.com/kt-aicoding/agents) | Agent Workflows | `AGENTS.md` / `CLAUDE.md` 实践、模板、迁移指南和语料治理。 |
| [claws](https://github.com/kt-aicoding/claws) | Operations | OpenClaw 运维、cron 修复和 fleet 治理手册。 |
| [hermes](https://github.com/kt-aicoding/hermes) | Operations | Hermes Agent 本地迁移、cron、launchd 和验证实践。 |
| [images](https://github.com/kt-aicoding/images) | Supporting Resources | README 配图、SVG 图示、生图工具和视觉资产资料库。 |

## 操作资料

| 文档 | 说明 |
| --- | --- |
| [目录索引](catalog/README.zh-CN.md) | Skills、MCP Servers、CLI Tools、Agent Workflows 和操作资料的分类入口。 |
| [本地 CLI/MCP 工具体系索引](catalog/local-cli-mcp-system.md) | 指向 CLI 和 MCP 专属仓库里的详细治理文档。 |
| [平台成本和免费额度参考](catalog/platform-cost-free-tiers.md) | 平台资源、免费额度、官方来源和账单跟进清单。 |
| [全面探索和优化 Ledger](catalog/exploration-optimization-ledger.md) | 当前 goal 的仓库、平台、验证和 blocker 记录。 |

## 仓库规范

- 保持组织边界清晰：只收纳 AI 编程基础设施。
- 小型 skills 和模板优先放在 monorepo。
- 成熟的 MCP server 和 CLI 可以独立成仓。
- 泛 AI 应用、创意项目和实验性 demo 继续保留在 `kevinten-ai`。
- 本仓库只保存公开安全的索引信息，不保存 token、cookie、私有路径或私有业务上下文。

## 迁入前检查

- 是否直接服务 AI 编程，而不是泛 AI 应用。
- 是否有清晰的类别归属，避免一个仓库同时承担 CLI、MCP、skill 和产品职责。
- 是否能公开说明，不依赖私有路径、私有账号或密钥。
- 是否已经有最小 README、目录结构和维护边界。
- 是否值得进入组织级索引，或者更适合留在原组织作为实验项目。
