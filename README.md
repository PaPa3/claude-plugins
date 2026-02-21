# Claude Plugins

Personal Claude Code plugins repository.

## Plugins

| Plugin | Description | Requires |
|--------|-------------|---------|
| [langsmith](./plugins/langsmith/) | LangSmith observability — browse runs, prompts, datasets, experiments | `uvx`, `LANGSMITH_API_KEY` |
| [gitlab](./plugins/gitlab/) | GitLab — MRs, issues, CI pipelines, API | `glab` CLI |
| [google-workspace](./plugins/google-workspace/) | Google Workspace — Gmail, Calendar, Drive, Contacts, Tasks | `gog` CLI |
| [python](./plugins/python/) | Python tooling — run scripts, manage deps, use tools | `uv`, `uvx` |

## Installation

Add this repo as a marketplace in Claude Code, then install individual plugins:

```
/plugin marketplace add <git-url>
/plugin install langsmith@<marketplace-name>
/plugin install gitlab@<marketplace-name>
/plugin install google-workspace@<marketplace-name>
```

## Other Installed Plugins

Plugins installed from external marketplaces (not in this repo).

| Plugin | Marketplace | Description |
|--------|-------------|-------------|
| `context7` | claude-plugins-official | Up-to-date library docs and code examples |
| `pyright-lsp` | claude-plugins-official | Python type checking via Pyright LSP |
| `code-simplifier` | claude-plugins-official | Simplify and refine code for clarity |
| `playwright` | claude-plugins-official | Browser automation and E2E testing |
| `atlassian` | claude-plugins-official | Jira and Confluence integration |
| `slack` | claude-plugins-official | Slack messaging and search |
| `comprehensive-review` | claude-code-workflows | Multi-agent code review across architecture, security, and performance |
| `llm-application-dev` | claude-code-workflows | Workflows for LangGraph, RAG, vector search, and AI agent architectures *(local: stim)* |
| `agent-orchestration` | claude-code-workflows | Multi-agent system optimization and context management *(local: stim)* |

## Structure

Each plugin follows the standard Claude Code plugin layout:

```
plugins/
└── plugin-name/
    ├── .claude-plugin/
    │   └── plugin.json      # plugin metadata
    ├── .mcp.json            # MCP server config (if applicable)
    ├── commands/            # slash commands
    └── skills/              # auto-invoked skills
```
