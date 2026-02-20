# Claude Plugins

Personal Claude Code plugins repository.

## Plugins

| Plugin | Description | Requires |
|--------|-------------|---------|
| [langsmith](./langsmith/) | LangSmith observability — browse runs, prompts, datasets, experiments | `uvx`, `LANGSMITH_API_KEY` |
| [gitlab](./gitlab/) | GitLab — MRs, issues, CI pipelines, API | `glab` CLI |
| [google-workspace](./google-workspace/) | Google Workspace — Gmail, Calendar, Drive, Contacts, Tasks | `gogcli` CLI |

## Installation

Add this repo as a marketplace in Claude Code, then install individual plugins:

```
/plugin marketplace add <git-url>
/plugin install langsmith@<marketplace-name>
/plugin install gitlab@<marketplace-name>
/plugin install google-workspace@<marketplace-name>
```

## Structure

Each plugin follows the standard Claude Code plugin layout:

```
plugin-name/
├── .claude-plugin/
│   └── plugin.json      # plugin metadata
├── .mcp.json            # MCP server config (if applicable)
├── commands/            # slash commands
└── skills/              # auto-invoked skills
```
