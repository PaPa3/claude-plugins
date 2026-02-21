# GitLab Plugin

Manage GitLab merge requests, issues, CI pipelines, and repositories from Claude Code using the `glab` CLI.

## Setup

```bash
# Verify glab is installed
glab version

# Authenticate
glab auth login
```

## Commands

| Command | Description |
|---------|-------------|
| `/mr [list\|view <id>\|diff <id>]` | Browse and review merge requests |
| `/ci [list\|status\|trace <job-id>]` | Inspect CI pipelines and job logs |

## Skill

The `gitlab-workflow` skill is auto-invoked when you ask about:
- Merge requests (list, review, approve, merge)
- GitLab issues
- CI/CD pipelines and job logs
- GitLab repositories or releases
