---
description: List recent LangSmith runs for a project
argument-hint: [project-name] [--error]
allowed-tools: [mcp__langsmith__fetch_runs, mcp__langsmith__list_projects]
---

# List LangSmith Runs

## Arguments
$ARGUMENTS

## Instructions

1. If a project name is given, use `fetch_runs` with that project name.
   Otherwise, call `list_projects` first and ask the user which project to inspect.
2. If `--error` flag is present, filter for runs with errors only (`has_error = true`).
3. Display runs as a table: Run ID, Name, Status, Latency, Start time.
4. Highlight failed runs in the output.
5. Offer to show full trace details for any run.
