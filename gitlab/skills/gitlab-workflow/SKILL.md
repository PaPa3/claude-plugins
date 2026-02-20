---
name: gitlab-workflow
description: "Use this skill when the user wants to: (1) manage GitLab merge requests (list, view, create, approve, merge), (2) work with GitLab issues (list, view, create, comment, close), (3) inspect CI/CD pipelines and jobs, (4) browse GitLab repositories or projects, (5) view pipeline logs or traces, (6) manage GitLab variables or releases, (7) interact with GitLab API."
version: 1.0.0
---

# GitLab Workflow Skill

Use the `glab` CLI to interact with GitLab. All commands run in the context of the current git repository unless a project flag is given.

## Key Commands

### Merge Requests
```bash
glab mr list [--state=opened|closed|merged] [--author=<user>] [--assignee=<user>]
glab mr view <id>
glab mr diff <id>
glab mr create --title "<title>" --description "<desc>" [--draft]
glab mr approve <id>
glab mr merge <id>
glab mr note <id> --message "<comment>"
```

### Issues
```bash
glab issue list [--state=opened|closed] [--label=<label>] [--assignee=<user>]
glab issue view <id>
glab issue create --title "<title>" --description "<desc>"
glab issue note <id> --message "<comment>"
glab issue close <id>
```

### CI/CD Pipelines
```bash
glab ci list [--branch=<branch>]
glab ci status [--branch=<branch>]
glab ci view [<pipeline-id>]
glab ci trace [<job-id>]
glab job view <job-id>
```

### Repository
```bash
glab repo view [<repo>]
glab repo list
glab repo clone <repo>
```

### API (raw access)
```bash
glab api <endpoint> [--method=GET|POST|PUT|DELETE] [--field key=value]
```

### Releases
```bash
glab release list
glab release view <tag>
glab release create <tag> --name "<name>" --notes "<notes>"
```

## Workflow Patterns

### Review an MR
1. `glab mr list` — find pending MRs
2. `glab mr view <id>` — read description and CI status
3. `glab mr diff <id>` — inspect code changes
4. `glab mr note <id> --message "..."` — leave a review comment
5. `glab mr approve <id>` or report issues

### Debug a failing pipeline
1. `glab ci list` — find recent pipelines
2. `glab ci view <id>` — check job statuses
3. `glab ci trace <job-id>` — view full job log
4. Identify the failure and suggest a fix

### Create an MR from current branch
1. Ensure commits are pushed
2. `glab mr create --title "..." --description "..." [--draft]`
3. Set reviewers and labels as needed

## Tips
- Use `--repo owner/project` to target a different repository
- Use `glab api` for operations not covered by other subcommands
- Pipeline traces can be long — summarize key failure lines for the user
