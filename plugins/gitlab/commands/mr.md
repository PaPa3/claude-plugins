---
description: List and review GitLab merge requests
argument-hint: [list|view|diff] [mr-id]
allowed-tools: [Bash]
---

# GitLab Merge Requests

## Arguments
$ARGUMENTS

## Instructions

Parse the arguments:
- No args or `list`: run `glab mr list` and display open MRs as a table (ID, Title, Author, Branch, CI status)
- `view <id>`: run `glab mr view <id>` and show full details
- `diff <id>`: run `glab mr diff <id>` and summarize the changes

For `list`, offer to view or diff any specific MR.
For `view`, offer to run `glab mr diff` or `glab mr approve`.
