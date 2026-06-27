# Local CLI And MCP System

Last refreshed: 2026-06-27.

This page records the current operating model for Kevin's local AI coding environment. It is an index-level snapshot, not a secret-bearing machine backup. Do not store tokens, API keys, OAuth secrets, browser cookies, private project trust lists, or private business context here.

Detailed source files remain in the private local workstation inventory and cost-audit notes. This public registry stores only the sanitized operating model.

## Operating Model

| Area | Default |
| --- | --- |
| Primary agent CLI | `codex` |
| Compatibility agent CLIs | `claude`, `gemini`, `qwen` |
| Source control | `git`, `gh` |
| Cloud platforms | Provider CLIs, not provider MCPs |
| Current docs | `context7` MCP |
| Browser QA and automation | Playwright CLI and `playwright` MCP |
| Design tools | Do not use Figma MCP by default |

Principle: deterministic cloud, database, source-control, and deployment operations should use CLIs. MCP should stay small and reserved for agent-native value such as current documentation retrieval and browser automation.

## Default MCP Surface

| MCP server | Status | Purpose |
| --- | --- | --- |
| `context7` | enabled | Current library/framework/API documentation |
| `playwright` | enabled | Browser automation and QA |

Provider MCPs are intentionally not default-enabled for GitHub, Vercel, Supabase, Cloudflare, or filesystem access because local CLIs already cover those workflows with lower overhead and clearer auditability.

## CLI Layers

| Layer | Tools | Role |
| --- | --- | --- |
| Agent entrypoints | `codex`, `claude`, `gemini`, `qwen` | AI coding sessions, compatibility, and cross-checks |
| Cloud and deploy | `vercel`, `supabase`, `wrangler`, `tcb`, `netlify`, `flyctl`, `railway`, `eas` | Deployments, resources, billing-risk discovery |
| JavaScript and TypeScript | `node`, `npm`, `pnpm`, `bun`, `tsx`, `tsc` | Web app and Node tooling |
| Python | `uv`, `pipx`, `python3` | Python projects and utility scripts |
| Go and Java | `go`, `mvn`, `java` | Backend and library projects |
| QA and security | `playwright`, `actionlint`, `gitleaks`, `osv-scanner` | Browser checks, GitHub Actions linting, secret/dependency risk scans |
| Registry and packaging | `clawhub`, `openclaw`, `mcporter` | Skill/package and MCP-related maintenance |

## Current Provider State

| Provider | CLI state | Resource note |
| --- | --- | --- |
| Vercel | logged in as `wshten-3419` | Hobby team; 38 projects; 5 Cron jobs; no contracts, Blob stores, Marketplace resources, or alert groups found from CLI |
| Supabase | logged in | only `kevinten10` remains after demo consolidation; old `trip-agent` and `law-agent` projects were deleted |
| CloudBase | logged in | one normal personal environment: `ai-native-2gknzsob14f42138`, expires 2026-11-04 |
| Cloudflare | logged in | real resources exist: Pages, KV, D1, R2, and Queue |
| Netlify | logged in | current account site list returned empty |
| Fly.io | logged in | app list returned empty |
| Railway | installed, not authenticated | complete `railway login --browserless` before resource or cost checks |
| GitHub | keyring auth for `kevinten10` works | use `env -u GH_TOKEN gh ...` when the outer shell has a stale `GH_TOKEN` |

## Repository Placement

| Content | Preferred repository |
| --- | --- |
| Canonical CLI/MCP/skill/workflow index | `kt-aicoding/registry` |
| Small CLI utilities | `kt-aicoding/cli-tools` |
| MCP server staging | `kt-aicoding/mcp-servers` |
| Reusable skills | `kt-aicoding/skills` |
| Claude Code and Codex configuration kit | `kt-aicoding/claudecode-codex-config` |
| Agent workflow templates | `kt-aicoding/agent-workflows` |

## Maintenance Commands

Run before cloud operations:

```bash
vercel whoami
supabase projects list
wrangler whoami
tcb env list
netlify status
flyctl auth whoami
railway whoami
```

Run for monthly tool health:

```bash
codex mcp list
codex doctor --json
npm outdated -g --depth=0
env -u GH_TOKEN gh auth status --active
actionlint --version
gitleaks version
osv-scanner --version
```

Run for monthly platform resource checks:

```bash
vercel projects list --scope kevintens-projects
supabase projects list
wrangler pages project list
wrangler kv namespace list
wrangler d1 list
wrangler r2 bucket list
wrangler queues list
tcb env list
netlify sites:list --json
flyctl apps list --json
```

## Governance Notes

- Keep global MCP minimal: `context7` and `playwright`.
- Prefer project-local tools and wrappers over global installations when a project provides them.
- Do not install Docker, Colima, Flutter, Dart, or global Gradle until a concrete project requires them.
- Treat Cloudflare as a real cost surface because R2/D1/Queues resources exist.
- Keep Supabase demo development in the existing `kevinten10` project unless the user explicitly accepts the cost of a new project.
- Upgrade global tools deliberately: patch-level Codex updates are low risk; `pnpm` major upgrades and Railway major upgrades should be project-driven.
