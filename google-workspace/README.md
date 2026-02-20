# Google Workspace Plugin

Interact with Gmail, Google Calendar, Drive, Contacts, and Tasks from Claude Code using the `gogcli` CLI.

## Setup

Install `gogcli` from [gogcli.sh](https://gogcli.sh) or [GitHub](https://github.com/steipete/gogcli), then authenticate:

```bash
gogcli auth login
gogcli auth status
```

## Commands

| Command | Description |
|---------|-------------|
| `/gmail [query]` | Search and read Gmail emails |
| `/gcal [days]` | List upcoming Calendar events (default: 7 days) |

## Skill

The `google-workspace-tools` skill is auto-invoked when you ask about:
- Reading or searching Gmail
- Google Calendar events
- Google Drive files
- Google Contacts / Tasks
- Google Docs, Sheets, Slides
