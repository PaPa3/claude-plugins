# LangSmith Plugin

Browse and debug your LLM traces, prompts, datasets, and experiments in LangSmith — directly from Claude Code.

## Setup

Requires `uv` / `uvx` to run the MCP server:

```bash
# Verify uvx is available
uvx --version

# Set your API key (add to ~/.bashrc or ~/.zshrc)
export LANGSMITH_API_KEY=ls__...
export LANGSMITH_API_URL=https://api.smith.langchain.com  # or your self-hosted URL
```

## MCP Server

Uses [langsmith-mcp-server](https://github.com/langchain-ai/langsmith-mcp-server) via `uvx langsmith-mcp-server`.

## Commands

| Command | Description |
|---------|-------------|
| `/ls-runs [project] [--error]` | List recent runs, optionally filtered to errors |
| `/ls-experiments [filter]` | Compare experiments with latency/cost/feedback metrics |

## Skill

The `langsmith-observability` skill is auto-invoked when you ask about:
- LangSmith traces, runs, or execution history
- Debugging AI pipeline failures
- Listing projects, datasets, prompts, or experiments
- Checking billing usage
