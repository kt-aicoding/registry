# AI Coding System Exploration And Optimization Goal

## Outcome

全面探索并优化 Kevin 的 AI coding 工具体系。完成后，`kt-aicoding` 相关仓库、CLI/MCP/skills/docs、平台资源与成本资料、部署验证资料都必须有清晰归属、当前状态、验证证据、公开安全文档和后续行动记录。

## Context

工作根目录：

- `<WORKSPACE_ROOT>`
- `<WORKSPACE_ROOT>/registry`
- `<WORKSPACE_ROOT>/cli-tools`
- `<WORKSPACE_ROOT>/mcp-servers`
- `<WORKSPACE_ROOT>/kt-aicoding-skills`
- 其他 `kt-aicoding` 相关本地仓库，如 `agent-workflows`、`claudecode-codex-config`

远端组织：

- `https://github.com/orgs/kt-aicoding/repositories`

继续或恢复前必须读取：

- 本文件
- `registry/README.md`
- `registry/catalog/*.md`
- `cli-tools/README.md`
- `cli-tools/docs/*.md`
- `mcp-servers/README.md`
- `mcp-servers/docs/*.md`
- `kt-aicoding-skills/README.md`
- `kt-aicoding-skills/skills/codex/*/SKILL.md`
- 相关 `references/*.md`

维护 ledger：

- `registry/catalog/exploration-optimization-ledger.md`

## Scope

In scope:

- `kt-aicoding` 组织下 AI coding 基础设施仓库
- CLI 体系：Codex、Claude Code、Gemini、Qwen、GitHub CLI、Vercel、Supabase、Cloudflare/Wrangler、Netlify、Railway、Fly、CloudBase 等
- MCP 体系：默认 MCP、provider MCP 边界、tool surface 设计
- Skills 体系：Codex skills、Claude Code 规范、shared workflows
- README、catalog、docs、references、agents/openai.yaml
- 平台成本、免费额度、资源状态、部署入口的公开安全摘要

Out of scope:

- 未经用户确认，不删除云资源、数据库、bucket、queue、domain、deployment、secret
- 未经用户确认，不改账单计划、不启用付费功能、不做生产破坏性操作
- 不输出、不提交 token、cookie、API key、OAuth secret、`.env` 原文或私有 credential
- 不把个人私有路径、账号隐私、私有业务上下文写入公开仓库
- 不重构无关 demo，除非它直接影响 AI coding 基础设施

## Constraints

1. 每个仓库先运行 `git status --short`，保护用户已有改动。
2. 只 stage 和提交本 goal 相关文件。
3. 不 revert 用户未要求回滚的改动。
4. GitHub CLI 优先使用 `env -u GH_TOKEN gh ...`。
5. 涉及最新价格、免费额度、平台规则、CLI 行为时，必须用官方文档或当前 CLI/dashboard 状态验证。
6. 公开文档必须做敏感信息扫描。
7. 文档优先中文；英文文档可保留但需与中文主入口一致。
8. 修改后必须提交、推送，并验证远端文件或 ref。

## Milestones

1. Inventory：从当前本地和远端状态重新盘点仓库、CLI、MCP、skills、平台入口和已有 docs。
2. Boundary Review：检查 registry、cli-tools、mcp-servers、skills、agent-workflows、config kit 的职责边界，记录重复、缺口、冲突和过时内容。
3. Optimization：做最小可维护改动，补 README/catalog/docs/skill/reference 链接和治理说明。
4. Verification：运行结构校验、敏感扫描、`git diff --check`、skill validator、只读 CLI/API 检查。
5. Publication：按仓库提交、推送，并验证远端状态。
6. Completion Audit：基于当前文件、命令输出和远端状态审计，不依赖聊天记忆。

## Per-Item Loop

对每个仓库或平台执行：

1. Inventory：确认 repo、branch、remote、dirty worktree、文档入口、部署或平台入口。
2. Targeted Read：读取相关 README、docs、catalog、skills、references 和项目指令。
3. Gap Analysis：记录缺失入口、重复内容、错误链接、过时说明、未验证声明。
4. Implement：只做最小完整改动；避免复制长篇内容，优先使用 canonical link。
5. Validate：运行可用校验；至少执行 `git diff --check` 和敏感扫描。
6. Commit/Push：只提交目标相关文件，推送后验证远端 ref 或关键文件。
7. Ledger：更新 `registry/catalog/exploration-optimization-ledger.md`，记录证据、提交、blocker、后续行动。

## Platform Checks

优先使用只读命令：

```bash
vercel whoami
supabase projects list
wrangler whoami
wrangler pages project list
wrangler kv namespace list
wrangler d1 list
wrangler r2 bucket list
wrangler queues list
netlify status
netlify sites:list --json
flyctl auth whoami
flyctl apps list --json
railway whoami
tcb env list
```

若 CLI 未登录，记录登录状态、影响范围、下一步命令，不读取或输出 credential 文件。

## Verification

最低验证：

```bash
git status --short
git diff --check
rg -n "/Users/|gho_|Bearer|API_KEY|SERVICE_ROLE|password|cookie|secret|token" README.md README.zh-CN.md docs catalog skills || true
env -u GH_TOKEN gh auth status --active
```

Skills 验证：

```bash
python3 ${CODEX_HOME:-$HOME/.codex}/skills/.system/skill-creator/scripts/quick_validate.py <skill-folder>
```

远端验证示例：

```bash
env -u GH_TOKEN gh api repos/kt-aicoding/<repo>/contents/<path> --jq '.name + " " + .sha'
git ls-remote origin main
```

敏感扫描只允许命中安全说明或 placeholder，不允许真实 secret。

## Done When

只有同时满足以下条件才能 complete：

- 所有 in-scope 仓库和平台都有 ledger 状态。
- 每个发现项都是 fixed、documented、not applicable 或 externally blocked。
- 修改过的仓库通过校验、敏感扫描、提交、推送和远端验证。
- README、catalog、docs、skills、references 没有明显冲突或断链。
- 平台成本/免费额度/资源资料有来源和日期，且不含 secret。
- 未执行任何未授权删除、付费、生产破坏性操作。
- completion audit 已写入 ledger，并基于当前证据通过。

## If Blocked

如果 GitHub 权限、网络、CLI 登录、平台 auth、官方文档访问或组织权限阻塞，先完成安全本地工作，然后记录：

- system/owner
- timestamp
- attempted command/action
- current error/result
- why local work cannot continue
- next action
- whether acceptable for completion

单个项目 blocked 不阻塞整个 goal；继续处理其他项目。只有所有剩余项目都无法推进，才标记整个 goal blocked。

## Final Report

最终报告必须包含：

- 每个仓库的 branch、commit、push 状态
- 修改摘要
- 验证命令摘要
- 远端验证摘要
- 平台检查摘要
- unresolved blockers
- dirty worktree notes
- ledger/audit 文件路径
