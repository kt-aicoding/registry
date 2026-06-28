# AI Coding System Exploration And Optimization Ledger

Last updated: 2026-06-28.

## Objective

Follow `docs/goals/ai-coding-system-exploration-optimization.md` to explore and optimize Kevin's AI coding system across `kt-aicoding` repositories, CLI/MCP/skills/docs, platform cost/resource notes, and deployment verification.

## Status Summary

| Area | Status | Evidence | Notes |
| --- | --- | --- | --- |
| Goal instruction file | completed | `docs/goals/ai-coding-system-exploration-optimization.md` | Durable file-backed goal created for resumable execution. |
| Registry catalog | verified | `README.md`, `README.zh-CN.md`, `catalog/*.md` | Categories for operations and supporting resources are present; repo coverage now reflects current remote inventory. |
| kt-aicoding repositories | inventoried | `env -u GH_TOKEN gh api 'orgs/kt-aicoding/repos?per_page=100&type=all&sort=updated'` | 16 public remote repos identified on 2026-06-28. |
| CLI/MCP/docs/skills | verified | Local status checks, `quick_validate.py`, `codex mcp list`, `codex doctor --json` | Governance skills and standalone skill repos pass; default MCP remains `context7` + `playwright`; CLI/MCP operating docs refreshed to 2026-06-28. |
| Platform resources/cost notes | in progress | Read-only CLI checks | No destructive or paid actions authorized. |

## Repository Inventory

| Repository | Local path | Remote | Branch | Dirty status | Status | Evidence / next action |
| --- | --- | --- | --- | --- | --- | --- |
| `.github` | `<WORKSPACE_ROOT>/kt-aicoding-dotgithub` | `kt-aicoding/.github` | `main` | clean | inventoried | Organization profile repo; cataloged under supporting resources. |
| `agent-workflows` | `<WORKSPACE_ROOT>/agent-workflows` | `kt-aicoding/agent-workflows` | `main` | clean | inventoried | Cataloged under agent workflows. |
| `agents` | `<WORKSPACE_ROOT>/agents` | `kt-aicoding/agents` | `main` | clean | verified | Local HEAD `8cb0c4c` matches remote `main`; existing dirty state has been resolved before this pass. |
| `claudecode-codex-config` | `<WORKSPACE_ROOT>/claudecode-codex-config` | `kt-aicoding/claudecode-codex-config` | `main` | clean | inventoried | Cataloged under CLI tools. |
| `claudecode-codex-switch` | `<WORKSPACE_ROOT>/claudecode-codex-switch` | `kt-aicoding/claudecode-codex-switch` | `main` | clean | inventoried | Added to CLI catalog; supersedes old `ccuse` migration candidate. |
| `claws` | `<WORKSPACE_ROOT>/claws` | `kt-aicoding/claws` | `main` | clean | inventoried | Cataloged under operations. |
| `cli-tools` | `<WORKSPACE_ROOT>/cli-tools` | `kt-aicoding/cli-tools` | `main` | clean | inventoried | Current provider CLI state refresh pending commit. |
| `hermes` | `<WORKSPACE_ROOT>/hermes` | `kt-aicoding/hermes` | `main` | clean | verified | Local HEAD `18d7939` matches remote `main`; existing dirty state has been resolved before this pass. |
| `images` | `<WORKSPACE_ROOT>/images` | `kt-aicoding/images` | `main` | clean | verified | README now includes project-type image usage guidance; SVG export script and example asset validated; local HEAD matches remote `main`. |
| `mcp-servers` | `<WORKSPACE_ROOT>/mcp-servers` | `kt-aicoding/mcp-servers` | `main` | clean | inventoried | MCP docs already link governance skill. |
| `registry` | `<WORKSPACE_ROOT>/registry` | `kt-aicoding/registry` | `main` | clean | verified | Goal file, ledger, and catalog updates are pushed and verified. |
| `skill-goal` | `<WORKSPACE_ROOT>/skill-goal` | `kt-aicoding/skill-goal` | `main` | clean | verified | README now includes one-line install and portable validation command; `quick_validate.py goal-prompt` passed; local HEAD matches remote `main`. |
| `skill-image` | `<WORKSPACE_ROOT>/skill-image` | `kt-aicoding/skill-image` | `main` | clean | verified | README now includes one-line install and portable validation command; `quick_validate.py skill/skill-image`, `bash -n`, and remote README check passed; local HEAD matches remote `main`. |
| `skill-jd` | `<WORKSPACE_ROOT>/skill-jd` | `kt-aicoding/skill-jd` | `main` | clean | verified | `quick_validate.py .` passed; local HEAD matches remote `main`. |
| `skill-taobao` | `<WORKSPACE_ROOT>/skill-taobao` | `kt-aicoding/skill-taobao` | `main` | clean | verified | `quick_validate.py .` passed; local HEAD matches remote `main`. |
| `skills` | `<WORKSPACE_ROOT>/kt-aicoding-skills` | `kt-aicoding/skills` | `main` | clean | inventoried | Governance skills pass; `goal-prompt-builder` added to catalog. |

## Platform Inventory

| Platform | CLI command | Status | Evidence / next action |
| --- | --- | --- | --- |
| GitHub | `env -u GH_TOKEN gh auth status --active`; REST repo list | verified | Keyring auth works; 16 public `kt-aicoding` repos enumerated. Do not record token details. |
| Vercel | `vercel whoami`; `vercel project ls ... --json` | verified | Logged in; 4 projects visible from read-only CLI query. |
| Supabase | `supabase projects list` | verified | One active project, `kevinten10`, visible; local registry repo is not linked to a Supabase project. |
| Cloudflare | `wrangler whoami`; resource count commands | partially verified | Logged in through `wrangler`; read-only counts returned Pages=1, KV=2, D1=1. R2/Queues count commands returned no parseable JSON in this run. |
| Netlify | `netlify status`; `netlify sites:list --json` | verified | Logged in; current directory is not linked; site list count is 0. Do not record account email. |
| Fly.io | `flyctl auth whoami`; `flyctl apps list --json` | verified | Logged in; apps list count is 0; metrics send warning is non-blocking. Do not record account email. |
| Railway | `railway whoami` | external blocker | CLI reports unauthorized; next action is `railway login` when Railway checks are needed. |
| CloudBase | `tcb env list` | verified | One normal personal environment visible; do not record raw environment identifiers in public docs. |

## MCP And Agent CLI Evidence

| Check | Status | Evidence |
| --- | --- | --- |
| Default MCP list | verified | `codex mcp list` shows `context7` and `playwright` enabled. |
| Codex doctor | warning | `codex doctor --json` reports overall warning, while config load, MCP config, provider reachability, websocket reachability, and git environment are usable. |
| Governance skills | verified | `quick_validate.py` passed for `cli-tooling-governance`, `mcp-surface-governance`, and `kt-aicoding-registry`. |
| `goal-prompt-builder` path | not applicable to earlier command | The actual monorepo path is `skills/codex/goal-prompt-builder`, not `skills/codex/goal-prompt`. |

## Change Log

| Date | Area | Change | Evidence |
| --- | --- | --- | --- |
| 2026-06-28 | registry | Created durable goal instruction file. | `docs/goals/ai-coding-system-exploration-optimization.md` |
| 2026-06-28 | registry | Created current-state ledger. | `catalog/exploration-optimization-ledger.md` |
| 2026-06-28 | registry | Verified catalog categories and repo coverage against current remote inventory. | `README*.md`, `catalog/skills.md`, `catalog/cli-tools.md`, `catalog/agent-workflows.md`, `catalog/operations.md`, `catalog/supporting-resources.md` |
| 2026-06-28 | docs | Refreshed registry CLI/MCP index and CLI/MCP operating docs to 2026-06-28 evidence. | `catalog/local-cli-mcp-system.md`, `cli-tools/docs/local-cli-system.md`, `mcp-servers/docs/local-mcp-system.md` |
| 2026-06-28 | publication | Pushed and verified registry, CLI, and MCP documentation refresh commits. | `registry@4f54db9`, `cli-tools@ba716fc`, `mcp-servers@7c0e958`; verified via GitHub API and `git ls-remote origin main`. |
| 2026-06-28 | platform | Ran read-only platform auth/resource checks. | CLI summaries in Platform Inventory. |
| 2026-06-28 | validation | Verified all clean local `kt-aicoding` repo heads against remote `main`; retried transient `ls-remote` failures through GitHub REST API. | Local/remote SHA checks for 16 repos; API checks for `claudecode-codex-config`, `claudecode-codex-switch`, and `claws`. |
| 2026-06-28 | validation | Revalidated standalone skill repositories. | `skill-goal`, `skill-image`, `skill-jd`, and `skill-taobao` all passed `quick_validate.py`; `skill-image` helper script also passed `bash -n` and smoke output. |
| 2026-06-28 | docs | Added copy-paste install/use guidance for image and goal skills, plus project-type image asset guidance. | `skill-image@4a7f215`, `images@83c4223`, `skill-goal@6bf2895`; verified with skill validators, SVG/export checks, sensitive scans, GitHub API README checks, and `git ls-remote origin main`. |

## Blockers

| Date | System | Attempted action | Result | Next action | Acceptable for completion |
| --- | --- | --- | --- | --- | --- |
| 2026-06-28 | GitHub GraphQL | `gh repo list kt-aicoding --limit 100 ...` | transient `EOF`; later REST API query succeeded | None for repository inventory | Yes |
| 2026-06-28 | Railway | `railway whoami` | unauthorized | Run `railway login` only when Railway resource checks are needed | Yes |
| 2026-06-28 | Local workspace | Edit `agents` or `hermes` | Earlier dirty worktrees were detected; current pass shows both repos clean and remote-matched | No blocker remains for inventory; do a focused review before future edits. | Yes |

## Completion Audit

- [x] Objective and instruction file reread after latest resume.
- [x] In-scope `kt-aicoding` repositories enumerated from current remote state.
- [x] Core local repository dirty status recorded.
- [x] Each repository has status: inventoried, deferred, in progress, not applicable, or externally blocked.
- [x] Completed/inventoried repository items have validation evidence appropriate to this pass.
- [x] Pushed repository items have remote refs matching local commits for this pass.
- [x] Platform checks have current read-only evidence or blocker records.
- [x] Public docs passed sensitive-output scan for final committed scope; matches are safety-policy text or placeholders, not raw secrets.
- [x] Remaining findings are classified as in-progress, deferred dirty worktree, external blocker, or non-destructive follow-up.
