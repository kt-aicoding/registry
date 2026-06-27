# MCP Servers

Model Context Protocol servers for AI coding workflows.

## Repositories

| Repository | Status | Notes |
| --- | --- | --- |
| [`kt-aicoding/mcp-servers`](https://github.com/kt-aicoding/mcp-servers) | created | Staging monorepo for MCP servers before mature servers graduate into standalone repos. |

## Operating References

| Document | Notes |
| --- | --- |
| [Local CLI And MCP System](local-cli-mcp-system.md) | Default MCP surface is intentionally minimal: `context7` for current docs and `playwright` for browser automation. Provider MCPs are not default-enabled when mature CLIs cover the workflow. |

## Migration Candidates

| Repository | Current Location | Status | Notes |
| --- | --- | --- | --- |
| `ai-coding-mcp` | `kevinten-ai/ai-coding-mcp` | candidate | Direct fit. |
| `mcp-http-proxy` | `kevinten-ai/mcp-http-proxy` | evaluate | Move if framed as coding-agent network tooling. |
| `mcp-content-styles` | `kevinten-ai/mcp-content-styles` | reference | MCP-related, but not necessarily AI coding specific. |
| `mcp-image-gen` | `kevinten-ai/mcp-image-gen` | reference | MCP-related, but broader than coding. |
| `mcp-ffmpeg` | `kevinten-ai/mcp-ffmpeg` | reference | MCP-related, but broader than coding. |
