---
name: google-workspace-tools
description: "Use this skill when the user wants to: (1) read, search, or send Gmail emails, (2) list or create Google Calendar events, (3) manage Google Drive files (list, upload, download, share), (4) manage Google Contacts or People, (5) manage Google Tasks, (6) work with Google Docs, Sheets, Slides, or Forms, (7) interact with any Google Workspace service via gogcli."
version: 1.0.0
---

# Google Workspace Tools Skill

Use the `gogcli` CLI to interact with Google Workspace services.

## Prerequisites

`gogcli` must be installed and authenticated:
```bash
gogcli auth login          # first-time OAuth setup
gogcli auth status         # check current auth status
gogcli accounts list       # list configured accounts
```

## Key Commands

### Gmail
```bash
gogcli gmail list [--query=<q>] [--limit=<n>]     # list/search emails
gogcli gmail read <message-id>                      # read an email
gogcli gmail send --to=<email> --subject=<subj> --body=<body>
gogcli gmail reply <message-id> --body=<body>
gogcli gmail trash <message-id>
gogcli gmail labels list
```

### Google Calendar
```bash
gogcli calendar list [--start=<date>] [--end=<date>]   # list events
gogcli calendar view <event-id>
gogcli calendar create --title=<title> --start=<datetime> --end=<datetime> [--attendees=<emails>]
gogcli calendar delete <event-id>
gogcli calendars list                                   # list all calendars
```

### Google Drive
```bash
gogcli drive list [--query=<q>] [--folder=<id>]
gogcli drive download <file-id> [--output=<path>]
gogcli drive upload <local-path> [--folder=<id>] [--name=<name>]
gogcli drive share <file-id> --with=<email> [--role=reader|writer|owner]
gogcli drive delete <file-id>
```

### Google Contacts / People
```bash
gogcli contacts list [--query=<name>]
gogcli contacts view <contact-id>
gogcli contacts create --name=<name> --email=<email> [--phone=<phone>]
```

### Google Tasks
```bash
gogcli tasks list [--tasklist=<id>]
gogcli tasks create --title=<title> [--due=<date>] [--tasklist=<id>]
gogcli tasks complete <task-id>
gogcli tasklists list
```

### Google Docs / Sheets / Slides
```bash
gogcli docs list
gogcli docs view <doc-id>
gogcli sheets list
gogcli sheets read <sheet-id> [--range=<A1notation>]
gogcli slides list
```

## Workflow Patterns

### Find and read an email
1. `gogcli gmail list --query="from:user@example.com subject:invoice"` — find matching emails
2. `gogcli gmail read <id>` — read the email content
3. Summarize or act on the content

### Schedule a meeting
1. `gogcli calendar list --start=today --end=+7d` — check free slots
2. `gogcli calendar create --title="..." --start="..." --end="..." --attendees="a@b.com,c@d.com"`
3. Confirm the created event details

### Find a file in Drive
1. `gogcli drive list --query="name contains 'report'"` — search Drive
2. `gogcli drive download <id>` — download if needed
3. Present file metadata or content to user

## Output Format
- Present emails as: From, Subject, Date, Body preview
- Calendar events as: Title, Date/Time, Attendees, Location
- Drive files as: Name, Type, Modified date, Owner
- Always confirm destructive operations (delete, trash, send) before executing
