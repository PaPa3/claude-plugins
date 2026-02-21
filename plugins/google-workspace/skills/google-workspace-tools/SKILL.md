---
name: google-workspace-tools
description: "Use this skill when the user wants to: (1) read, search, or send Gmail emails, (2) list or create Google Calendar events, (3) manage Google Drive files (list, upload, download, share), (4) manage Google Contacts or People, (5) manage Google Tasks, (6) work with Google Docs, Sheets, Slides, or Forms, (7) interact with any Google Workspace service via gog."
version: 1.0.0
---

# Google Workspace Tools Skill

Use the `gog` CLI to interact with Google Workspace services.

## Prerequisites

`gog` must be installed and authenticated:
```bash
gog login <email>      # first-time OAuth setup
gog status             # check current auth status
gog auth accounts      # list configured accounts
```

## Key Commands

### Gmail
```bash
gog gmail search <query>                            # search emails/threads
gog gmail get <messageId>                           # read a message (aliases: info, show)
gog gmail send --to=<email> --subject=<subj> --body=<body>
gog gmail labels list                               # list labels
```

### Google Calendar
```bash
gog calendar events [<calendarId>]                  # list events (aliases: list, ls)
gog calendar events --min=<date> --max=<date>       # filter by date range
gog calendar event <calendarId> <eventId>           # get event details (aliases: get, info, show)
gog calendar calendars                              # list all calendars
```

### Google Drive
```bash
gog drive ls [--folder=<id>]                        # list files in root or folder
gog drive search <query>                            # full-text search (aliases: find)
gog drive get <fileId>                              # get file metadata
gog drive download <fileId> [--output=<path>]       # download file (aliases: dl)
gog drive upload <localPath> [--folder=<id>] [--name=<name>]   # upload file (aliases: up, put)
gog drive delete <fileId>                           # delete file
```

### Google Contacts
```bash
gog contacts list                                   # list contacts (aliases: ls)
gog contacts search <query>                         # search by name/email/phone
gog contacts get <resourceName>                     # get contact details (aliases: info, show)
gog contacts create --name=<name> --email=<email>   # create contact (aliases: add, new)
gog contacts update <resourceName> [flags]          # update contact (aliases: edit, set)
gog contacts delete <resourceName>                  # delete contact (aliases: rm, del)
```

### Google Tasks
```bash
gog tasks lists                                     # list all task lists
gog tasks list <tasklistId>                         # list tasks in a list (aliases: ls)
gog tasks get <tasklistId> <taskId>                 # get task details (aliases: info, show)
gog tasks add <tasklistId> --title=<title> [--due=<date>]   # add task (aliases: create)
gog tasks done <tasklistId> <taskId>                # mark task complete (aliases: complete)
gog tasks update <tasklistId> <taskId> [flags]      # update task (aliases: edit, set)
```

### Google Docs / Sheets / Slides
```bash
gog docs list
gog docs view <doc-id>
gog sheets list
gog sheets read <sheet-id> [--range=<A1notation>]
gog slides list
```

## Workflow Patterns

### Find and read an email
1. `gog gmail search "from:user@example.com subject:invoice"` — find matching threads
2. `gog gmail get <messageId>` — read the message content
3. Summarize or act on the content

### Browse calendar events
1. `gog calendar calendars` — list available calendars
2. `gog calendar events --min=2026-02-21 --max=2026-02-28` — list upcoming events
3. `gog calendar event <calendarId> <eventId>` — view full details

### Find a file in Drive
1. `gog drive search "report"` — search Drive by name/content
2. `gog drive ls` — browse root folder
3. `gog drive download <id>` — download if needed

### Manage tasks
1. `gog tasks lists` — list all task lists
2. `gog tasks list <tasklistId>` — list tasks
3. `gog tasks add <tasklistId> --title="My task"` — add a task
4. `gog tasks done <tasklistId> <taskId>` — mark complete

## Output Format
- Present emails as: From, Subject, Date, Body preview
- Calendar events as: Title, Date/Time, Attendees, Location
- Drive files as: Name, Type, Modified date, Owner
- Always confirm destructive operations (delete, trash, send) before executing
