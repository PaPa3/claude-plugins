---
description: Inspect GitLab CI/CD pipelines and job logs
argument-hint: [list|status|trace <job-id>]
allowed-tools: [Bash]
---

# GitLab CI/CD

## Arguments
$ARGUMENTS

## Instructions

Parse the arguments:
- No args or `list`: run `glab ci list` and show recent pipelines (ID, Status, Branch, Duration, Created)
- `status`: run `glab ci status` for the current branch
- `view <pipeline-id>`: run `glab ci view <id>` to show job breakdown
- `trace <job-id>`: run `glab ci trace <job-id>` and summarize the log — highlight errors, warnings, and final status

For failures, suggest likely causes and fixes based on log content.
